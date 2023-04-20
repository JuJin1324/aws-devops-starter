# aws-c3-starter
> c3: CodeBuild - CodeDeploy - CodePipeline

## CodeBuild
### 개요
> CodeCommit 혹은 Github 과 같은 Remote Repository 에 코드를 테스트 및 빌드 후 실행 파일을 
> S3 에 저장해준다.  
> 
> CodeBuild 는 여러 언어를 지원하며, 빌드 툴도 Maven 및 Gradle 을 지원한다.   
> CodeBuild 는 수동 및 자동으로 빌드를 실행시킬 수 있으며 Jenkins 플러그인도 지원한다.  

### 구성
> **프로젝트 구성**  
> `이름`: 프로젝트 이름을 입력한다.  
> `설명`: 프로젝트 설명을 입력한다.  
> `동시 빌드 제한`: 동시 빌드 제한 갯수를 입력한다.  
> 
> **소스**  
> `소스 공급자`: CodeBuild 에서 빌드할 소스코드 프로젝트를 가져올 Remote Repository 종류 입력  
> `리포지토리`: 소스 공급자에서 CodeBuild 에서 빌드할 소스코드 프로젝트명 입력  
> `Git clone 깊이`: git clone 시 프로젝트 전체의 git commit 을 가져오는 것이 아닌 clone 깊이의 값에 따른
> commit 갯수만 가져오도록 조정. 여기서는 마지막 git commit 만 필요함으로 일반적인 경우에는 `1` 을 입력  
> `Git 하위 모듈`: 리포지토리 소스 코드 프로젝트에 딸린 하위 모듈을 가져오는 것에 대한 옵션  
> 
> **환경**  
> `새 환경 이미지`: 빌드 시 AWS 컴퓨팅을 이용하려면 `관리형 이미지` 를 선택하고 도커 이미지를 사용하려면 `사용자 지정 이미지`를 사용한다.  
> `운영 체제`: 관리형 이미지의 경우 Amazon Linux 2, Ubuntu 중 선택한다.  
> `런타임`: 2023-04-13 기준 런타임은 Standard 밖에 없다.  
> `이미지`: arm 용 빌드 시에는 aarch64 를, 인텔 용 빌드 시에는 x86_64 를 선택하고 버전은 최신 버전을 선택한다.  
> `환경 유형`: Linux 를 이용한다.  
> `권한이 있음`: 프로젝트 빌드에 Docker 를 이용하는 경우(ex.testcontainers) 활성화한다.  
> `서비스 역할`: 처음 CodeBuild 프로젝트를 생성하는 경우 새 서비스 역할을 통해서 서비스 역할을 새로 생성 후
> 동일 역학을 갖는 CodeBuild 프로젝트를 생성한 경우라면 기존 서비스 역할에서 선택한다.  
> 추가 구성  
> `VPC`: 소스 코드 프로젝트에서 테스트 시 EC2 와 내부 연결이 필요한 경우가 아니라면 VPC 를 선택하지 않는다.  
> `컴퓨팅`: 소스코드 빌드에 맞는 스펙을 선택한다.  
> 
> **Buildspec**  
> `빌드 사양`: `buildspec 파일 사용` 을 선택 후 프로젝트 루트에 buildspec.yml 생성하여 관리한다.   
>
> `build`: 프로젝트 빌드에 관한 정보를 담는다.  
> `build.on-failure`: 빌드 중 오류가 발생하여 빌드가 실패한 경우 해야할 작업을 기술한다.(ABORT, CONTINUE 중 택 1)  
> `build.commands`: 빌드 작업 시 실행할 명령어들의 목록
>
> `post_build`: 빌드가 성공적으로 완료되면 이후 실행할 프로세스에 대한 정보를 담는다.    
> `post_build.on-failure`: 포스트 빌드 중 오류가 발생하여 포스트 빌드가 실패한 경우 해야할 작업을 기술한다.(ABORT, CONTINUE 중 택 1)  
> `post_build.commands`: 포스트 빌드 작업 시 실행할 명령어들의 목록
>
> `artifacts`: 빌드 산출물(artifact)에 대한 정보  
> `files`: S3 에 올릴 파일 목록  
> `discard-paths`: 산출물이 존재하는 경로를 버리고 파일 자체들만 S3 에 위치시킬 경우 yes, 디렉터리 경로를 유지해서 S3 에 넣을 경우 no
> ```yaml
> version: 0.2
> phases:
>   build:
>       on-failure: ABORT
>       commands:
>           - echo Build Starting on `date`
>           - java -version
>           - chmod +x ./gradlew
>           - ./gradlew bootJar -Pprofile=dev -x test -x asciidoctor
>   post_build:
>       on-failure: ABORT
>       commands:
>           - echo $(basename ./build/libs/*.jar)
>           - echo $(basename ./build/scripts/*.sh)
>           - echo $(basename ./build/resources/main/*.yml)
>           - pwd
> artifacts:
>   files:
>       - build/libs/*.jar
>       - build/scripts/*.sh
>       - build/resources/main/application-dev.yml
>   discard-paths: yes
> ```

