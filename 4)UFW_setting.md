# UFW / 설정하기

생성일: 2021년 7월 8일 오후 10:05

## UFW

---

[방화벽에 대해서](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=ynkim642&logNo=220420006809)

### UFW

- Uncomplicated Firewall
- 데비안 계열 및 다양한 리눅스 환경에서 작동되는 `사용하기 쉬운` 방화벽 관리 프로그램
프로그램 구성에는 iptable를 사용한다. (iptable 설정과 관리가 겁나복잡함)
- 리눅스의 핵심인 커널은 server에 대한 client의 네트워크 접속을 제어하는 넷필터라는 모듈을 가지고 있는데, 그것을 활용하여 서버 접속에 대한 네트워크 정책을 세우는 프로그램이 바로 Firewall
- 설치했다고 바로 작동되지는 않고 시스템 시작시에도 방화벽이 백그라운드에서 자동으로 활성화되게끔 하기 위해선 터미널에서 작업을 해주어야 한다.

### iptable

시스템관리자가 리눅스 커널 방화벽이 제공하는 테이블과 그것들을 저장하는 체인, 규칙들을 구성할 수 있게 해주는 사용자 공간 응용프로그램

### 방화벽 사용 이유

- 보안이 필요한 네트워크의 통로를 단일화하여 관리함으로써 외부의 불법침입으로부터 내부의 정보자산을 보호하기 위한 시스템
- 사용자 인증, 주소변환, 감사기록 등이 장점
- 강력한 접근제어를 제공하기 위해 외부망과 내부망의 구성을 위한 별개의 네트워크를 가진다
- 바이러스와 같은 맬웨어 형태로 존재하는 위협은 방어할 수 없다

### UFW 활용

- 꼭 필요한 포트만 열어둔다
- 내부 비공개 서비스 포트는 기본값이 아닌 임의 포트로 변경한다
- 특정 컴퓨터 IP에서만 내부 비공개 서비스 포트로 접속한다

## UFW 설정

---

- `sudo apt install ufw` 명령어로 설치
- `sudo ufw status verbose` 명령어로 ufw 상태 확인 (디폴트는 inactive)
- `sudo ufw enable` 명령어로, 부팅 시 ufw 활성화되게 설정
- `sudo ufw default deny` 명령어로 기본 incoming deny로 설정
- `sudo ufw allow 4242` 명령어로, ssh연결 허용
- 정책 삭제 시, <span style="color: red">~~삭제~~</span>

### DHCP끄기

아래 홈페이지 참고

[VirtualBox Debian - dhclient 없애기, 고정 IP 설정](https://nostressdev.tistory.com/3)