# 1. 서버 파트 전용 Organization 이용 목적

- 과제 제출
- 코드 리뷰
- 아키이빙
  <br />
  <br />

# 2. 첫 세팅 방법

자신의 이름으로 된 repository를 clone 받아서 이용한다.
<br />
<Br />

## 2.1. clone 이란?

원격의 Git 저장소를 로컬에 복제해오는 명령어이다.  
<br/>

## 2.2. clone 방법

1. 아래 버튼을 눌러 git 저장소 주소를 복사합니다.
   <img src="https://user-images.githubusercontent.com/29723695/135631910-53e3f7a4-2857-4905-8766-0ea963b50065.png">

2. cmd(git bash, iterm, cmder 등)를 이용하여 해당 파일을 위치시키고자 하는 폴더에서 <br />
   `git clone <주소> ` 명령어를 입력합니다. <br />
   <img src="https://user-images.githubusercontent.com/29723695/135632077-b6b9cc38-5a7c-48bf-9d7f-640661752bf8.png">

   - cmd는 local 폴더를 그대로 반영하고 있습니다. `cd <로컬주소>` 를 입력하면, 해당 경로로 들어가고(Change Directory), `../` 를 입력하면 이전 폴더로 돌어갈 수 있습니다. 저 같은 경우는 (클론하고자 하는 레포지토리를) `~/dev/sopt/29/WE-SOPT-29_SERVER` 경로 안에 위치시키고자 했기 떄문에 해당 경로로 `cd ~/dev/SOPT/29/WE-SOPT-29_SERVER` 를 하고, `git clone` 명령어를 실행해 `NOTICE` 폴더를 생성했습니다.<br/><br/>

3. 이제 `NOTICE` 프로젝트로 들어가서(cd : Change Directory), 프로젝트를 실행시킵니다. (code .)
   <img src="https://user-images.githubusercontent.com/29723695/135632230-1291630f-a891-408b-86f0-32411bfda168.png">  
   <br/>

# 3. About git/github

<img src="https://uidaholib.github.io/get-git/images/workflow.png">
<br/>

## 3.1. 4가지 영역

git/github를 사용하면 4개의 영역을 마주하게 됩니다.

1. working directory (작업하는 공간)
2. staging area
3. local repository (git)
4. remote repository (github)  
   <br />

## 3.2. add란?

working directory에 있는 파일(VS Code에서 변경사항이 발생한 파일)을 staging area로 올리는 명령어.  
즉, 무엇을 repository에 올릴지 정하는 단계.  
다시 말하면 무엇을 commit할 지 정하는 단계.  
<br/>

## 3.3. commit이란?

staging area에 있는 파일을 local repository(git)에 올리는 명령어.  
github가 아니라, git에 올리는 명령어입니다.  
git은 local 환경에서 repository 버전관리 해주는 시스템입니다.  
github는 이 버전을 온라인 상에 올릴 수 있게 하는 서비스 중 하나일 뿐입니다.  
<br />

## 3.4. push 란?

local 에 올려놓은 파일을 remote(github 같은 소스코드 호스팅 플랫폼)에 올릴 수 있도록 하는 명령어  
즉 push 해야 github에 올라가고, 다른 사람이 온라인에서 해당 코드를 볼 수 있습니다.  
협업을 가능케 하는 것은 github와 같은 서비스입니다.  
<br />

## 3.5. pull 이란?<br />

push는 working directory(여러분의 VS Code)와 remote(github)가 다를 때 remote에 올라와 있는 버전을 working directory로 가져오기 위한 명령어입니다.  
<br />

# 4. commit 을 왜 하는가?

> 개발 히스토리를 남겨, 이전 개발 기록으로 돌아가기 위하여. (**history rollback**)

이것이 제대로 이루어지려면, 변경사항이 작고 독립적이어야 합니다. 즉, 하나의 기능마다 하나의 커밋을 해주어야 합니다.
<br/>
-> commit message는 기본적으로 하나의 기능이 완수되었음을 설명하는 것이 좋습니다.