### 주의사항
> AWS CodeBuild 에서 @SpringBootTest 를 이용하여 테스트를 시도할 경우 Exception 이 발생하는데,
> AWS CodeBuild 시 사용되는 컴퓨팅 인스턴스가 인터넷에 연결되지 않아서 인듯 하다.  
> 현재 나의 경우 AWS CodeBuild 에서는 테스트 자체를 빼고 테스트하도록 buildspec.yml 의 `phases.build.commands` 에
> `./gradlew bootJar -x test -x asciidoctor` 를 통해서 모든 테스트 및 asciidoctor(Spring Rest Docs) 에 관련된 
> task 를 모두 빼고 빌드를 실행하도록 설정하였다.  

### 비용
> 2023-04-13 기준   
> general1.small(2 vCPU, 3GB): 0.005 USD  

### Jenkins 플러그인
> TODO

---

## CodeDeploy
### 개요
> AWS CodeDeploy 는 애플리케이션 배포를 자동화하기 위한 AWS 의 배포 서비스이다.  
> 배포는 EC2 인스턴스, 온프레미스 서버 혹은 가상머신, serverless Lambda functions 등에 할 수 있다.  
> AWS CodeDeploy 는 컴파일을 위한 소스코드를 AWS CodeCommit, Github, Bibucket 등에서 가져오며,
> Amazon S3 bucket 에 빌드된 artifect 를 저장한다.  

