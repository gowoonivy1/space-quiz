# 🚀 Space Exploration Quiz (우주 탐사 퀴즈)

미션 컨트롤(Mission-Control) HUD 테마의 한/영 이중 언어 우주 탐사 퀴즈 웹 애플리케이션입니다. 외부 의존성이나 빌드 과정 없이 단일 `index.html` 파일로 동작합니다.

🌐 **Live Demo:** [https://gowoonivy1.github.io/space-quiz/](https://gowoonivy1.github.io/space-quiz/)

## ✨ 주요 기능 (Features)

- **10개의 우주 탐사 퀴즈**: 보이저 1호, 아폴로 11호, 제임스 웹 우주망원경 등 인류 우주 탐사 역사를 다루는 10문항과 상세 해설 제공
- **한/영 실시간 전환 (Bilingual Support)**: 진행 중인 점수와 문제 상태를 유지한 채 한국어(`한국어`)와 영어(`EN`)를 즉시 전환 가능
- **연속 정답 & 최고 기록 추적**: 실시간 스트릭(Streak) 배지 표시 및 `localStorage` 기반 최고 점수 저장
- **미션 컨트롤 HUD 디자인**: 시스템 라이트/다크 모드 자동 대응 및 키보드 단축키 완벽 지원 (`1`–`4`, `A`–`D`, 방향키, `Enter`/`Space`)

## 🛠️ 로컬 실행 방법 (How to Run Locally)

별도의 패키지 설치나 빌드 도구가 필요하지 않습니다.

### 1. 파일 직접 열기
리포지토리를 클론한 뒤 브라우저에서 `index.html` 파일을 바로 엽니다.

```bash
git clone https://github.com/gowoonivy1/space-quiz.git
cd space-quiz
open index.html
```

### 2. 로컬 웹 서버로 실행 (선택 사항)
로컬 정적 서버를 사용해 실행할 수도 있습니다.

```bash
python3 -m http.server 8000
```
그 후 브라우저에서 `http://localhost:8000`에 접속합니다.
