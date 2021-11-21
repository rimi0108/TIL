# CI/CD

- Continous Integration, Continuous Delivery/Deployment의 약자이다.
- 지속적 통합, 지속적 배포
- 프로그래머들이 소프트웨어를 코딩하고 나서 이를 최종 배포까지 하는 과정에서 진행되는 일들

## CI
- git으로 merge하고 test하면 되는데, 거기서 뭐가 또 필요하나?
- 각 구성원들의 코드를 받아와 합치기 전에 코드에 문제가 없는지 확인해야 한다.
- 규모가 커질 수록 사람이 수작업으로 테스트를 하는데 무리가 있기때문에 자동화 작업을 진행한다.
- 자동화된 빌드, 테스트는 코드의 충돌을 방어한다.

### MSA (Micro Service Architecture)

- 기존의 어플리케이션이 모든 기능을 포함하는 하나의 거대한 서비스였다면, MSA는 작은 기능별로 서비스를 잘게 쪼개어 개발하는 형태를 의미한다.
- MSA에서는 기능 추가가 매우 빈번히 발생하고 작은 단위의 기능들의 긴밀한 동작 테스트도 중요해진다.
  - 여기서 CI의 적용은 기능 충돌을 방지할 수 있다.

## CD
- Continous Delivery : 공유 레포지토리로 자동으로 Release 하는 것
- Continous Deployment : 자동으로 배포하는 것
- 개발자의 변경사항이 레포지토리를 넘어 고객의 프로덕션 환경까지 릴리즈 되는 것

## CI/CD 툴
- Jenkins
- Buildkite
- Bamboo
- 등 등



### <참고>
- https://artist-developer.tistory.com/24