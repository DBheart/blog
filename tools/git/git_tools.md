툴로 쓰는 깃(이크립스, VS Code, Source Tree)
	> 별로 추천하고 싶지는 않다. 소스트리와 VS Code는 느리고, 이크립스는 헸갈린다.
	1. 프로젝트 import
		ㄱ. 이크립스
			1. Git 레파지토리에서 추가
				- "Clone Git Repository"로 추가
				- SVN하고 했갈렸던것은 SVN은 원격과 연결이라면 이것은 local Repository에 넣는 clone 과정이라는 것이다. 실제로 특정 디렉토리에 생성되어 있다.
				- 마우스 오른쪽 버튼 -> "Import Projects..." -> 디렉토리 선택
			2. 프로젝트 import에서 추가 : 추후 push할때 문제가 될수도 있음
				- 마우스 오른쪽 키 import 선택
				- "Projects from Git" 선택, 이것을 하면 아래 두개를 선택할수 있음 
					- Existing local repository : 1번에서 clone한것을 프로젝트로 생성
					- Clone URI : 클론을 하면서 프로젝트 Import
		ㄴ. VS Code
			- clone 기능 미지원
			- clone후 File => Opne Folder에서 클론된 프로젝트를 선택 
			- 터미널을 연후에 git cli명령으로 진행한다.
		ㄷ. 소스 트리
			- 탭부분의 "+" 클릭하여서 clone 진행
			- 소스트리는 소스수정 기능없으므로 프로젝트 생성은 안된다. Git관리만 한다.
	2. 기본 소스 반영
		소스반영은 대체적으로 add를 해서 stage에 반영후 commit하여 commit버전을 push를 하여 최종적으로 원격서버에 반영하게 된다. 
		소스를 받을때도 마찬가지이다. commit단위로 pull을 받게 된다. 기본적으로 commit을 한단위로 움직인다는것을 유념하며 진행하여여 한다. 
		여기서는 우선 충돌이 없다는 가정하에 내가 수정하는 것을 반영하는것을 여러 툴들로 하는법을 알아볼것이다. 
		실제로 실행해보지는 않아서 맞지 않을수도 있지만 최대한 찾아본후에 적을 것이다.
		ㄱ. 이크립스
			- 프로젝트선택 => 마우스 오른쪽키 -> Team -> Synchronize Workspace
				- 왼쪽 Synchronize에서는 내가 클론 받은 브랜치와 다른 내용이 있는 소스 리스트가 보이게 된다. 
					> 틀린점을 확인후에 push를 받는게 최종 목적이다. 이크립스는 특이하게 OverWrite라는 기능이 있어서 원격에 있는것을 덧씌워줄수도 있다. 하지만 이건 임시이며 push받은것이 아니기때문에 commit할때 충돌이 날수 있기때문에 되도록 pull로 받도록 한다.
					> 파일 선택후 OverWrite, Merge, Mark as Merged라고 3개가 있는지 OverWrite와는 달리 두개는 잘 모르겠다. 
				- 오른쪽에는 내가 수정한 소스들이 나오는데 각각 아래와 같은 상태가 있다.
					* Unstaged change : 아직 add하기전이지만 수정된것
					* Stated changes : commit 대상이라고 생각하면된다. add를 하면 올라오게 된다.
					* Add index : state상태로 올리는 것을 말한다. 
					* commit message : 커밋할때 메세지
					* commit and push : 커밋과 동시에 원격에 커밋버전을 반영한다.
					* commit : 로컬에 커밋만을 한다.
		ㄴ. VS Code
			- 왼쪽의 3버너째에 있는 Source Control을 선택
			- changes리스트에서 파일끝에 있는 "+" 버튼이나 파일여러개 선택후 마우스 오른쪽버튼 누르면 나오는 "stage changes" 선택
			- "..."을 클릭후 commit stated(Signed off)를 클릭후 커밋 메세지를 입력해서 커밋
				- "V"를 눌러서 커밋하지 말자. chnages에 있는 것이 모두 커밋된다.
				- 왜인지 모르겠지만 원격에 있는 것은 pull받은후 나의 branch에 merge할때 changes가 엄청나게 생길때가 있다.
			- push 실시
		ㄷ. 소스트리
			- 커밋까지는 이크립스와 비슷하다. -> 파일 상태 클릭하면 커밋할수 있는 화면이 나온다.
			- push는 위에 push 버튼을 누르면 된다.
		ㄹ. 기타 팁들
			- 이전 커밋에 파일을 추가할수 있는 cli명령이 있다.
				> git commit --amend  , 물론 추가 add를 한것이 있어야 겠지?
			- 이크립스도 그렇고 소스트리도 스테이지로 올리고 내리고가 참 쉽게 되어있다. 
				> 직관적이다. untrack도 쉬운것같다. assume도 쉬운것 같고
			- VS Code에서
				- Discard changes는 statge들어가기전에 수정 되기 전으로 돌리는 것을 말한다. 
					> cli로는 'git checkout -- 파일들'
					> 이걸하면 내가 수정한것이 다 날라가므로 되도록 하지 말자. 깃소개에서도 권장하지 않는단다.
				- Stage chages는 Add 하는 것
				- Unstage changes는 add를 해제할때 쓴다.
					> cli로는 'git reset HEAD 파일들', ㅇㅇ? 아닌데... 다시한번 보도록 하자.
			- 이크립스의 Syncnize후 오른쪽에 있는 Unstaged change에 있는 파일 선택후 오른쪽 마우스 클릭하면 다음을 할수 있는 기능이 나온다.
				- Assume Unchanged : 고나리 대상 아님으로 status로 나오지 않게 한다.
					> status로 하면 보이지 않게 된다.
				- Untrack : 관리대상아님으로 바꾸고 stage로 올린다. 
					> cli로 볼때는 untracked file로 보이는 것들인것 같다.
					> 이것들은 commit가 되지 않는다. 
	3. 소스비교 : log, show, blame
		ㄱ. 이크립스
			- SVN부터 사용한 이크립스는 sync를 맞춘다음에 진행하고 이는 했다. 또한 show history와 show local history가 참으로 유용했는데 그걸 생각하고 사용하면 했갈릴수가 있다. 
			- git도 마찬기지로  "Team -> Synchronize Workspace"를 지원한다. 이것은 현재 브론치랑 리모트의 브론치를 비교해서 보여주게 된다.
			- 이때 왼쪽에 파일트리에서 파일을 클리하면 리모트의 같은 브랜치와 비교를 하고 오른쪽의 Unstage나 Staged에 있는 파일을 클릭하면 로컬의 commit와 비교하는 것이니 했갈리지 말자.
			- 또한 git은 다른 브론치와 비교할수 있다. 우선 내가 찾은 것은 리모트에 있는 브론치이다.
				> Team -> Advanced -> Synchronize -> 비교 브론치 선택, 이렇게 진행하면 로컬과 리모트의 브론치와 비교할수 있다.
			- 로컬의 커밋버전과 비교하는것은 아래의 것을 실행하면 될것 같다.
				> Team -> Show in History , 실행하면 커밋히스토리가 나오며 커밋버전을 클릭하면 수정된 내역이 나오고 거기서 파일 선택한 후 마우스 오른쪽키 선택하면 "Work 버전과 비교"와 "이전버전과 비교"가 있으니 확인해보면 될것 같다.
			- blame기능인 하나의 파일에 대한 이력의 경우
				> 파일 선택 -> Team -> Show in History를 선택하면 여태 수정한 커밋버전과 함께 나온다.
			- 이크립스의 경우 로컬히스토리라고 해서 파일이 수정된 내역을 볼수 있다. 
				> Team -> Show Local History
				> SVN에서는 유용하게 쓰던것인데 브론치에서 브론치로 Merge 받거나 그러면 사라지는 것 같아서 이전처럼 많이 사용하지는 않는것 같다.
				> 하나의 작업이 나올때마다 브랜치를 따서 작업을 진행하기 때문에 의미가 많이 퇴색되었다.
		ㄴ. VS Code
			- log, show, blame에 대해서 그렇게 기대하기 힘든것 같다. 무척 느리기도 해서 쓰기 싫고 말이다. 
				> 파일 or 폴더 선택후 Reveal in Explorer을 선택하면 해당 폴더로 이동하는데 거기서 git bash를 하면 될것 같다.
				> VS Code의 터미널을 열면 root폴더로 자동이동해주니까 여기서 써도 된다. 하지만... 쓸수록 점차 느려진다.
			- VS Code에 나오는 git명령관련해서 정리만하고 넘어간다.
				- Pull : 브랜치 받기
				- Pull(Rebase) : Pull을 받으면 리모트를 받아서 로컬과 함치는 Merge라는 버전을 생성하게 됩니다. 이러한 Merge버전없이 바로 뒤에 붙게하는것이 Rebase입니다.
					> git pull --rebase
				- Pull from ... :어떤 브론치에서 받을지 선택하여서 받습니다.
				- push : 같은 브랜치의 remote에 파일을 보냅니다.
				- push to... : 브론치를 선택해서 remote의 해당 브랜치에 넣게 합니다.
				- sync :  둘이 서로 맞추는 것 같은데... 쓰기 겁나서 못써보겠습니다.
				- checkout to ... : 브랜치 바꾸기, 브랜치를 새로 생성할 수도 있습니다.
				- Publish Branch : ?? 몬지 모르겠네.. 감이 안잡힙니다.
				- 이 아래에 있는 commit와 stash기능은 궅이 안하도록 하겠습니다. 그렇게 어렵지 않네요.
		ㄷ. 소스트리
			- 엄청 느리다... 써야하는 걸까? 그래도 사람들이 꽤 쓰는것 같으니 몇 글자 적어본다.
			- 왼쪽의 Hisotry를 클릭하면 commit버전 목록이 쭉 나열되며 commit버전을 클릭하면 그 밑으로 파일과 수정된 소스부분이 나온다.
			- 파일상태를 클릭하면 commit를 할수 있게 해준다.
			- blame는 히스토리를 누른상태에서 파일 선택후에 마우스 오른쪽키에 있는 "선택된 로그"를 선택하면 나온다.
			- 원격 브랜치추가과 폐기는 몬지 모르겠다. rebaseㄴ느 재배치라는 말일까?
	4. 나머지 충돌하는 내역은 툴을 사용하는 것보다는 git bash를 사용하여 cli명령을 내리는게 잘 진행되는 것 같다.
		> 툴들에서는 충돌 날때 어느것으로 수정할수 있는지 선택과 어느 파일이 충돌났는지를 볼수 있는 기능이 있는것 같다. 이걸로 충돌을 대체하는 것 같다.