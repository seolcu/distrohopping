# 배포판들의 문제점

## Debian 계열

### 공통 문제

- 오래된 DE/Compositor 버전
- 오래된 Mesa 버전으로 게이밍에 부적합 (Flatpak을 쓸 수 있지만, 게임 내 한글 입력이 안됨)

### Debian

- 업데이트가 느림 (장점일 수도 있지만 데스크톱에서는 불편함)
- Testing이나 Unstable을 쓸 수 있지만, 일상용으로 의도된 게 아님

### Ubuntu

- Snap 강제 사용
- 일부 버전에서 `.deb` 파일 더블클릭 설치 안됨 (Snap 강제의 일환인듯. 그냥 불편함)
- `apt` 써도 Snap으로 패키지 설치됨 (자유 없는 자유 소프트웨어. 왜?)
- Flatpak 설치하면 앱 스토어가 두 개가 됨
- 업데이트 도구가 여러 개라 뭘 써야 할지 혼란스러움

### Mint

- 메인 DE인 Cinnamon의 Wayland 지원이 실험적임

### Pop!_OS

- Deal-Breaker: 오랫동안 업데이트가 안됨. 아직 개발 중이라고 보는 게 맞음
- COSMIC DE가 아직 개발 단계

---

## Fedora 계열

### 공통 문제

- (AMD만 해당) 시스템 Mesa 드라이버에 h.264/h.265 VA-API 기능 없음 (RPMFusion에서 `mesa-freeworld` 설치 가능하지만 다른 의존성과 꼬여서 부팅 실패나 간헐적 종료 발생 가능. 시스템 Mesa는 그대로 두고 하드웨어 가속이 필요한 건 Flathub 앱 쓰는 게 나음. openSUSE 코덱 문제랑 비슷한 해결책). (Intel, NVIDIA는 해당 없음)
- Firefox에서 유튜브 재생 OOTB 상태로는 별로임
- Hugo 패키지 업데이트가 느림 (Brew로 설치해야 함)
- 패키지 가용성 제한 (starship, virtualbox, ghidra, gamescope-session-steam 등이 메인 레포에 없음)
- RPMFusion에만 있고 Flathub에 없는 패키지(예: Virtualbox) 설치가 꺼려짐
- Copr 레포가 새 Fedora 릴리즈에 뒤처지는 경우 많음
- 6개월 릴리즈 주기가 부담될 때가 있음 (특히 Copr 관련)

### Fedora

- 기본 Fedora Flatpak 리모트는 Flathub이 있으니 쓸모없음 (그냥 지우는 게 나음)
- 데스크톱에서 내장 그래픽 활성화되어 있으면 Steam 실행 실패 (`steamwebhelper` 에러)
- Btrfs 쓰면서도 제대로 된 시스템 롤백이 어려움 (부트 메뉴 옵션이 커널 버전만 다른 거지, 실제 스냅샷 롤백이 아님)
- Flathub 버전 Ghidra에서 한국어 폴더명이 제대로 안 보임

### Nobara

- 설치 과정에서 한국어 선택 옵션 없음
- 기본 홈 폴더명(Documents, Downloads 등)이 영어임. 자동으로 다시 생성되어서 짜증남
- "Games" 폴더가 홈 디렉토리에 바로 있고 숨겨져 있지 않음
- 표준 Fedora보다 릴리즈가 많이 뒤처짐

### Fedora Atomic

- `dnf group` 명령어 사용 불가
- 대부분의 온라인 가이드가 `dnf` 명령어를 쓰기 때문에 패키지 레이어링이 어려움
- Copr 레포 설치하려면 파일을 수동으로 다운받아 `/etc/yum.repos.d`에 넣어야 함
- `rpm-ostree`가 전반적으로 느림
- 사용자를 그룹에 추가할 수 없음
- 내 네트워크에서 미러 연결 안될 때가 많음 (ostree 미러 자체가 다운된 것 같았음, 모바일 핫스팟으로도 안됨)
- Toolbox가 불편함; 컨테이너에서 앱 삭제하고 export하는 게 안됨
- Distrobox가 기본 설치 안됨 (패키지 레이어링 필요)

### Bazzite