가령 서버 개발을 한다고 했을 때, API 하나를 커밋 단위로 잡을 수도 있겠습니다.

<br />

# 5. Commit Message Convention

commit message를 어떻게 적을지에 관한 약속입니다.

정답은 없습니다. 같이 작업하는 팀에서 그 팀에게 가장 맞는 일련의 규칙들을 설정하고 따르면 됩니다.

중요한 것은 변경 사항에 대한 설명이 명확하도록 하는 것이며, 변경 사항의 종류를 reasonable하게 구분하는 것입니다. 그래야 **history rollback**이 용이하기 때문입니다.

가령 다음과 같은 규칙을 설정할 수 있겠습니다.

#1

> `기능(feat)`: 새로운 기능을 추가  
> `버그(fix)`: 버그 수정  
> `리팩토링(refactor)`: 코드 리팩토링  
> `형식(style)`: 코드 형식, 정렬, 주석 등의 변경(동작에 영향을 주는 코드 변경 없음)  
> `테스트(test)`: 테스트 추가, 테스트 리팩토링(제품 코드 수정 없음, 테스트 코드에 관련된 모든 변경에 해당)  
> `문서(docs)`: 문서 수정(제품 코드 수정 없음)  
> `기타(chore)`: 빌드 업무 수정, 패키지 매니저 설정 등 위에 해당되지 않는 모든 변경(제품 코드 수정 없음)
> [Prefix] <Description> (#Issue_Number)

<br/>

#2

> - ✅ [CHORE] : 코드 수정, 내부 파일 수정
> - ✨ [FEAT] : 새로운 기능 구현
> - ➕ [ADD] : Feat 이외의 부수적인 코드 추가, 라이브러리 추가, 새로운 파일 생성 시
> - 🍱 [ADD] : 에셋 추가
> - 🚑️ [HOTFIX] : issue나, QA에서 급한 버그 수정에 사용
> - 🔨 [FIX] : 버그, 오류 해결
> - ⚰️ [DEL] : 쓸모없는 코드 삭제
> - 📝 [DOCS] : README나 WIKI 등의 문서 개정
> - 💄 [MOD] : storyboard 파일,UI 수정한 경우
> - ✏️ [CORRECT] : 주로 문법의 오류나 타입의 변경, 이름 변경 등에 사용합니다.
> - 🚚 [MOVE] : 프로젝트 내 파일이나 코드의 이동
> - ⏪️ [RENAME] : 파일 이름 변경이 있을 때 사용합니다.
> - ⚡️ [IMPROVE] : 향상이 있을 때 사용합니다.
> - ♻️ [REFACTOR] : 전면 수정이 있을 때 사용합니다
> - 🔀 [MERGE]: 다른브렌치를 merge 할 때 사용합니다.

>      제목 첫 글자를 대문자로
>      제목은 명령문으로
>      제목 끝에 마침표(.) 금지
>      제목과 본문을 한 줄 띄워 분리하기
>      본문은 "어떻게" 보다 "무엇을", "왜"를 설명한다.
>      본문에 여러줄의 메시지를 작성할 땐 "-"로 구분

**Ex) 이렇게 사용할 수 있습니다.**

#1

```
git commit -m "feat: postGET API 구현"
git commit -m "feat: 소셜 로그인 구현 "
git commit -m "fix: JWT 버그 수정"
git commit -m "docs: readme 수정"
```

<br/>

#2

```
git commit -m "✨ [FEAT] : postGET API 구현"
git commit -m "✨ [FEAT] : 소셜 로그인 구현 "
git commit -m "🔨 [FIX] : JWT 버그 수정"
git commit -m "📝 [DOCS] readme 수정
```

<br/>

이처럼 구체적인 규칙은 정하기 나름입니다!

<br/>

# 6. 과제 제출 방법

> 과제는 매주 금요일까지 새 branch를 파서 Pull Request (PR)로 제출하는 것을 원칙으로 합니다.

