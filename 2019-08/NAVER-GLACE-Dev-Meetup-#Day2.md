# NAVER GLACE Dev Meetup #Day2

> [행사 안내 URL](https://festa.io/events/424)  
> 장소 : 강남역 2번 출구 메리츠 빌딩 16층 NAVER D2 Startup Factory  
> 시간 : 2019년 8월 21일 19:00 ~ 22:00  
> 참여 목적 :  
> 대규모 시스템에 리액트를 잘 적용하고 있는 사례와 Spring Boot 코틀린 적용 사례를 참고하기 위함.

## section 1. Glace 팀에 대하여

* Global Place의 합성어

* 조직 문화
  * 신기술 활용, FE 고도화, 개발 효율을 추구.
  * Code = Document 별도 문서는 최소화한다.
    * 코드를 읽기 쉽게 작성.
    * 2중 루프 피하기, 식별 가능한 이름을 사용하는 등의 규칙
  * code review 생활화, micro 소통을 중요시함.

* 사내 생활
  * 정해진 출퇴근 시간 없음, 최소 근무시간 주 15시간 (퇴직금을 지급하기 위한 법적 최소 시간)
  * 수평문화, 직급 없음. 호칭은 모두 OOO님.
  * 누구나 issue를 제시하고, 스스로 issue를 taking한다.

* 현재 서비스 중인 프로젝트
  * LINE conomi - 일본 현지 맛집 찾기 서비스
    * 차후 현재 한국에서 서비스중인 네이버 예약 시스템을 덧붙일 예정.
    * [타베로그](https://tabelog.com)와 경쟁하는 서비스

* 감상
  * 개개인이 알아서 잘하자
  * 정해진 출퇴근 시간이 없다 == 내 할 일 끝나야 집에 간다
  * Code = Document라는 문구가 감명 깊었음
  * 이번 행사의 취지를 약간 잘못 파악하고 참석했다는 생각이 들었음
  * 개발 인력 모집 취지의 행사로 파악됨
  * 타베로그 이야기에 흥미가 매우 생김

## section 2. Place 개발 - 게으른 개발자가 부지런히 일하는 방법

* 네이버 메일, My Place 서비스 FE 리액트 전환.
  
* 게으른 개발자?
  * 빌 게이츠의 게으른 사람에게 일을 시킨다는 이론.
  * 게으른 게발자 -> 귀찮고 반복적인 업무 자동화 모색 -> 개발 생산성 상승
  * 워라벨은 중요하다! 자동화 연구 -> 워라벨 좋아짐

* 개발자의 생산성을 높이는 문화
  * 보고용 문서 작성은 하지 않는다.
    * 기술 지식/ 사례 공유 문서는 적극 작성!
  * 주간 보고도 Github issue로 정리한다.
  * 동기식 커뮤니케이션은 지양하고 비동기식(깃헙 이슈, 코멘트)을 지향한다.
  
* 리뷰 문화
  * 코드의 문제는 혼자의 책임이 아니다 - 책임 분산
  * 누가 짜도 비슷한 코드 - 이해하기 쉬운 코드
  * Test code 작성보다 Code review가 DevOps에 있어 더 좋은 방법임.
  * 누군가 휴가를 갔을 경우 - 백업이 쉽다.

* 개발 생산성 & 리팩토링
  * 적은 인원으로 여러 업종 대한 서비스 프론트 개발
  * 업종 별로 비슷한 여러 페이지 공통화 / 재사용
  * 요구사항에 급히 새로운 업종 추가 - 미용실 개발에 2주 걸림 (재사용에 의한 이득)
  * 업종이 너무 많아져 리팩토링을 하게 됨
  * 리팩토링은 더 빨리 달리기 위한 준비에 시간을 쓰는 것
  * 기존에 비해 성능, 개선점 등을 중점적으로 고려
  * 각자 관심 있는 주제를 맡아서 자료 조사 / 정리 후 팀원들에게 공유
  * 결과, 리액트 Class Component에서 Functional Component로 모든 코드 전환.
  * GraphQL, Apollo 도입하여 구축
  * 새로운 기술이나 개선 된 코드를 만들고 싶으면 바로 Branch를 따서  
    PR 작성 후 팀원들의 코드 리뷰 후 Merge하는 문화를 만듬.

* 이런 개발자와 일하면 재미있습니다.
  * 끊임 없이 공부하는 개발자.
  * 겪어보지 못한 에러를 보고 희열을 느끼는 개발자 (~~변태~~)

* 감상
  * 부럽다. 우리 회사에도 도입하고 싶다.
  * 내가 먼저 시작해야겠다.
  * 이 문서 작성 시작.
  * 좋은 건 나누자. 좀스럽게 굴지 말고.

## section 3. DevOps in Place

* DevOps에 사용하는 Tool들
  * Git, Jenkins, Lambda(AWS Service), WORKS(NAVER가 만든 업무용 메신저)활용.
    * ~~WORKS에 대한 발표자 피셜 : Slack보단 구리지만 많이 쓸만해졌다.~~

* Git Branch 운영.
  
  * Master*
    * 정기 배포, 핫픽스 모두 릴리즈를 통해 태그 생성 후 배포
    * 핫픽스 브랜치의 base
    * PR 없이는 merge 불가, 필요 review 수는 탄력적으로 조정

  * Develop*
    * 개발 완료된 코드를 merge
    * 배포 시엔 master에 merge후 배포
    * 정기 배포 브랜치의 base

  * Test
    * Test 환경에 Continuous Delivery
    * 자유롭게 merge하고 overwrite 가능

* Jenkins

  * Master
    * 업데이트 되면 Docker image build, test, push
    * 미리 image 보안 검수 요청 - 3분 정도 걸리는 자동화 보안 검수에 들어감.
    * Production 환경에 배포할 image 준비

  * Test
    * 업데이트 되면 image build, test, push
    * Test 환경에 image 배포
    * CD pipeline 결과 DB에 적재
  
  * etc.
    * PR 생성시 반드시 eslint / tslint prettier로 코드 컨벤션 강제
    * 배포 결과 메신저로 받음.
    * 게으른 개발자가 자동화할 수 있는 기능들을 람다를 사용해서 구축
  
  * 감상
    * 상당 수 우리 팀에도 구축 되어있는 부분
    * 조직의 규모와 수준을 생각해서 우리만의 깃 운영의 노하우를 쌓을 필요가 있음
    * 커밋할 때 코드 컨벤션 강제하는 것은 좋은 운영 노하우라 여겨짐.

## section 4. React Native를 활용한 Cross Platform 앱 개발 성공기

## section 5. 네이버가 만든 테스트 툴 nGrinder

## section 6. 네이버 여행 오픈하다 오픈소스 만든 이야기 (feat. GraphQL)

## section 7. Spring Boot 기반의 네이버 예약 서버에 Kotlin 적용하기
