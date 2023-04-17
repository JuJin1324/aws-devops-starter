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
> ```yaml
> version: 0.2
> phases:
>   build:
>     commands:
>       - echo Build Starting on `date`
>       - chmod +x ./gradlew
>       - ./gradlew bootJar
>   post_build:
>     commands:
>       - echo $(basename ./build/libs/*.jar)
>       - pwd
> artifacts:
>   files:
>     - build/libs/*.jar
>   discard-paths: yes
> ```

### Jenkins 플러그인
> TODO

### 비용
> 2023-04-13 기준   
> general1.small(2 vCPU, 3GB): 0.005 USD  

---

## CodeDeploy
### TODO
> 

---

## CodePipeline
### 개요
> CodePipeline 은 프로그램의 소스 코드, 빌드, 테스트, 배포 의 전반을 관리한다.  
> 그 중 빌드, 테스트를 CodeBuild 를 사용한다.  

--- 

## CI/CD
### CI
> TODO

### CD
> TODO