-> OT 때 최종 마감일인 12월 24일까지만 제출해주시면 된다고 말씀드렸죠? 이 사실엔 변함이 없고, 그 때까지만 제출해주시면 불이익은 없습니다. 다만 그 때 그 때 세미나 진도에 맞춰 과제를 제출해주시면 여러분도 편하고, 채점하는 저도 편할 것 같습니다. 따라서 가급적이면 매 주 금요일 (다음 세미나 전)에 과제 제출을 완료해주시면 감사하겠습니다 :)

## 6.1. main/master branch란?

깃에서 프로젝트를 생성하면 처음 생기는 주 브랜치를 의미합니다. 예전에는 이 주 브랜치 이름이 master였으나, 인터넷 상에서 인종차별적 표현을 지양하자는 운동에 따라 작년을 기점으로 주 브랜치 이름이 main으로 변경되었습니다.  
<br/>

## 6.2. branch와 pull request란?

<img src="https://t1.daumcdn.net/cfile/tistory/999A7E495B28DBB036">

> 주 브랜치(Master branch)에서 Development branch를 파고 개발하고 main에 합치고, release로 배포하는 일련의 과정을 나타낸 그림.

Software개발시 개발자들은 동일한 소스코드 위에서 신규 개발, 버그 수정 등의 업무를 협업하곤 합니다. 이때 동일한 branch로 작업을 하면, 합칠 때에 일명 `conflict`라고 부르는 것이 발생할 수 있습니다. 이를 방지하기 위해 보통 여러 개의 브랜치(`Branch`)를 생성해 하나의 프로젝트를 여러 갈래로 나누어서 관리합니다. 우선 `branch`를 나누어서 각자 맡은 부분을 따로 개발을 한 후, 나중에 main 브랜치로 합치는 것이죠.

`pull request`란, 여러 갈래의 브랜치를 하나로 합치는 과정에서 `"저의 코드를 봐주시고, main branch에 반영해주세요"` 라고 요청하는 행위입니다.
<br/>
<br/>

## 6.3. branch를 생성하는 방법

`git branch <branch_name>`

과제 제출시 branch 이름은 `assignment1-wooyeong-kim`과 같이 해주시면 됩니다.

branch 이름은 kebab case(소문자 단어들을 - dash로 연결하는 문자표기법)을 흔히 사용합니다.
<br/>
<br/>

## 6.4. branch로 이동하는 방법

`git switch <branch_name>`
<br/>
<br/>

## 6.5. branch 생성과 동시에 이동하는 방법

`git switch -c <branch_name>`
<br/>
<br/>

## 6.6. branch를 삭제하는 방법

`git branch -d <branch_name>`
<br/>
<br/>

## 6.6. `git stash`

새 branch에서 작업해야 하는데, 잘못하여 main이나 다른 branch에서 작업한 경우에 자주 사용한다.
이전 commit의 상태로 되돌리고, commit 이후의 모든 파일(add 한 것도)을 잠깐 스택에 저장해두는 명령어.
<br/>
<br/>

## 6.7. `git stash pop`

임시 저장해둔 파일들을 꺼내오는 명령어.

즉, feature/header라는 branch에서 작업을 하다가, feature/footer라는 branch에서 해야할 일이 생겼다고 하자. 이때 commit을 하기엔 하나의 기능을 마치지 않은 단계라고 하자. 이 상태에서 branch를 옮기려고 하면 옮겨지지 않는다. commit하지 않았기 때문에 local 환경에서 기억할 수 없기 때문이다. 그러므로 이 변경사항들을 임시로 저장해둬야하는데, 이를 위해 `git stash` 명령어를 사용한다. 이후 feature/footer에서 작업을 마치고 다시 feature/header로 돌아와서 `git stash pop` 명령어를 사용하면 이전에 임시저장 해둔 변경사항이 다시 돌아오게 되어, 작업을 이어나갈 수 있게 된다.
<br/>
<br/>

## 6.8. pull request 를 날리는 방법

