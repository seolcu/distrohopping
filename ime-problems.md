# IME들의 문제점

## 환경변수 정리

- `GTK_IM_MODULE=(IME)`: GTK 입력 담당
- `QT_IM_MODULE=(IME)`: QT 입력 담당
- `XMODIFIER=@im=(IME)`: X 또는 XWayland 담당

위 세 변수만 잘 설정되어도 대부분의 문제 해결

## 일반적인 팁

- `~/.bash_profile` 에 넣는 게 일반적이다.
- KDE에서 Fcitx5 사용시 kcm이 설치되어 있지 않다면 설치하면 좋다
- NixOS에서는 환경변수를 따로 설정할 필요 없이, 위키 따라서 enable만 해주면 됨.
- Fedora는 im-chooser가 설치되어 있으므로, XMODIFIERS 환경변수를 따로 지정하는 대신 "입력 방식" 프로그램으로 ime를 선택한다. 또는 im-chooser를 삭제하자.

## IBus

- GNOME 아니면 소고 로고 생김
- KDE의 시작버튼?에서 한글입력 안됨
- KDE에서 GTK_IM_MODULE이랑 QT_IM_MODULE unset하라고 알림뜸 (프로토콜 미스매치?)

## Fcitx5

- 한글모드로 바꿀때마다 Korean이라고 툴바가 뜸(끄는법: 전역 옵션 -> 입력기 변경시 입력기 정보 표시 체크해제하기. 요즘엔 이게 편해서 그냥 켜고 쓰는중)
- KDE, 전체적으로 다 고쳐진건지 현재 openSUSE만 고쳐진건지 모르겠지만 GTK_IM_MODULE이랑 QT_IM_MODULE을 꺼야 오히려 터미널에서 한글입력이 가능함

## Kime

- 짱인데 설치가 어려운게 단점이었는데...
- 이젠 설치까지 쉬워진 고트 그자체 감사합니다
