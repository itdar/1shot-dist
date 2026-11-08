# 시험 결과

## 0.8.20 보안 수정 확인 (2026-11-08)

| 시험 | 결과 |
|---|---|
| 서명 요구 조건 (`codesign -R`로 같은 문자열 확인) | Chrome(EQHXZ8M8AV), Edge(UBF8T346G9), Battle.net(G847MC6JZ5), Mac App Store 앱(Amphetamine): 통과. 다른 팀 ID: 거부. TextEdit: `anchor apple` 통과 |
| 자체 서명한 가짜 앱 | 시험하지 못했습니다 |
| 단위 테스트 (포트, 실행 옵션 대시 개수, 대소문자) | 통과 |
| `auth: biometric/password` 입력 | 사람 시험 대기 |

## 결과 (2026-11-05, macOS 26.5.1)

| 시험 | 결과 |
|---|---|
| 단위 테스트 10개 (도메인 비교, 설정 검사) | 통과 |
| Chrome 로컬 로그인 페이지: 아이디와 비밀번호 | 통과. 서버가 받은 값이 정확합니다 (특수문자, 한글, é 포함) |
| Safari 로컬 로그인 페이지 | 통과 |
| macOS 기본 비밀번호 창(NSSecureTextField) | 통과 |
| TextEdit (번들 ID로 일치) | 통과 |
| 다른 도메인 / 다른 앱 / 칸 종류가 틀림 | 입력하지 않고 `fail` |
| `security find-generic-password -w`로 직접 읽기 | 막힘 (키체인 암호 창) |
| 다시 빌드한 뒤 읽기 | 확인 창 없이 읽힘 (같은 인증서) |
| Battle.net 앱 (CEF) | 통과 (가짜 비밀번호, 제출 안 함). 앱 + 도메인 `account.battle.net`으로 일치합니다. 칸 종류를 알려 주지 않으므로 `field_check: false`가 필요합니다 |
| 네이버 로그인 (Chrome) | 통과 (가짜 값, 제출 안 함). Tab이 버튼으로 가자 비밀번호 입력을 거부했습니다 |
| 전역 단축키 (Chrome 로컬 페이지) | 통과. ⌃⌥⌘U, ⌃⌥⌘P로 정확히 입력됩니다. 맞는 항목이 없으면 `fail`과 경고음. 단축키를 바꾸면 새 단축키로 동작합니다 |
| 직접 다운로드 (dmg) | 통과. 첫 실행은 Gatekeeper가 막습니다. 허용 후 앱이 CLI 격리를 지우고, 명령줄 도구 설치 버튼이 동작합니다 |
| `auth: biometric/password` | 시험하지 못했습니다. 사람의 지문이 필요합니다 |
| `brew install --cask` (로컬 tap) | 통과. 앱과 `1shot` 명령이 설치되고, Gatekeeper가 막지 않습니다 |
| UI: 항목 수정, 저장, 비밀번호 저장, 그 뒤 Chrome에 입력 | 통과 |
| 개인정보 `info auto` (Safari, Chrome 로컬 한국어 양식 15칸) | 통과. 성명, 휴대폰 3칸(목록 + 텍스트 2칸), `[년] [월] [일]` 목록 3개, 주민번호 앞·뒤(비밀번호 칸), 학력 목록, 성별 라디오, 동의 체크 박스, 이메일, `YYYY.MM.DD` 한 칸 생일. 검색 칸은 맞는 항목이 없어 입력하지 않음 |
| 개인정보 날짜 선택기(`type=date`) | 지원하지 않음. 두 브라우저 모두 키 입력 결과가 일정하지 않았습니다. `fail`을 돌려줍니다 |
| 브라우저가 알려 주는 칸 정보 (Safari, Chrome) | 이름표, `aria-label`, `title`, placeholder, 요소 id, 앞의 글자, `legend`는 읽힘. `autocomplete`, `name`, `maxlength`, `type=tel`은 읽히지 않음 |