해당 브랜치에 push하고 github repository에 들어가보면 자동으로 pull request 날리겠냐는 메시지가 뜨게 된다.

feature/header branch에서 작업을 하고, `git push feature/header` 하였다면, 아래와 같이 메시지가 뜬다.
<img src="https://user-images.githubusercontent.com/24906022/134860968-5247ac82-5e7e-4683-9131-ccb775da54f9.png">

그리고 `Compare & pull request` 버튼을 누르면 아래와 같은 창이 뜨게 된다.
<img src="https://user-images.githubusercontent.com/24906022/134861317-ef32abc4-7d9a-436d-8a9f-416668240f0d.png">
제목을 입력하고, 내용에는 자신이 이 pull request에서 한 작업, 코드 확인 받고 싶은 부분을 적어주면 된다. 또한 UI 구현 문제가 있거나, 구현 사항을 확실히 보여주고 싶은 경우 img나 gif를 통해서 첨부해주면 좋을 것이다.
<br/>
<br/>

## 6.9. pull request 에서 comment 달고, approve 받기

pull request를 날리면, 해당 pr에서 작성된 코드 변경사항을 볼 수 있고, comment를 달아 칭찬을 해주거나/피드백을 해줄 수 있다. `Files changed`에 들어가서 변경사항을 확인하고, comment를 달아준다.
<img src="https://user-images.githubusercontent.com/24906022/134861942-e84cd47b-500f-4c68-8b8f-414faa0e3857.png">
그리고 오른쪽 위에 `Review changes `버튼을 눌러, 전체 코멘트를 달아주거나, approve 해주거나, Request changes로 수정 요청을 할 수 있다. 그래서 보통 프로젝트 진행 시, 리드 개발자가 approve한 다음에, pull request를 merge할 수 있도록 기능을 추가하기도 한다. 과제에서는 파트장이 approve 한 다음에, merge될 수 있도록 할 것이다.
<img src="https://user-images.githubusercontent.com/24906022/134861725-f376fee2-af3e-4cd0-8bd6-847a9e384895.png">
<br/>
<br/>

## 6.10. branch 내용을 main으로 합치기

과제 제출을 하고, 파트장이 approve하였다면, branch를 main에 merge할 수 있다.
<img src="https://user-images.githubusercontent.com/24906022/134882348-97e2fe41-52c9-4951-87bd-69f3f893fd1f.png">
그리고 이제 해당 브랜치는 필요가 없으므로 `delete branch` 버튼을 눌러, branch를 삭제해주면 된다.
<img src="https://user-images.githubusercontent.com/24906022/134882533-b5b3f69c-286d-4299-9085-a43c05fbffa6.png">
<br/>
<br/>

## 6.11. main에 branch 내용이 붙은 코드를 local 에서 불러오기 (git pull)

특정 branch 내용을 main에 merge 하면, github repository에 잘 반영될 것이다. 하지만 working directory에서는 반영되어 있지 않을 것이다. 이 상태로 작업을 하고 push를 하면, local과 remote(github)간의 차이로 인해 conflict가 발생할 것이다. 그러므로, github의 변경사항을 working directory로 가져올 필요가 있다. 이 명령어가 바로 git pull 이다. main에 있는 내용을 가져온다는 의미에서 `git pull origin main`을 사용한다.

[pr 날리고, comment달고, approve 한 좋은 예시](https://github.com/pa-rang/kyrics-frontend/pull/15)  
<br />

# 7. 정리

과제 제출은

1. 자신의 이름으로 된 repository를 clone 받기
2. 새 branch를 파서 개발하고 pull request 날리기
3. commit message를 아무렇게나 기술하지 않고, convention을 지켜서 commit 하기

<br/>

# 8. Thanks to

**핵심 내용을 작성해주신 웹팟장님과, 커밋 메시지 컨벤션 관련 도움을 주신 iOS 파트장님께 감사드립니다**

웹팟장님(김의진)의 깃허브: https://github.com/euijinkk

iOS 파트장(장혜령)님의 깃허브: https://github.com/hryeong66
