# GA4 실습용 랜딩페이지

성동 SESAC 6기 공용 틀입니다. 노란 칸을 내 브랜드로 채우고, Day 34에 GA4를 붙입니다.

## 1. 내 브랜드로 채우기 (Codex)

Codex에 아래처럼 요청하세요.

> 모든 파일에서 YOUR-GITHUB-ID를 내아이디로 바꿔줘.
> index.html의 노란 표시(class="todo") 칸을 아래 내 브랜드 정보로 채우고 노란 표시는 없애줘. title과 description, og 태그도 같이 바꿔줘.
> (브랜드명, 타깃, 핵심 문장, 장점 3개, 혜택, FAQ 3개, CTA 문구)

브랜드 색은 index.html과 result.html 맨 위 `--primary`, `--accent` 값을 바꿉니다. 대표 이미지는 `assets/hero.jpg`로 올리고 "대표 이미지 자리를 assets/hero.jpg로 바꿔줘"라고 요청합니다.

## 2. GA4 붙이기 (Day 34)

1. GA4 관리 → 데이터 스트림 → 웹 → 주소 `https://내아이디.github.io/` → 측정 ID(G-로 시작) 확인
2. 태그 안내 → 직접 설치의 Google 태그 코드를 복사
3. index.html과 result.html의 `<!-- GA4 ... -->` 줄 바로 아래에 붙여 넣기 (Codex에 "이 GA4 코드를 두 파일 head의 GA4 주석 아래에 넣어줘")
4. index.html 개인정보 팝업의 "익명 방문 통계" 줄 주석을 풀기

## 3. 이미 심어 둔 이벤트

GA4 코드만 붙이면 아래 이벤트가 자동으로 들어옵니다.

| 이벤트 | 언제 | 파라미터 |
|---|---|---|
| `cta_click` | 신청 버튼(헤더·첫 화면·혜택)을 누를 때 | `location` = header / hero / offer |
| `nav_click`, `more_click`, `faq_open` | 메뉴, 자세히 보기, FAQ를 누를 때 | `location` |
| `generate_lead` | 신청 폼 제출 후 동의까지 눌렀을 때 | |
| `page_view` (result.html) | 신청 완료 페이지가 열릴 때 | |

전환(주요 이벤트)으로는 `generate_lead`를 표시하는 것을 권합니다. 확인은 GA4 관리 → DebugView 또는 실시간 보고서에서 합니다.

## 바꾸면 안 되는 것

- `id="cta-main"`, `id="lead-form"`, `id="cta-submit"`, `data-ga` 속성
- `assets/privacy.js`, `assets/track.js`
- 푸터의 "수업 실습용 페이지" 문구
