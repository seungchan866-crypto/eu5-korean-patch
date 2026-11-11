[README_KO.md](https://github.com/user-attachments/files/34661130/README_KO.md)
# EU5 1.4.8 테스트 브랜치 한글 입력 패치

Windows Steam 테스트 브랜치 `1.4.8-testing-branch`, 빌드 `26547371`용 비공식 패처입니다.

한글 조합 종료 처리를 수정해 글자가 잘못 조합되거나 Backspace로 지워지지 않는 문제를 해결합니다. 수정 대상은 설치 폴더의 `binaries/eu5.exe`입니다. 생산 화면과 공용 건물 툴팁이 Steam 원본인 파일 구성에서도 적용과 복원을 검증했습니다.

## 사용법

1. ZIP을 풀고 게임을 완전히 종료합니다.
2. `EU5-Korean-IME-Patcher.exe`를 열면 Steam 라이브러리에서 설치 경로를 자동으로 찾습니다. 표시된 경로를 확인하고 **1**을 선택합니다. 지원 빌드가 여러 곳에 있으면 먼저 목록에서 경로를 선택합니다. 쓰기 권한 오류가 나오면 관리자 권한으로 실행합니다.
3. Steam 라이브러리에서 게임을 실행합니다. 지점 검색창에서 `카스티야`를 직접 입력하고 Backspace로 전부 지워 확인합니다.
4. 원본으로 복원하려면 게임을 종료하고 패처에서 **2**를 선택합니다.

다른 드라이브에 등록된 Steam 라이브러리도 자동으로 탐색합니다. 설치 경로를 직접 지정하려면 압축을 푼 폴더에서 PowerShell을 열고, 아래 예시의 경로를 Steam의 **설치된 파일 찾아보기**에서 열리는 경로로 바꿔 실행합니다.

```powershell
.\EU5-Korean-IME-Patcher.exe apply --game-dir "D:\SteamLibrary\steamapps\common\Europa Universalis V"
.\EU5-Korean-IME-Patcher.exe restore --game-dir "D:\SteamLibrary\steamapps\common\Europa Universalis V"
```

패처는 Steam 빌드와 실행 파일 해시를 확인한 뒤 적용하거나 복원합니다. `EU5KoreanImePatcher.cs`는 패처 소스이며 `SHA256SUMS.txt`에서 파일 해시를 확인할 수 있습니다.

## 검증 범위

1.4.8에서 `카스티야` 직접 입력과 Backspace 삭제를 게임 화면에서 확인했습니다. 그 실행에는 이전 툴팁 수정이 들어 있었고, Steam 원본 툴팁을 사용한 별도 시험에서는 실행 파일의 적용·복원과 두 원본 GUI의 해시를 확인했습니다.