- 데스크톱 폴더명이 영어임
- Fedora Atomic과 같은 단점 공유

---

## Arch 계열

### 공통 문제

- 어떤 이유에선지 우리집 네트워크에서 `reflector`가 안됨 (모바일 핫스팟에서는 됨)
- 최근 AUR에서 악성코드 발견됨
- 최근 Arch 인프라가 DDoS 공격 받음
- Secure Boot OOTB 지원 안함

### Arch

- 설치 과정이 복잡함
- 자잘한 버그가 많음
- 초기 설정에 시간이 많이 걸림
- 새 사용자가 모를 수 있는 필수 도구들에 대한 문서가 부족함

### Archinstall

- 그냥 순수 Arch임
- 다른 배포판에 비해 너무 기본적임
- `reflector`가 안되면 무한 로딩에 갇힘

### EndeavourOS

- 불필요한 기본 앱이 있음 (YAD, gtk icon browser 등)
- 경고: 기본 테마를 설치하면 업데이트마다 커스텀 테마를 덮어씀
- 스냅샷은 수동으로 설정해야 함

### Garuda

- 특별한 강점이 없는 마이너 배포판
- 너무 사전 설정되어 있음

### CachyOS

- 개발팀이 작은 매우 새로운 배포판
- 너무 사전 설정되어 있음

### Manjaro (쓰레기)

- Certbot 인증서가 만료됨, 보안과 유지보수에 신경 안 쓴다는 증거
- 의존성 버전 불일치로 AUR 사용 불가
- "그냥 시스템 시간을 바꾸세요" 같은 무책임한 해결책 제시

---

## openSUSE Tumbleweed

- 멀티미디어 코덱 OOTB 제공 안함 (설치할 수 있지만 Packman 레포가 한국에서 매우 느리고, 장기적으로 시스템을 불안정하게 만들 수 있음. Flathub 쓰는 게 나은 해결책. Fedora VA-API 문제와 비슷)
- Fcitx5가 아닌 구버전 Fcitx가 기본으로 옴
- 터미널과 VSCode의 기본 한국어 폰트가 못생겼는데, 지우면 Notion 웹앱이 깨짐
- Sunshine 설치가 어려움 (위키에서 제안하는 Flatpak, Appimage, Homebrew 방법이 openSUSE에서 안됨. OBS의 MaxxedSUSE 패키지만 작동하고, setuid용 라이브러리와 README에 있는 특정 방화벽 설정 필요)
- Deal-Breaker: IDA Free 설치 불가 (8.4, 9.1 둘 다 실제로 설치된 라이브러리가 없다고 실패함. 알 수 없는 버그이고, 표준 레포나 OBS에서도 프로그램을 구할 수 없음)
- `pwntools`가 공식 레포에 없음 (OBS로 설치 가능하지만 안정성 의문, `pwntools`는 venv보다 전역 설치가 훨씬 편함)
- distrobox에서 `sudo`가 OOTB로 안됨

---

## NixOS

- 매뉴얼이 성숙하지 않음
- 개념이 너무 복잡하고 학술적임
- 고정된 파일 구조가 없어서 결정 장애와 시간 낭비 유발
- Deal-Breaker: 사전 컴파일된 바이너리 실행에 어려움 (`nix-ld` 같은 유틸리티가 있지만 항상 작동하지 않음, 특히 바이너리 분석 관련)
- 소스에서 컴파일해야 하는 패키지는 시간이 오래 걸릴 수 있음
- `home-manager`와 메인 NixOS 설정 간에 옵션이 공유 안됨 (내 실력 문제일수도?)
- Flathub과 nixpkgs 모두에서 OnlyOffice 한글 입력 안됨
- Deal-Breaker: `ida-free` 패키지가 망가져 있음

---

## 기타 배포판 (사용해보지 않음)

### Void Linux

- 괜찮아 보이지만 매우 마이너한 배포판

### Gentoo Linux

- 이걸 써야 할 이유를 못 찾겠음

### Solus

- 뭔지 모르겠음

### GeckoLinux

- Deal-Breaker: 개발 중단됨

### KDE Neon

- Deal-Breaker: KDE Linux 개발을 위해 곧 중단될 예정
