# git rebase

## merge와 rebase의 차이점
- git merge 명령어와 git rebase 명령어를 혼용하면 문제가 생길 수도 있으니, 하나의 명령어를 선택해서 사용하도록 하자
![](https://images.velog.io/images/rimi0108/post/e69a88d4-bab7-47b5-8bae-d8076ddc0bd3/image.png)
- merge는 main branch를 기점으로 생성된 feature branch의 모든 commit을 하나로 합치는 것이다.
- merge를 사용하면 불필요한 merge commmit이 생성된다.
  - 모든 feature branch가 main으로 merge 될때마다 merge commit이 남는다. 
  - branch history가 지저분해지기 쉽다.
- main 브랜치에서 각 기능마다 독립된 branch를 생성해 로직을 작성하고 수정하더라도 merge했을 시 다른 branch의 작업과 내역이 겹쳐 구분하기 어려워진다.
- git rebase를 사용하면 각 기능마다 commit을 하나로 통합해 깔끔하게 history를 관리할 수 있다.

### git -HEAD
- 현재 체크아웃된 커밋을 가르킨다
  - 현재 작업 중인 커밋
  - HEAD는 브랜치의 이름 가르킴

### rebase 명령어
- **git rebase -i main**
  - rebase를 하면서 squash를 사용해 커밋을 하나로 정리 할 수 있다
- **git rebase --abort**, **git reflog**
  - 잘못 리베이스 했을 시, 돌아갈 지점을 찾을 수 있다
- **git reset --hard 돌아갈지점**
  - 돌아갈 지점으로 다시 git을 복구할 수 있다
- <span style="color:indianred">**conflict 발생 시 🤯** </span>
  - 에디터에서 충돌한 코드를 해결한 후 
  git add . -> git rebase --continue를 반복한다.
  - commit을 할 필요는 없다.