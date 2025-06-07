# 브랜치 전략 (Git Flow 간소화)

## 주요 브랜치
- `main`: 배포 가능한 안정 버전
- `dev`: 개발 통합 브랜치
- `feature/*`: 각 기능별 작업 브랜치 (예: feature/robot-control)

## 작업 흐름
1. 기능 작업은 feature/* 브랜치에서 진행
2. 작업 완료 후 dev 브랜치로 Pull Request 생성
3. dev에서 테스트 후 main으로 병합

## 브랜치 이름 규칙
- `feature/기능명`: 새 기능 개발
