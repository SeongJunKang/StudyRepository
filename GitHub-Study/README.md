# GitHub Study
- 이건 원격지 Git을 공부하기 위해 만든 프로젝트입니다.<br>

## Git game
- [Git game](https://learngitbranching.js.org/)이라는 사이트는 GitHub의 브런치 연습을 위한 사이트 입니다.<br>
- 많은 힌트를 제공하니 연습용으로 좋을 것 같습니다.

## Git
- Git은 분산 버전 관리 시스템(Distributed Version Control System; DVCS)으로 로컬(Local)의 repository와 서버(Master)의 repository가 있습니다.<br>
서버의 repository에서 클론을 받으면 로컬 repository가 생기고, 로컬 repository에서 수정하여 서버에 수정사항을 반영할 수 있습니다.
- 작업을 행하는 작업 폴더를 `워킹 디렉토리`라고 부릅니다
- 워킹 디렉토리의 모든 파일은 크게 Tracked(관리대상임)와 Untracked(관리대상이 아님)로 나눈다. 
- Tracked 파일은 또 Unmodified(수정하지 않음)와 Modified(수정함) 그리고 Staged(커밋으로 저장소에 기록할) 상태 중 하나이다. 
<br>

![깃허브의 라이프 사이클](/GitHub-Study/images/lifecycle.png)

이미지 출처, 참고 사이트 : [git-scm](https://git-scm.com/book/ko/v2/Git%EC%9D%98-%EA%B8%B0%EC%B4%88-%EC%88%98%EC%A0%95%ED%95%98%EA%B3%A0-%EC%A0%80%EC%9E%A5%EC%86%8C%EC%97%90-%EC%A0%80%EC%9E%A5%ED%95%98%EA%B8%B0)

## Git 명령어 

### git init 
- git 파일로 변경하기 위한 초기 설정 실행
## 사용자 정보 등록
### git config --global user.name "username"
- 사용자 이름 등록
### git config --global user.email "useremail"
- 사용자 이메일 등록
### git add
- Untracked 혹은 Modified 파일을 Staged에 저장할 준비를 한다.
- git add . => 워킹 디렉토리의 파일을 Staged에 저장할 준비를 한다.
- git add filename => 해당 파일을 Staged에 저장할 준비를 한다.
- git add *.exp => exp라는 확장자를 가진 파일을 Staged에 저장할 준비를 한다.
### git commit
- 저장 준비가 된 파일들을 Staged에 저장하여 Unmodified 상태로 변경한다.
- 커밋이 되면 커밋의 정보가 해쉬태그 형태로 남는다.
- git commit -m "message" => 커밋 내용을 간략한 메세지로 남긴다.
- git commit => vi가 열리면서 커밋의 자세한 내용을 남긴다.
### git status
- 현재의 관리하고 있는 파일의 상태를 확인할 수 있다.
### git log 
- 현재 커밋된 메세지들과 해시태그를 확인할 수 있다.
### git branch
#### 새로운 Branch를 만든다. 작업할 워킹 디렉토리를 나눈다고 생각하면된다.
```
git branch [ Branch Name ]
```
#### Branch를 삭제한다.
```
git branch -d [ Branch Name ]
```
#### 브랜치 원격 저장소에 등록하기
```
git push origin [ Branch Name]
```
#### local 브랜치 remote branch와 연동하기
```
git branch --set-upstream-to origin/[Branch Name]
```


### git checkout
- HEAD는 현재 내가 작업하는 워킹디렉토리의 위치를 의미한다.
#### Branch로 HEAD를 옮긴다.
```
git checkout [ branchName ]
```
#### Branch가 없는 상태의 커밋된 위치로 HEAD를 옮긴다. 해시코드는 약자 6~8자리만 써도 이동이 된다.
```
git checkout [ HashCode ]
```
#### 새로운 Branch를 만들고 HEAD를 이동한다.
```
git checkout -b [ branchName ]
```
### git merge
- git merge [ Branch Name ] => master와 해당 branch를 merge(통합)한다.<br>
ex) bugFix라는 branch와 Master를 merge하는 예제. - git merge bugFix
ex) 깃 게임 기본 3단계 merge.

![Git Game의 깃 기본 3단계](/GitHub-Study/images/gitMerge.png)
<br>

### git rebase
- git rebase [합칠 branch] [합쳐질 branch] => 합쳐질 branch를 master에 추가한다라는 의미.<br>
- cf) master랑 branch(ex:test)가 있고, test branch보다 master가 HEAD가 높을 때,<br>
1. git checkout test<br>
2. git rebase master<br>

ex) 깃 게임 기본 4단계 rebase.

![Git Game의 깃 기본 4단계](/GitHub-Study/images/GitRebaseImg.PNG)
<br>

![Git Game의 깃 기본 4단계의 정답](/GitHub-Study/images/GitRebaseAnswer.PNG)
<br>

이미지 출처 : [git Game](https://learngitbranching.js.org/)

## 다른 명령어 추가 예정
