# AWS IDP

AWS에서 IDP 솔루션의 deploy 및 테스트 방법에 대해 설명합니다.

## 특징

- [Paddle OCR](https://github.com/PaddlePaddle/PaddleOCR) 활용하여 Lambda로 배포하여 경제적입니다. (CPU로 구동 가능)

### Build 

1. 전제조건 확인 — node, pnpm, cdk, python3, uv, aws CLI가 설치되어 있는지 검사하고, 없으면 자동 설치
2. 의존성 설치 — pnpm install --frozen-lockfile 실행 (.python-version 파일도 자동 수정)
3. 빌드 — pnpm nx run-many -t lint,compile,test,bundle -p @idp-v2/infra @idp-v2/frontend
4. CDK 배포 — CDKToolkit 부트스트랩 확인 후 cdk deploy 실행
5. 후처리 — Cognito 관리자 계정 생성 및 배포 URL 출력


[Sample AWS IDP Pipeline](https://aws-samples.github.io/sample-aws-idp-pipeline/ko/)를 이용해 설치합니다.
