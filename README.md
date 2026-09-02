# teach

수원 영덕초 초등교사 연수 — 노션 · 클로드.

Vercel 정적 배포용 저장소. 루트가 그대로 서빙된다.

## 다섯 페이지

상단 탭으로 오간다. 탭은 다섯 페이지가 **완전히 같은 모양**을 쓴다
(페이지 팔레트와 무관하게 자기 색을 따로 갖는다).

| 경로 | 무엇 |
|---|---|
| `index.html` | **교안** — 강의 슬라이드 26장. `←` `→` 이동, `N` 해설, `Esc` 목차 |
| `skills.html` | **스킬** — 교사용 스킬 10종. 예시 프롬프트 복사, `SKILL.md` 전문 복사, zip 내려받기 |
| `cowork.html` | **코워크** — 시켜놓고 딴 일 하기. 채팅과 뭐가 다른지부터 |
| `plugins.html` | **플러그인** — 여럿을 한 묶음으로. `teacher-pack` 설치법 |
| `connectors.html` | **커넥터** — 드라이브·지메일·캘린더·노션 연결 |

탭 링크는 세 군데 모두에서 동작한다. 배포 사이트와 로컬에서는 상대 경로로,
형제 파일이 없는 클로드 아티팩트에서는 아티팩트 주소로 자동 전환된다.

## 스킬 10종

`skills/<이름>/SKILL.md` 가 원본, `skills/<이름>.zip` 이 claude.ai 업로드용.

| 언제 | 이름 | 무엇을 막아주나 |
|---|---|---|
| 매주 | `weekly-plan` | 진도를 지어내는 것 |
| 수시 | `home-letter` | 모르는 날짜·금액을 지어내는 것 |
| 수시 | `lesson-design` | 40분에 안 맞는 활동, 비현실적 준비물 |
| 학기 중 | `assessment` | 성취기준 코드를 지어내는 것 |
| 상시 | `writing-feedback` | 아이 글을 대신 고쳐주는 것 |
| 월 1회 | `seating-chart` | 조건 충돌을 조용히 넘기는 것 |
| 주기적 | `school-doc` | 근거 법령·조항을 지어내는 것 |
| 수시 | `parent-message` | “절대·다시는·반드시” |
| 상담 주간 | `counsel-prep` | 상담 중에 흐려지는 판단 |
| 학기말 | `record-phrase` | 근거 없이 지어내는 것 |

열 개 모두 같은 세 문장을 지킨다.

> 학생 실명은 넣지 않는다 · 모르는 것은 지어내지 않는다 · AI는 초안을 쓰고 판단은 교사가 한다

### claude.ai 에 올리기

1. 설정 → 기능 → **“코드 실행 및 파일 생성”** 켜기
2. Customize → Skills → `+` → 스킬 업로드 → zip 선택 (한 번에 하나씩)

커스텀 스킬 업로드는 **Pro 이상**이다. 무료 계정은 `SKILL.md` 본문을 프로젝트 지침에 붙여 쓴다.
자세한 사용법은 [`skills/사용법.md`](skills/사용법.md).

## teacher-pack — 클로드 코드용 플러그인

같은 스킬 10종을 하나로 묶었다. 여러 선생님께 나눠줄 때 쓴다.

```
/plugin marketplace add gusrl0613/teach
/plugin install teacher-pack@teach
```

- `.claude-plugin/marketplace.json` — 마켓플레이스 카탈로그
- `plugins/teacher-pack/` — 플러그인 본체 (`plugin.json` + 스킬 10종)

저장소가 비공개라 접근 권한이 있어야 설치된다.

## 원본

`secondbrain/teaching/2026_초등교사_노션_클로드/` — 설계·사전안내문·강사대본·실습폴더가 함께 있다.
