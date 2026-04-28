# 🚀 프로젝트 개요: Node.js & Jenkins CI/CD 파이프라인 예제

이 프로젝트는 **Node.js 애플리케이션**을 Jenkins 서버와 연동하여, 자동화된 **Jenkins Pipeline**을 통해 도커(Docker) 이미지를 빌드하고 **Docker Hub에 배포(Push)**하는 CI/CD(지속적 통합/지속적 배포) 예제입니다.

## 📌 주요 특징
* **파이프라인 스크립트**: 프로젝트 내 `misc/Jenkinsfile`을 사용하여 Jenkins 파이프라인을 구성합니다.
* **자동화된 빌드 및 배포**: 소스 코드 체크아웃부터 테스트, 도커 이미지 생성 및 레지스트리 업로드까지 전 과정이 코드로 자동화되어 있습니다.
* **동적 태깅(Tagging)**: Git의 커밋 해시(Commit ID)를 추출하여 도커 이미지의 고유한 태그(버전)로 사용합니다.

## 🛠️ 파이프라인 작업 흐름 (Pipeline Workflow)
1. **Preparation (준비)** 
   * Git 저장소에서 최신 소스 코드를 가져옵니다. (`checkout scm`)
   * 이미지 태그로 사용할 Git 커밋 ID를 추출합니다.
2. **Test (테스트)** 
   * Node.js 환경에서 의존성 패키지를 설치(`npm install`)하고, 애플리케이션 테스트(`npm test`)를 수행합니다.
3. **Docker Build & Push (빌드 및 배포)** 
   * 프로젝트 루트 디렉토리의 `Dockerfile`을 기반으로 도커 이미지를 빌드합니다.
   * 완성된 이미지를 Docker Hub 레지스트리에 안전하게 업로드(Push)합니다.

## 💻 기술 스택 (Tech Stack)
* **Application**: Node.js
* **CI/CD**: Jenkins (Pipeline)
* **Containerization**: Docker
* **Registry**: Docker Hub
* **VCS**: Git / GitHub
