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


## hyend-physical 팀별 Git 기본 명령어 가이드

아래는 hyend-physical 프로젝트의 각 팀(폴더)별로 처음 Git을 사용하는 분들도 쉽게 따라할 수 있도록 정리한 Git 명령어 안내입니다.  
모든 팀원이 프로젝트 협업에 원활하게 참여할 수 있도록, **기본 명령어부터 실전 협업에 필요한 브랜치, 커밋, 병합, 충돌 해결까지** 단계별로 설명합니다.  

---

### 1. 공통: Git 시작하기

**1) Git 설치**
- Windows: [Git 공식 다운로드](https://git-scm.com/download/win)
- Mac: 터미널에서 `brew install git`
- Linux: 터미널에서 `sudo apt-get install git`

**2) 사용자 정보 등록**
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
```

**3) 프로젝트 클론**
```bash
git clone https://github.com/lico4268/hyend-physical.git
cd hyend-physical
```

---

### 2. 팀별 폴더 안내

- **robot-control**: 로봇 하드웨어 및 이동 로직
- **web**: 제어용 웹 UI
- **ai**: AI API 연동(음성/이미지 등)

각 팀은 해당 폴더에서 작업을 진행합니다.

---

### 3. 기본 명령어

**1) 변경 사항 확인**
```bash
git status
```

**2) 파일 추가 및 커밋**
```bash
git add 파일명      # 예: git add main.py
git commit -m "설명 메시지"
```

**3) 변경사항 원격 저장소로 보내기**
```bash
git push origin 브랜치명
```

**4) 최신 코드 가져오기**
```bash
git pull origin 브랜치명
```

---

### 4. 브랜치 전략 및 협업

**1) 브랜치 생성 및 이동**
```bash
git checkout -b 브랜치명   # 새 브랜치 생성 후 이동
```
- 각 팀별로 `feature/robot-control/`, `feature/web/`, `feature/ai/` 하위에서 자신의 작업 브랜치를 만들어 사용하세요.

**2) 브랜치 목록 확인**
```bash
git branch
```

**3) 브랜치 전환**
```bash
git checkout 브랜치명
```

---

### 5. 협업 시 유용한 명령어

**1) 커밋 내역 확인**
```bash
git log
```

**2) 특정 파일 변경 사항 보기**
```bash
git diff 파일명
```

**3) 병합(merge)**
- 예: `feature` 브랜치 작업을 `main`에 병합할 때
```bash
git checkout main
git pull origin main
git merge feature
git push origin main
```

**4) 충돌 해결**
- 충돌이 발생하면, 파일을 직접 수정한 후
```bash
git add 충돌해결된파일
git commit
git push origin 브랜치명
```

---

### 6. 실수했을 때

**1) 최근 커밋 취소(수정 후 다시 커밋)**
```bash
git reset --soft HEAD~1
```

**2) 워킹 디렉토리 변경 취소**
```bash
git checkout -- 파일명
```

---

### 7. 참고 사항

- **최대한 자주 pull/push 하여 동기화**하세요.
- **커밋 메시지는 명확하게** 작성하세요. 예: "로봇 전진 기능 추가", "UI 버튼 디자인 개선"
- **불필요한 파일은 .gitignore에 등록**하세요.

---

**이 가이드는 hyend-physical의 실제 폴더 구조와 협업 환경, 그리고 Git 초보자를 위한 친절한 설명을 반영하여 작성되었습니다.** 