### 구성 요소
> **애플리케이션(Application)**  
> 애플리케이션 이름: 이름은 유니크해야한다.
> 컴퓨팅 플랫폼: 배포될 컴퓨터의 플랫폼을 지정한다. 온프레미스 서버/EC2 인스턴스, 서버리스(람다), Amazon ECS(Docker)를 지원한다.
>
> **배포 그룹(Deployment group)**  
> EC2 인스턴스들에 태그를 붙여놓은 논리적(logical) 그룹이다.  
> 배포 그룹에는 EC2 인스턴스 1개 혹은 Auto scailing 그룹이 올 수 있다.
>
> **배포 구성(Deployment configuration)**  
> 배포의 성공/실패 여부를 결정하기 위한 룰을 정의한다.  
> 컴퓨팅 플랫폼에 따라 다른 룰이 올 수 있다.  
> 일단 `EC2/온프레미스`를 예로 들면 룰은 `최소 정상 호스트`가 있다. 최소 정상 호스트는 숫자 혹은 백분율로 지정할 수 있으며,
> 숫자는 말 그대로 배포 과정에서 healthy 한 호스트가 몇 개가 되었을 때 정상적으로 배포되었는지 판단하는 기준이 되며,
> 백분율은 정해진 퍼센트의 인스턴스들이 healthy 한 상태가 되었을 때 정상적으로 배포되었는지 판단하는 기준이된다.
>
> **배포 유형(Deployment type)**  
> 현재 위치(In-place deployment): 기존 실행 중이던 애플리케이션은 종료하고 새롭게 배포된 애플리케이션을 배포/설치 및 실행 후 검증한다.  
> `EC2/온프레미스` 플랫폼에서만 사용 가능한 유형이다.  
> 이 유형으로 배포 시 로드밸런서를 이용하는 것이 추천된다. 로드밸런서 이용 시 배포될 인스턴스들의 등록을 해제 후 업그레이드를 실행한다.   
> 
> 블루/그린(Blue/green deployment): 신규 배포 시 기존의 배포 환경을 종료하지 않고 신규와 기존 두 개의 동일한 프로덕션 환경을 실행 상태로 두는 방식이다.  
> 배포 시에 발생하는 다운 타임을 최소화하기 위해서 사용되는 배포 방식이다.  
> 두 개의 환경은 각각 블루와 그린으로 명명하며 블루는 기존에 배포된 프로덕션 애플리케이션이며, 그린은 신규로 배포된 프로덕션 애플리케이션을 의미한다.  
> 
> EC2/온프레미스에서 블루/그린 배포 동작  
> 1.신규 버전의 애플리케이션 배포를 위한 신규 인스턴스가 생성된다.    
> 2.신규 버전의 애플리케이션이 신규 인스턴스에 설치된다.    
> 3.설정된 Optional 대기 시간 동안 애플리케이션 테스트 및 시스템 검증이 진행된다.  
> 4.신규 인스턴스가 모두 준비가 완료되면 ELB(Elastic Load Balancer)에 등록된다. 신규 인스턴스 등록이 모두 끝나
> 요청이 라우팅될 수 있는 상태가 되면, 기존 인스턴스들은 등록을 해제한다.   
> `EC2/온프레미스` 플랫폼에서의 블루/그린 배포는 EC2 인스턴스에서만 가능하며, 온프레미스 환경에서는 불가능하다.   
> 
> 서버리스 람다에서 블루/그린 배포  
> 서버리스 람다에서는 기존 배포 유형이 블루/그린 방식이다. 그럼으로 서버리스 람다 플랫폼에서 배포 시 배포 유형을 따로 지정할 필요가 없다.  
> 
> Amazon ECS(Docker)에서 블루/그린 배포  
> 애플리케이션 배포가 성공적으로 완료되면 트래픽이 기존 태스크에서 신규 태스크로 변경된다.
> 
> **서비스 역할(IAM Instance profile)**
> AWS EC2 인스턴스에 배포 작업을 하기 위해서는 Amazon S3 버킷에 접근하여 artifect 를 가져올 수 있어야하고,
> Github 이나 CodeCommit 과 같은 소스코드 리포지토리에 접근하여 빌드할 소스코드를 가져올 수 있어야하고,
> 배포 과정에서 신규 EC2 인스턴스를 생성할 수 있어야한다.  
> CodeDeploy 에서 위의 작업들을 수행하기 위해서는 IAM Role 이 필요하다.  
> 만약 배포 플랫폼이 서버리스 람다 혹은 ECS(Docker) 인 경우 IAM Role 은 불필요하다.  
>
> **Revision**  
> Revision 은 수정된 컨텐츠의 묶음을 의미한다.  
> 빌드 완료된 artifact, 웹 페이지들, 실행 파일들, 배포 스크립트 및 AppSpec 파일이 될 수 있다.
> AppSpec 파일은 yml 혹은 JSON 파일로 작성이 가능하다.  
> EC2/온프레미스 플랫폼에서 AppSpec 파일이 요구되며 AppSpec 파일을 통해 소스 파일이 배포되거나 스크립트를 실행시킨다.  
> 
> **주의 사항**  
> 배포 그룹에서 최소 healthy 인스턴스 수를 계산할 때 stop 된 인스턴스는 failed 로 인식된다.  
> 너무 많은 인스턴스를 stop 시켜서 최소 healthy 인스턴스 수보다 적어지면 배포가 실패로 종료될 수 있다.  

### 비용
> 2023-04-19 기준   
> AWS CodeDeploy 를 통해 Amazon EC2, AWS Lambda 또는 Amazon ECS에 코드를 배포하는 데는 추가 비용이 부과되지 않습니다.  
> 온프레미스에 CodeDeploy를 사용하는 경우: AWS CodeDeploy를 사용해 온프레미스 인스턴스를 업데이트하는 경우에는 업데이트당 `0.02 USD`의 요금이 부과됩니다. 
> 최소 요금 및 사전 약정은 없습니다. 예를 들어 인스턴스 3개에 대한 배포는 인스턴스 업데이트 3회와 동일합니다. 
> CodeDeploy에서 인스턴스를 업데이트하는 경우에만 요금이 부과됩니다. 배포가 진행되지 않은 인스턴스에 대해서는 요금이 부과되지 않습니다.

---

## CodePipeline
### 개요
> CodePipeline 은 프로그램의 소스 코드, 빌드, 테스트, 배포 의 전반을 관리한다.  
> 그 중 빌드, 테스트를 CodeBuild 를 사용한다.  

### TODO
> TODO

--- 

## CI/CD
### CI
> TODO

### CD
> TODO
