# aws-devops-starter

## DevOps
### 개요
> DevOps는 애플리케이션과 서비스를 빠른 속도로 제공할 수 있도록 조직의 역량을 향상시키는 문화 철학, 방식 및 도구의 조합입니다.
> Plan -> Build -> Test -> Release -> Monitoring   
> -> Plan -> Build -> Test -> Release -> Monitoring ...(반복)    

### DevOps 의 이점
> **속도**  
> 작업 속도가 빨라지므로 고객을 위해 더 빠르게 혁신하고, 시장 변화에 더 잘 적응하고, 좀 더 효율적으로 비즈니스 성과를 창출할 수 있습니다. 
> DevOps 모델을 사용하면 개발자와 운영팀이 이러한 성과를 실현할 수 있습니다. 예를 들어 마이크로 서비스와 지속적 전달을 사용하면 
> 팀에서 서비스를 주도적으로 운영하여 업데이트를 좀 더 빠르게 릴리스할 수 있습니다.
>  
> **신속한 제공**  
> 릴리스의 빈도와 속도를 개선하여 제품을 더 빠르게 혁신하고 개선할 수 있습니다. 
> 새로운 기능의 릴리스와 버그 수정 속도가 빨라질수록 고객의 요구에 더 빠르게 대응하여 경쟁 우위를 강화할 수 있습니다. 
> 지속적 통합과 지속적 전달은 빌드에서 배포까지 소프트웨어 릴리스 프로세스를 자동화하는 방식입니다.
> 
> **안정성**  
> 최종 사용자에게 지속적으로 긍정적인 경험을 제공하는 한편 더욱 빠르게 안정적으로 제공할 수 있도록 애플리케이션 업데이트와 인프라 변경의 품질을 보장합니다. 
> 지속적 통합(CI)및 지속적 전달(CD)과 같은 방식을 사용하여 각 변경 사항이 제대로 작동하며 안전한지 테스트합니다. 
> 모니터링과 로깅 방식을 통해 실시간으로 성능에 대한 정보를 얻을 수 있습니다.
> 
> **확장**  
> 규모에 따라 인프라와 개발 프로세스를 운영 및 관리합니다. 자동화와 일관성이 지원되므로 위험을 줄이면서 복잡한 시스템 또는 변화하는 시스템을 
> 효율적으로 관리할 수 있습니다. 예를 들어 코드형 인프라(Infrastructure as Code)를 사용하면 개발, 테스트 및 프로덕션 환경을 반복 가능하고 
> 좀 더 효율적인 방식으로 관리할 수 있습니다.
> 
> **협업 강화**  
> 주인의식 및 책임과 같은 가치를 강조하는 DevOps 문화 모델에서 좀 더 효과적인 팀을 구축합니다. 개발자와 운영팀은 긴밀하게 협력하고, 많은 책임을 공유하며, 
> 워크플로를 결합합니다. 이를 통해 비효율성을 줄이고 시간을 절약합니다(예: 개발자와 운영팀 간의 인도 기간 단축, 실행되는 환경을 고려한 코드 작성 등).
> 
> **보안**  
> 제어를 유지하고 규정을 준수하면서 신속하게 진행할 수 있습니다. 자동화된 규정 준수 정책, 세분화된 제어 및 구성 관리 기술을 사용함으로써 
> 보안을 그대로 유지하면서 DevOps 모델을 도입할 수 있습니다. 예를 들어 코드형 인프라와 코드형 정책을 사용하면 규모에 따라 규정 준수를 정의하고 추적할 수 있습니다.

### DevOps 의 기술적 구성요소
> 1. 코드 기반 인프라(Infrastructure as Code): 코드 기반 인프라는 인프라 구성을 소프트웨어 프로그래밍하는 것처럼 처리하는 방식이다.  
> 결과적으로 애플리케이션을 작성하는 작업과 애플리케이션이 실행되는 환경을 구현하는 작업을 코드 기반으로 관리할 수 있다.  
> 2. 버전 관리(Version Control): 개발 시간이 지남에 따라 발생되는 소스코드의 변경 사항을 개발팀이 관리하는 데 도움을 주는 소프트웨어 도구.
> 3. One-Step 빌드와 배포(Build & Deploy): 배포 작업의 위험을 최소화하는 것은 무엇보다 중요한 일이며, 배포 툴은 안정적이며 효과적인 소스 배포와 운영
> 서비스에 영향도를 최소화하면서 배포할 수 있도록 도와준다. 대량의 변경된 내용을 한 번에 배포하기보다 자동화된 배포 툴을 통해 조금씩 자주 변경되는 내용을
> 배포함으로써 위험을 분산시킬 수 있게 한다. 잦은 배포 주기는 배포 위험이나 결함을 사전에 미리 파악할 수 있게 도와준다. 이런 배포 도구는 자동화를 통해 지속적으로
> 수행 가능한 시스템으로 구성되며, 이런 자동화 도구는 DevOps 의 기술적 구성 요소의 핵심이다.  
> 4. 장애 발생 시 인프라의 빠른 배포: DevOps 기반의 인프라 환경은 문제 발생 시 기존 인프라를 빠르게 재배포가 가능한 환경으로 제공한다.

