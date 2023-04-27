# security1

## 스프링 시큐리티 스터디용 리포지토리

### 스프링 시큐리티 최신버전을 활용하여 구성하였으며, 이전 버전과 메서드 사용등의 차이 및 최신 버전에서의 사용법을 익히기 위함.

## Day-1

스프링 시큐리티의 설정을 통하여 권한 설정, 인터셉터 등을 설정
- 오라클 db를 연결하는 중 permission denied로 인하여 db 연결에 실패 하였으나, 비밀번호세팅 잘못 되어있던것으로 확인하여 해결

## Day-2
- application.properties에서 viewResolver 관련 세팅이 가능하여 WebMVCConfig는 삭제처리
- userdetails 클래스를 이용한 로그인 처리
- 세션 로그인시 session을 유지하기 위해 stateless 설정을 비활성화 시켜야 한다.

## Day-3
- hasRole()메서드 사용시 각각의 Role 앞에 'ROLE_'을 붙히지 않도록한다. 이는 스프링 시큐리티에서 접두사를 자동으로 붙혀주기 때문에 따로 붙히게 되면 Role을 이상하게 인식함.
- @EnableMethodSecurity(securedEnabled = true) //secured 어노테이션 활성화(특정 메서드에 걸고싶을때 사용)
- @EnableMethodSecurity(prePostEnabled = true) //preAuthorize 어노테이션 활성화(특정 메서드에 걸고싶을때 사용)
    1. google login - google api 프로젝트 생성 및 id, key 필요
    2. 구글 로그인의 진행
       1.  구글로그인버튼 클릭 -> 구글로그인창 -> 로그인 완료 -> code반환(Oauth-Client) -> AccessToken요청 -> userRequest 정보 -> loadUser함수 호출 -> 구글로부터 회원 프로필 get
       
    