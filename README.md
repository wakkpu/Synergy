# 프로젝트 소개

---

- 프로젝트명: 시너지
- 서비스 특징: 레크리에이션 자동 진행 기능이 추가된 화상 회의 프로그램
- 기획 배경
    - 코로나19 이후 온라인으로 만나는 일이 잦아졌는데, 온라인은 오프라인에 비해 느껴지는 집중도나 몰입감, 친밀감이 다를 수 밖에 없다.
    - 온라인 회의 역시 늘어나 온라인 상으로 레크리에이션을 진행하는 일이 많은데, 게임 진행을 위한 프로그램을 실행하고, 화상 회의 프로그램으로 이를 화면 공유해 진행한다.
    - 프로그램을 여러 개 켜는 것 자체도 번거롭고, 온라인이기 때문에 진행에도 애로 사항이 많다.
    - 이를 해소하기 위해 한 프로그램 내에서 화상 회의와 게임 진행을 하는 프로그램을 개발했다.
- 주요 기능
    - 문제집 커스터마이즈
    - 링크 공유
- 주요 기술
    - WebRTC
    - JWT Authentication
    - REST API
- 참조 리소스
    - OpenVidu
    - Material UI
- 배포 환경
    - AWS Ubuntu 18.04

# 팀 소개

---

- 전종민(팀장, 백엔드): 로그인, 화상 회의, 레크리에이션 게임 로직 개발
- 강봉민(백엔드): 회원가입, 트러블 슈팅, 배포 관련 설정(HTTPS), 화상 회의
- 조민서(백엔드): 마이페이지, 화상 회의
- 김수정(프론트엔드):
- 김영훈(프론트엔드): 게임생성 페이지, 게임 페이지, 전반적인 UI 디자인

# 프로젝트 상세 설명

### 개발 환경

---

- Windows 10 + WSL
- AWS Ubuntu 18.04
- 백엔드
    - Java 11
    - Gradle 6.7
    - Spring Boot 2.4.5
- 프론트엔드
    - node 16.15.1
    - npm 8.12.2
    - nvm 1.1.9
- 데이터베이스
    - MariaDB 10.6
    - Redis 3.0.5

### 기술 스택

---

- 프론트엔드
    - React
    - TypeScript
    - Material UI
    - Sweet Alert 2
- 백엔드
    - Spring Boot
    - Spring Security
    - JWT
    - JPA
- 데이터베이스
    - MariaDB
    - Redis
- 오픈소스 API
    - OpenVidu
- 협업 툴
    - Jira
    - Gitlab
    - MatterMost
    - Notion
- 인프라
    - Docker
    - Jenkins
    - AWS EC2   

# 기능 설명

### 회원 가입

---

![Untitled](./images/Untitled%202.png)

회원 가입 시 닉네임과 이메일 중복 체크를 해야 하고, 비밀 번호 다시 입력해 확인을 해야 한다.

![Untitled](./images/Untitled%203.png)

회원 가입을 하고 나면 인증용 이메일이 발송되고, 인증 링크를 클릭하지 않으면 로그인 시 이메일 인증을 하라는 경고가 뜬다.

![Untitled](./images/Untitled%204.png)

### 마이페이지

---

![Untitled](./images/Untitled%205.png)

마이페이지에서는 회원 탈퇴, 문제집 생성, 문제집 삭제, 전체 문제집 삭제를 할 수 있다.

### 문제집 생성

---

문제집은 레크리에이션에서 사용할 문제들의 모음집으로, 단체의 특성에 맞게 커스터마이즈할 수 있다.

![Untitled](./images/Untitled%206.png)

![Untitled](./images/Untitled%207.png)

문제집 생성 시 문제집의 이름과, 어떤 게임에서 사용할 문제집인지 정하고, 문제집의 문제들을 작성한 뒤 생성한다.

### 채널 생성

---

![Untitled](./images/Untitled%208.png)

![Untitled](./images/Untitled%209.png)

![Untitled](./images/Untitled%2010.png)

채널 생성 시 어떤 게임을 플레이 할 것인지, 개인전/팀전 중 하나를 고르고, 어떤 문제집을 사용할 것인지, 몇 라운드 플레이 할 것인지 선택한 뒤 채널을 생성한다.

### 화상 채팅

---

![Untitled](./images/Untitled%2011.png)

채널을 생성하고 난 뒤의 화면이다. 카메라와 마이크 on/off, 채팅이 가능하다.

초대 링크 버튼을 클릭하면 초대 링크가 클립보드에 복사된다. 
다른 사용자들에게 이 링크를 공유해 참여하도록 할 수 있다.

게임 시작 버튼을 누르면 초기에 설정한 게임이 시작된다.

### 채널 참여

---

![Untitled](./images/Untitled%2012.png)

초대 링크를 받아 참가할 때의 화면이다. 
채널에 있는 다른 사용자들과 닉네임이 중복되진 않는지 확인하고 입장할 수 있다.

![Untitled](./images/Untitled%2013.png)

호스트 화면과 다른 게스트 화면을 확인할 수 있다. 
초대 링크나 게임 시작 버튼이 없는 모습이다.

### 게임 동작(몸으로 말해요 기준)

---

게임이 시작되면 서버로부터 문제집과 사용자 목록을 불러와 무작위로 정렬해 출제 순서를 정한다.

![Untitled](./images/Untitled%2014.png)

출제자 화면이다. 출제자에게만 문제의 정답을 알려준다.

![Untitled](./images/Untitled%2015.png)

채팅에 정답이 나왔다면 채널에 있는 모든 사람들에게 맞춘 사람의 닉네임을 표시한다

![Untitled](./images/Untitled%2016.png)

![Untitled](./images/Untitled%2017.png)

![Untitled](./images/Untitled%2018.png)

게임의 규칙상 출제자는 마이크와 채팅을 사용할 수 없고, 카메라를 끌 수 없다.

![Untitled](./images/Untitled%2019.png)

![Untitled](./images/Untitled%2020.png)

게임이 종료되면 게임 종료 표시 후 어떤 플레이어가 몇 개를 맞췄는지 결과를 표시한다.
