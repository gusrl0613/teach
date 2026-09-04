# teach

수원 영덕초 초등교사 연수 — 노션 · 클로드.

Vercel 정적 배포용 저장소. 루트가 그대로 서빙된다.

## 다섯 페이지

상단 탭으로 오간다. 탭은 다섯 페이지가 **완전히 같은 모양**을 쓴다
(페이지 팔레트와 무관하게 자기 색을 따로 갖는다).

| 경로 | 무엇 |
|---|---|
| `index.html` | **교안** — 강의 슬라이드 26장. `←` `→` 이동, `N` 해설, `Esc` 목차 |
| `skills.html` | **스킬** — 교사용 스킬 20종. 예시 프롬프트 복사, `SKILL.md` 전문 복사, zip 내려받기 |
| `cowork.html` | **코워크** — 시켜놓고 딴 일 하기. 채팅과 뭐가 다른지부터 |
| `plugins.html` | **플러그인** — 여럿을 한 묶음으로. `teacher-pack` 설치법 |
| `connectors.html` | **커넥터** — 드라이브·지메일·캘린더·노션 연결 |

탭 링크는 세 군데 모두에서 동작한다. 배포 사이트와 로컬에서는 상대 경로로,
형제 파일이 없는 클로드 아티팩트에서는 아티팩트 주소로 자동 전환된다.

## 스킬 20종

`skills/<이름>/SKILL.md` 가 원본, `skills/<이름>.zip` 이 claude.ai 업로드용.
스무 개를 한 번에 넣으려면 아래 `teacher-pack` 플러그인을 쓴다.

| 분류 | 스킬 |
|---|---|
| **안내·문서** (6) | `home-letter` 가정통신문 · `weekly-plan` 주간학습안내 · `daily-note` 알림장 · `school-doc` 공문·계획서 · `notice-digest` 공문 간추리기 · `meeting-note` 회의 정리 |
| **수업** (6) | `lesson-design` 수업 설계 · `worksheet` 학습지 · `assessment` 평가문항 · `explain-simply` 눈높이 설명 · `read-level` 읽기 자료 조정 · `writing-feedback` 글쓰기 피드백 |
| **학급 운영** (5) | `class-setup` 학급 세우기 · `seating-chart` 자리배치 · `conflict-talk` 갈등 중재 · `praise-note` 칭찬·격려 · `event-plan` 행사 기획 |
| **학부모** (2) | `parent-message` 학부모 답장 · `counsel-prep` 상담 준비 |
| **기록** (1) | `record-phrase` 생기부 문구 |

스무 개 모두 같은 세 문장을 지킨다.

> 학생 실명은 넣지 않는다 · 모르는 것은 지어내지 않는다 · AI는 초안을 쓰고 판단은 교사가 한다

각 스킬은 **서로 다른 위험 하나씩**을 막는다. 무엇을 막는지는 `skills.html` 카드의 빨간 칸에 있다.

### claude.ai 에 올리기

1. 설정 → 기능 → **“코드 실행 및 파일 생성”** 켜기
2. Customize → Skills → `+` → 스킬 업로드 → zip 선택 (한 번에 하나씩)

커스텀 스킬 업로드는 **Pro 이상**이다. 무료 계정은 `SKILL.md` 본문을 프로젝트 지침에 붙여 쓴다.
자세한 사용법은 [`skills/사용법.md`](skills/사용법.md).


## teacher-pack — 플러그인

같은 스킬 20종을 하나로 묶었다. 플러그인은 **claude.ai 채팅에서도** 쓴다 (모든 유료 플랜).

| 상황 | 방법 |
|---|---|
| 혼자 · Pro | claude.ai `Customize → Plugins → Personal plugins → +` → `gusrl0613/teach` |
| 학교 배포 · Team/Enterprise 소유자 | `조직 설정 → 플러그인 → Upload a file` 에 `teacher-pack.zip` (50 MB 이하) |
| 클로드 코드 | 아래 두 줄 |

```
/plugin marketplace add gusrl0613/teach
/plugin install teacher-pack@teach
```

- `.claude-plugin/marketplace.json` — 마켓플레이스 카탈로그
- `plugins/teacher-pack/` — 플러그인 본체 (`plugin.json` + 스킬 20종)

저장소가 공개라 **깃허브 계정 없이 누구나** 설치된다.
깃이 없거나 파일로 건네야 하면 `teacher-pack.zip` 을 쓴다 —
`claude --plugin-dir teacher-pack.zip` 또는
`claude --plugin-url https://raw.githubusercontent.com/gusrl0613/teach/main/teacher-pack.zip`

## 원본

`secondbrain/teaching/2026_초등교사_노션_클로드/` — 설계·사전안내문·강사대본·실습폴더가 함께 있다.