### 참조사이트
> [DevOps란 무엇입니까?](https://aws.amazon.com/ko/devops/what-is-devops/)

---

## IaC(Infrastructure as Code) 도구
### 개요
> IaC 도구에 관한 내용 중 명확히 이해해야 할 것은 Configuration Orchestration Tool 과 Configuration Management Tool 의 차이다.  
> `Terraform` 과 `AWS CloudFormation` 과 같은 Orchestration Tool 은 서버 및 기타 인프라의 구축을 자동화하도록 설계되었다.  
> `Chef`, `Puppet` 과 같은 Management Tool 은 이미 프로비저닝된 이 인프라의 소프트웨어와 시스템을 구성하고 관리하는 데 도움이 된다.  

### Terraform
> 오픈소스 기반의 `Configuration Orchestration Tool` 로 클라우드/온프레미스에 구애받지 않고 사용할 수 있는 인프라 프로비저닝 툴이다. 

### AWS CloudFormation
> `Configuration Orchestration Tool` 로 JSON/YAML 을 사용하여 템플릿을 생성할 수 있다.



---

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
> 동일 역할을 갖는 CodeBuild 프로젝트를 생성한 경우라면 기존 서비스 역할에서 선택한다.  
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

### aws cli
> **start-build**  
> AWS CodeBuild 프로젝트의 빌드를 새로 실행한다.  
> ```shell
> aws codebuild start-build --project-name <프로젝트 이름>
> ```
> 
> **batch-get-builds**  
> AWS CodeBuild 프로젝트의 진행 상태를 조회한다. watch 명령어와 같이 사용하는게 효과적이다. 
> Bash shell 스크립트 파일에 start-build 와 함께 작성한다.
> ```shell
> # 원형
> watch -d aws codebuild batch-get-builds --ids <프로젝트 빌드 ID>
> 
> # deploy-dev.sh
> buildId=`aws codebuild start-build --project-name <프로젝트 이름> | jq '.build.id' | sed 's/\"//g'`
> watch -d aws codebuild batch-get-builds --ids $buildId
> ```
>
> **list-builds**  
> `--sort-order=DESCENDING` 을 통해서 최근에 빌드한 프로젝트가 가장 상위에 오도록 정렬하여 가져올 수 있다.  
> `| jq '.ids'` 를 통해서 빌드 ID 만 콘솔에 표시한다.  
> ```shell
> aws codebuild list-builds --sort-order=DESCENDING | jq '.ids'
> ```
> 
> list-builds 를 응용하여 projectName 으로 설정한 프로젝트 중 가장 최근에 빌드된 빌드 ID 를 찾아서
> S3 의 경로를 지정해 artifact 를 다운받는다.  
> 다운받은 artifact 에 start-aws-c3-starter.sh 스크립트 파일을 이용해서 artifact 를 실행한다.
> (물론 빌드 시 스크립트 파일이 artifact 에 포함되도록 개발자가 개발하는 빌드 툴에서 직접 설정해야한다.)  
> ```shell
> projectName='aws-c3-starter'
> buildId=`aws codebuild list-builds --sort-order=DESCENDING | jq '.ids' | grep "$projectName" -m 1 | sed "s/$projectName://" | sed 's/\"//g' | sed 's/,//g' | sed 's/ //g'`
> aws s3 cp s3://starter.codebuild/dev/$buildId/$projectName/ . --recursive
> chmod +x start-$projectName.sh
> ```

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

### 에이전트
> ec2에 설치하는 프로그램으로, CodeDeploy에서 해당 ec2를 사용할 수 있도록 하는 프로그램이다. ec2이외의 배포환경에는 필요하지 않다.    
> 에이전트는 어플리케션 개정, 배포기록, 배포스크립트 등을 EC2의 루트 디렉토리에 저장한다. 
> Amazon Linux, Ubuntu server, RHEL 인 경우, `/opt/codedeploy-agent/deployment-root` 에 위치한다.  
> 
> EC2(Amazon Linux) 에 에이전트 설치 및 실행  
> ```shell
> yum -y update
> yum install -y ruby
> cd /home/ec2-user
> curl -O https://aws-codedeploy-us-east-2.s3.us-east-2.amazonaws.com/latest/install
> chmod +x ./install
> sudo ./install auto
> ```
> 실행 확인: `sudo service codedeploy-agent status`

### 구성 요소
> **애플리케이션(Application)**  
> 애플리케이션 이름: 이름은 유니크해야한다.  
> 컴퓨팅 플랫폼: 배포될 컴퓨터의 플랫폼을 지정한다. 온프레미스 서버/EC2 인스턴스, 서버리스(람다), Amazon ECS(Docker)를 지원한다.
>
> **배포 구성(Deployment configuration)**  
> 배포의 성공/실패 여부를 결정하기 위한 룰을 정의한다.  
> 컴퓨팅 플랫폼에 따라 다른 룰이 올 수 있다.  
> 일단 `EC2/온프레미스`를 예로 들면 룰은 `최소 정상 호스트`가 있다. 최소 정상 호스트는 숫자 혹은 백분율로 지정할 수 있으며,
> 숫자는 말 그대로 배포 과정에서 healthy 한 호스트가 몇 개가 되었을 때 정상적으로 배포되었는지 판단하는 기준이 되며,
> 백분율은 정해진 퍼센트의 인스턴스들이 healthy 한 상태가 되었을 때 정상적으로 배포되었는지 판단하는 기준이된다.
>
> **배포 그룹(Deployment group)**  
> EC2 인스턴스들에 태그를 붙여놓은 논리적(logical) 그룹이다.  
> 배포 그룹에는 EC2 인스턴스 1개 혹은 Auto scailing 그룹이 올 수 있다.  
> 
> 배포 그룹 이름: 배포 그룹의 이름을 지정한다.  
> 서비스 역할(IAM Instance profile)  
> AWS EC2 인스턴스에 배포 작업을 하기 위해서는 Amazon S3 버킷에 접근하여 artifect 를 가져올 수 있어야하고,
> Github 이나 CodeCommit 과 같은 소스코드 리포지토리에 접근하여 빌드할 소스코드를 가져올 수 있어야하고,
> 배포 과정에서 신규 EC2 인스턴스를 생성할 수 있어야한다.  
> CodeDeploy 에서 위의 작업들을 수행하기 위해서는 IAM Role 이 필요하다. IAM 에서 사용 사례 선택에 CodeDeploy 를 선택하여 만든 역할을 연결한다.
> (없으면 IAM 에서 직접 새로 만들어야한다.)   
> 만약 배포 플랫폼이 서버리스 람다 혹은 ECS(Docker) 인 경우 IAM Role 은 불필요하다.
>
> 배포 유형(Deployment type)  
> 현재 위치(In-place deployment): EC2 인스턴스 자체를 종료하고 새로 만드는 것이 아닌 기존에 실행 중인 EC2 인스턴스 내부의 애플리케이션만 교체하는 방식이다.   
> 기존 실행 중이던 애플리케이션은 종료하고 새롭게 배포된 애플리케이션을 배포/설치 및 실행 후 검증한다.  
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
> Revision  
> Revision 은 수정된 컨텐츠의 묶음을 의미한다.  
> 빌드 완료된 artifact, 웹 페이지들, 실행 파일들, 배포 스크립트 및 AppSpec 파일이 될 수 있다.
> AppSpec 파일은 yml 혹은 JSON 파일로 작성이 가능하다.  
> EC2/온프레미스 플랫폼에서 AppSpec 파일이 요구되며 AppSpec 파일을 통해 소스 파일이 배포되거나 스크립트를 실행시킨다.  
> 
> 주의 사항   
> 배포 그룹에서 최소 healthy 인스턴스 수를 계산할 때 stop 된 인스턴스는 failed 로 인식된다.  
> 너무 많은 인스턴스를 stop 시켜서 최소 healthy 인스턴스 수보다 적어지면 배포가 실패로 종료될 수 있다.  

### 비용
> 2023-04-19 기준   
> AWS CodeDeploy 를 통해 Amazon EC2, AWS Lambda 또는 Amazon ECS에 코드를 배포하는 데는 추가 비용이 부과되지 않습니다.  
> 온프레미스에 CodeDeploy를 사용하는 경우: AWS CodeDeploy를 사용해 온프레미스 인스턴스를 업데이트하는 경우에는 업데이트당 `0.02 USD`의 요금이 부과됩니다. 
> 최소 요금 및 사전 약정은 없습니다. 예를 들어 인스턴스 3개에 대한 배포는 인스턴스 업데이트 3회와 동일합니다. 
> CodeDeploy에서 인스턴스를 업데이트하는 경우에만 요금이 부과됩니다. 배포가 진행되지 않은 인스턴스에 대해서는 요금이 부과되지 않습니다.

### 참조사이트
> [CICD - Codedeploy란? (Codedeploy를 이용한 자동배포(CD) 환경 구축하기)](https://galid1.tistory.com/745)

---

## CodePipeline
### 개요
> CodePipeline 은 프로그램의 소스 코드, 빌드, 테스트, 배포 의 전반을 관리한다.  

### 고수준 구성
> Source -> Build -> Staging -> Manual Approval -> Production
> 
> **Source**  
> 개발자가 외부 저장소(remote repository) 에 소스코드를 커밋(commit)하면 정해진 CodePipeline 의 사이클이 시작된다.     
> 
> **Build**  
> CodePipeline 이 소스코드의 변경이 commit 됨을 즉시 그리고 자동으로 알아차려 테스트 및 코드를 컴파일하여 Artifact(빌드 결과물)을 생성한다.  
> 
> **Staging**  
> 앞에서 빌드된 Artifact 를 staging 환경에 배포한다. 이를 통해 성능 테스트(load test) 및 통합 테스트(integration test) 를 개발자 및 테스터가 진행할 수 있게된다.  
> 
> **Manual Approval**  
> 운영 환경(production environment) 에 즉시, 자동 배포 이전에 사람의 개입이 필요하다. 
> 모든 테스트가 완료되어 문제가 없는지 Staging 레벨에서 통과 및 운영 환경에 배포하는 비즈니스 적 요구 시점에 배포하는 것이 필요하기 때문에 그전에 운영환경에 배포되는 것을
> 막을 필요가 있다.
> 
> **Production**  
> 운영환경에 배포하기로 결정이 되었으면 Manual Approval 를 통과시키면 CodeDeploy 를 통해서 운영 환경에 Artifact 를 배포한다.
>
> **Again**  
> 운영환경 배포 이후 테스트를 통해서 버그를 찾고 개발자가 코드를 수정하여 외부 저장소에 소스코드를 커밋하여 위의 Source 단계부터 다시 시작한다.  

### 각 스테이지 별 input/output
> AWS CodePipeline 은 각 스테이지 별로 Artifact 를 input 및 output 하게 된다.  
> 해당 Artifact 는 Amazon S3 의 버킷에 저장하게 되며 해당 버킷을 artifact 버킷이라고 부른다.   
> 파이프라인 생성 시 고급 설정에서 기본 위치를 선택하여 버킷을 생성하거나 기존에 생성된 버킷을 artifact 버킷으로 사용할 수 있다.  

### CI(Continuous Integration) with AWS CodePipeline
> Build 스테이지를 통해서 빌드 및 테스트를 통한 검증할 수 있다. CI 는 지속적으로 커밋된 코드를 빌드하고 테스트하는 것에 집중한다.  

### CD(Continuous Delivery) with AWS CodePipeline
> 신규 릴리즈 프로세스를 자동화한다는 용어. 모든 스테이지는 자동화된다. 빌드, 테스트 및 운영 환경 배포까지.

--- 

## CI/CD
### CI
> 소스코드의 commit 들을 merge 하고 빌드(단위테스트)하는 것까지는 CI 라고 한다.  
> 이전의 소프트웨어 개발에서는 개발의 마지막 사이클에 모든 커밋들을 merge 하였었다. 
> 하지만 보다 자주 코드를 커밋하고 merge 하는 것이 merge 하면서 발생한 conflict 들을 인지하고 처리하는 것에 더 용이하기 때문에 
> 더 자주 코드를 커밋하고 merge 한다.  
> 
> **신규 merge 코드 퀄리티 체크**  
> 1.코드 퀄리티 스캔 및 신규 코드가 엔터프라이즈 코드 스탠다드에 맞는지 확인한다.  
> 2.코드를 빌드하고 자동화된 테스트들을 실행한다.

### CD
> CD 는 CI 의 다음 단계이다. CD 는 애플리케이션을 test 부터 프리 프로덕션 환경까지의 다양한 환경에 배포한다.  
> CD 는 프로덕션 환경으로는 자동으로 배포하지 않는다.  
> 
> **Continuous Delivery**  
> 프로덕션 환경을 제외한 모든 배포 과정을 자동화한다.  
> 다만 프로덕션 환경에 배포하는 것은 사용자의 수동 허가(Manual approval)를 요구한다.  
> 
> **Continuous Deployment**  
> 프로덕션 환경을 포함한 모든 배포 과정을 자동화한다.  
