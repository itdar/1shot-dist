# 개인정보 처리방침 (Privacy Policy)

> **Summary (English):** 1shot collects no personal data. It has no account, no analytics and no server. Your entries and passwords stay on your device (and in your own sync folder if you turn sync on). The only network request is an optional update check to the GitHub API.

시행일: 2026-11-05 · 대상: 1shot 앱과 `1shot` 명령줄 도구

## 1. 수집하는 정보

1shot은 개인정보를 수집하지 않습니다.

- 회원 가입, 계정, 로그인이 없습니다.
- 사용 통계, 광고 추적, 오류 보고 전송이 없습니다.
- 개발자가 운영하는 서버가 없습니다.

## 2. 기기에 저장하는 정보

다음 정보는 사용자의 기기에만 저장합니다.

| 정보 | 저장 위치 | 내용 |
|---|---|---|
| 항목 설정 | 공식 릴리스: 앱 전용 키체인 / 소스 빌드: `~/.config/1shot/entries.yaml` | 항목 ID, 대상 앱과 도메인, 아이디 |
| 비밀번호 | 공식 릴리스: 앱 전용 키체인 / 소스 빌드: 로그인 키체인 (서비스 `1shot`) | 사용자가 저장한 비밀번호 |
| 내부 키 | 같은 키체인 (서비스 `1shot.meta`) | 설정 서명 키, 동기화 폴더 경로와 동기화 암호 |
| 앱 설정 | macOS 사용자 기본값 (`dev.gino.1shot.app`) | 단축키, 업데이트 확인 여부, 첫 실행 안내 표시 여부 |

## 3. 외부로 보내는 정보

- **업데이트 확인 (선택):** 하루에 한 번까지 `api.github.com`에 최신 릴리스 정보를 요청합니다. 요청 헤더에는 앱 이름과 버전(`1shot/<버전>`)만 넣습니다. GitHub의 개인정보 처리방침이 적용됩니다. 설정에서 끌 수 있습니다.
- **iCloud 키체인 (선택, 기본 꺼짐):** 켜면 항목과 비밀번호가 Apple의 iCloud 키체인으로 같은 Apple 계정의 기기와 동기화됩니다. Apple의 종단 간 암호화와 개인정보 처리방침이 적용됩니다.
- **기기 간 동기화 (선택):** 사용자가 고른 폴더에 암호화한 보관 파일(`1shot-vault.age`)을 씁니다. 그 폴더가 git 저장소이면 사용자의 git 원격 저장소로 push합니다. 보관 파일은 사용자의 동기화 암호로 암호화(age, scrypt)되어 있습니다. 1shot 개발자는 이 파일에 접근하지 않습니다.
- 그 밖에는 아무것도 보내지 않습니다.

## 4. 화면과 입력 정보

- 1shot은 입력할 때만 손쉬운 사용 API로 맨 앞 앱, 포커스된 칸의 종류, 웹 페이지 주소를 읽습니다. 이 정보는 저장하거나 보내지 않습니다.
- 1shot은 화면을 녹화하거나 키 입력을 기록하지 않습니다.

## 5. 삭제

- 앱의 **설정 > 데이터 > 모든 데이터 삭제**, 또는 `1shot reset`으로 비밀번호, 내부 키, 항목 파일을 모두 지웁니다.
- 앱 설정은 `defaults delete dev.gino.1shot.app`로 지웁니다.
- 동기화 폴더의 보관 파일은 사용자가 직접 지웁니다.

## 6. 변경과 문의

- 이 방침을 바꾸면 이 파일과 릴리스 노트에 적습니다.
- 문의: https://github.com/itdar/1shot-dist/issues
