<https://github.com/kskk7210/SWE_2nd.git>
### SWE_2nd

## git과 gitHub의 사용에 관하여
### git
깃(git)은 프로젝트에 담겨있는 데이터들의 변경사항을 저장하기 위한 용도로 데이터 하나하나, 변경사항 하나하나의 스냅샷(snap shoot)으로 볼 수 있습니다.
### gitHub
깃허브(gitHub)는 깃을 지원하는 원격저장소로 깃의 변경사항등이 저장되고 공유되는 곳이라고 볼 수 있습니다.

> 아래부터 설명될 git과 gitHub는 일련의 흐름에 따라 설명될 것이며 각 명령어의 쉬운 사용부터 옵션 사용까지 볼 수 있습니다. 

### init과 config, clone
위 세 개의 명령어는 프로젝트를 시행하기 전 기본적으로 실행해야하는 명령어라고 할 수 있습니다.
#### init
먼저 init의 경우 로컬저장소로 사용할 폴더를 지정해준 후에 .git 폴더를 생성하여 사용할 수 있게끔 하는 것입니다.
명령어 사용의 경우 아래의 순서를 따르며 실행결과는 다음의 사진과 같습니다.
1. 로컬저장소(local repositoriy)로 사용할 폴더 지정
2. 해당 폴더에서 마우스 우클릭 후 git bash 선택
3. git init 명령어 입력후 실행
4. 해당 폴더에 .git 파일 생성
![git init use](https://user-images.githubusercontent.com/81507012/117341616-5448e180-aedd-11eb-8b90-0da3e935848c.JPG)

#### config
**config**의 경우 깃(git)의 사용환경설정이라고 볼 수 있습니다.

    git config --global
        git config --global user.name 
        git config --global user.email

위와 같은 코드를 이용하여 유저네임(user.name)과 유저이메일(user.email)을 지정하는데 이때 유저 정보는 깃허브(gitHub)가입 정보와 같도록 해줍니다.
global 옵션으로 설정해주는 이유는 사용하는 PC에 모든 저장소에 안정적으로 접근 가능한 설정을 하기 위함이라고 볼 수 있습니다.

아래 콘솔 실행화면을 통해 자세한 코드 입력 방식을 알 수 있습니다.
![config use](https://user-images.githubusercontent.com/81507012/117342820-9a527500-aede-11eb-8669-57ead64bd4aa.JPG)

#### clone
init이 로컬저장소에서 .git을 생성하는 방식이었다면 **clone**의 경우 깃허브(gitHub)에서 저장소(Repository)를 생성하여 로컬저장소로 지정 생성된 폴더에 그대로 내려받는 것입니다.
**clone** 명령어를 사용할 때는 깃허브(gitHub)의 저장소(Ripository) URL을 통해 실행할 수 있습니다.
    git clone RepositoryURL

위와 같은 방식으로 입력하면 아래와 같은 실행 결과를 얻을 수 있습니다. 
![clone use result](https://user-images.githubusercontent.com/81507012/117343322-21075200-aedf-11eb-8352-272c8c1848e8.JPG)
clone 이후 SWE_2nd라는 폴더가 생성된 것을 확인 할 수 있는데 이는 깃허브 저장소(gitHub Repository)의 이름과 같으며 이 안에 .git 파일이 존재합니다.


***


### add, commit 그리고 push
위의 세개의 명령어는 세트처럼 이용합니다. 
파일을 추가하거나 어떤 상태를 변경한 후에 변경된 상태를 추가한다는 의미의 ***add***, 변경사항 내역을 저장하고 이름(메세지, 내역)을 붙여줄 수 있는 ***commit***, 앞서 발생한 사항들을 깃허브 저장소에 올려주는 ***push*** 명령어가 있습니다.

#### add
1. 가장 처음 아무것도 하지 않은 상태에서 로컬저장소를 보면 clone을 통해 내려받은 원격저장소(gitHub Repository) 폴더와 그 안에 생성되어 있는 .git외에는 아무것도 존재하지 않는다.
2. 이 상태에서 임의로 파일 하나를 생성 및 저장한다. (20201378_김유신.md)
3. 2의 과정을 통해 변경사항이 생긴 것이기 때문에 **add** 명령어를 이용하여 변경된 사항들을 모아두어야 한다. 
    기본적으로 git add 명령어를 입력하며
    git add filename 을 입력하여 특정 파일에 대해서 add를 실행하거나
    git add . 을 통해서 폴더에 있는 전체 파일에 대해서 add를 실행할 수 있다.

-add 명령어는 늘 사용되어야 하기 때문에 하나의 활동을 하고 나면 필수적으로 add 명령어를 실행하는 습관을 들일 필요가 있습니다. 필자의 경우 작은 변경사항마다 add 명령어를 실행하고 대체적으로 filename을 입력하는 코드보다는 .(점)을 찍어 한 번에 파일을 올리는 코드를 자주 사용하게 될 것 같습니다.

#### commit
*add*가 진행되고 나면 그 후에 해주는 것이 바로 이 **commit**입니다.
-**commit**은 변경사항을 저장하는 역할을 합니다. *add*를 통해 모아둔 변경사항을 *commit*을 통해 저장한다고 보면 됩니다.
-*commit*의 경우 변경 내역을 지칭하는 메세지를 덧붙일 수 있습니다.
    git commit -m 여기서 -m이 메세지를 덧붙이는 옵션이며
    예를들어
        git commit -m"Add MarkDown File [20201378_김유신.md]"
    와 같은 코드의 경우 메세지 Add MarkDown File에 해당하는 파일이 [] 대괄호 안에 있는 파일임을 명시합니다.

1. 앞서 변경사항에 대한 add가 진행되었으며 변경사항을 저장해야한다.
2. git commit 명령어를 입력하여 변경사항을 저장한다.
3. commit의 옵션 중 가장 많이 사용하게 되는 것은 아마 amend 옵션이 될 것이다. 
    git commit --amend
방식으로 사용되는 명령어 옵션으로 이미 작성한 commit의 메세지를 바꾸고 싶을 때 사용한다.

#### push
**push**명령어의 목적은 저장된 변경사항들을 원격저장소로 보내는 것입니다. 
1. 앞서 add와 commit 명령어를 통해 변경사항이 저장되었다.
2. 원격저장소와 로컬저장소가 같지 않은 상태이다.
3. *push*명령어를 통해 로컬저장소의 변경사항들을 원격저장소로 보낸다.
   
    git push
라는 입력방식을 따르며 명령어 작업 이후 깃허브 저장소에서 새로고침을 하게 되면 로컬저장소와 똑같이 반영되어있는 사항들을 확인할 수 있습니다.

-*push* 명령어의 옵션 중 가장 자주 사용하게 되는 것은 강제 push 옵션으로
    git push -f
위와 같은 형태로 사용되며 보통 reset을 진행한 후 사용하게 됩니다. ~~(이 옵션의 경우 reset 명령어를 익힌 후 뒤에서 더 살펴보도록 하겠습니다.)~~


-아래는 *add, commit, push*의 명령어 실행 및 결과가 반영된 모습입니다.
![add commit push test use](https://user-images.githubusercontent.com/81507012/117348370-1485f800-aee5-11eb-8005-5381d3a3ac12.JPG)
-사진을 보면 처음 로컬저장소에 md파일이 추가되었고 add 명령어 입력 후에 commit 명령어로 변경사항을 저장해주었고 마지막에 push 명령어를 사용함으로 원격저장소에 변경사항이 반영된 상태입니다.

-아래 사진은 *commit -amend* 명령어 옵션의 사용으로 변경된 commit 메세지와 원격저장소에 반영된 상태입니다.
![file modify](https://user-images.githubusercontent.com/81507012/117349382-4a77ac00-aee6-11eb-8481-6a9c20aaeb7c.JPG)
![commit -amend use](https://user-images.githubusercontent.com/81507012/117349402-4ea3c980-aee6-11eb-89f5-532606b35410.JPG)
    ㅡModify contents [20201378_김유신.md] 였던 commit 메세지가
      Mofify md code [20201378_김유신.md]로 바뀐 것을 확인할 수 있습니다.


***

### status와 log
두 명령어 모두 무언가를 확인하려고 사용한다는 점에서 비슷하지만 명령어 실행결과가 다르고 옵션으로 응용되는 범위가 다릅니다.

#### status
**status**명령어는 현재상태를 보고자 할 때 사용됩니다.
1. 만약 이미 add commit push를 마친 파일을 수정했고
2. 수정이 되었는지 유무에 대해 확인을 하고 싶을 때 사용된다.
    git status
라는 명령어 입력을 하면 현재 상태를 알려주기 때문에 파일을 수정한 직후라면 아래와 같이 mofified라고 알려주게 됩니다. 
![status use](https://user-images.githubusercontent.com/81507012/117350523-a1ca4c00-aee7-11eb-89d5-485b327b1e73.JPG)

-status 명령어를 통해 현재 상태를 알게 되면 추가 변경사항의 유무를 쉽게 파악할 수 있기 때문에 이후 add와 같은 활동이 더 필요한지 파악하기 쉽습니다. 

#### log
status는 현재 상태를 알려주지만 **log**명령어를 실행할 경우 그동안의 commit의 흔적을 모두 볼 수 있습니다. 
1. 그동안 얼만큼의 commit을 진행했는지 알고 싶거나
2. 얼만큼의 변경사항이 존재하고 특정 commit의 해시값이 필요할 경우
3. log 명령어를 사용한다.
    git log // 기본형태
    git log --graph //branch와 병합정보 (branch또한 뒤에서 다룰 예정)
    git log --pretty //형식을 지정하여 해시값, 작성자이름, 작성날짜 등을 출력
기본형태와 그에 따른 옵션이 여러가지 있는데 가장 자주 사용하게 된 것은 graph였고 보다 능숙해진다면 형식을 지정하여 여러 방식으로 log를 볼 수 있는 pretty 옵션의 사용 빈도가 높아질 것입니다. 

-아래 화면은 옵션없이 log 명령어만을 실행했을 때 볼 수 있는 화면입니다.
![log use](https://user-images.githubusercontent.com/81507012/117352844-6bda9700-aeea-11eb-87c3-38dd074525ed.JPG)


***


### reset option
#### reset (reset --hard)
**reset**은 이전 commit의 진행 위치로 돌아가고 싶을 때 사용하는 명령어입니다
1. 이미 진행된 commit이 있다.
2. 앞서 진행된 commit 중에 되돌아가고자 하는 상태의 commit이 존재한다.
3. 이 경우 **reset** 명령어를 사용하여 되돌아갈 수 있다. 

-*reset*은 함께 사용하는 옵션마다 붙는 조건이 조금씩 다릅니다.
    git reset 
    git reset --soft commit해시값 //해당 commit 값으로 돌아간 이후에도 이전 commit 보관
    git reset --hard commit해시값 //돌아가고 나면 이후 commit 전부 삭제

-*reset --hard*를 사용할 경우 되돌아가기로 지정된 해시값 이후의 commit은 전부 삭제되어 다시 되돌아갈 수 없습니다. 또한 reset으로 되돌아간 commit값 상태에서도 원격저장소로 push가 필요합니다. 하지만 이 상태에서는 push가 정상적으로 작동하지 않기 때문에 위에서 봤던 강제 push의 방법인 *push -f*를 이용해야합니다.

-아래 사진은 reset을 진행하여 *Modify md code* 메세지를 가진 내용이 추가된 파일에서 *Add MarkDown File* 메세지를 가진 내용 없이 추가된 파일의 commit 상태로 돌아갔기 때문에 MarkDown File에 아무것도 없는 것을 확인할 수 있습니다.
![reset--hard use](https://user-images.githubusercontent.com/81507012/117354698-9e858f00-aeec-11eb-8b45-59a8e819ee3f.JPG)

-아래 사진은 reset 이후 push -h가 진행되어 원격저장소에 변경사항이 반영된 상태입니다.
![push -h](https://user-images.githubusercontent.com/81507012/117354823-c5dc5c00-aeec-11eb-9ac8-8e11ea08b2ce.JPG)


***


### branch, merge 와 checkout
위의 명령어를 통해 branch를 생성하고 branch head를 변경하며 branch를 합칠 수 있습니다.

#### branch
**branch**란 여러 개발자가 동시에 작업을 할 수 있도록 도와주는 기능입니다. 각 다른 **branch**를 가지고 동시에 여러작업을 수행하다가 나중에 하나로 병합을 할 수 있습니다.
1. 여러사람이 같은 내용을 기반으로 동시에 다른 작업을 한다.
2. 용도를 나누어야 하며 나중에 합쳐서 배포할 예정이다.
3. 위와 같은 상황일 경우 branch를 생성한다.
명령어로는
    git branch
라는 형태로 사용하는데 별다른 옵션없이 입력하면 현재 생성되어 있는 branch와 branch의 head가 어디에 지정되어 있는지 알 수 있습니다. 
    git branch develop // develop이라는 이름의 branch를 생성
    git branch -d //비어있는 branch 제거

혼자서 아직 깊은 작업을 해본 적이 없는 경우 (본인포함) branch의 필요성을 느끼지 못할 수도 있으나 다수가 작업하거나 서브로 수정하고 작업할 공간이 필요할 경우 branch를 생성하여 활동을 수행하고 나중에 병합할 수 있습니다.

#### checkout
1. 현재 문서의 head가 master branch로 설정되어 있다.
2. 작업을 위해서는 따로 생성한 branch로 head를 옮기고 싶다.
3. 혹은 merge를 수행하기 위해 head를 다시 master branch로 옮기고 싶다.
4. 이 경우 **checkout**명령어를 사용하여 head 위치를 움직일 수 있다.
    예를 들어 master branch가 존재하고 new라는 branch를 생성
        git checkout new // git checkout (head를 옮기고자하는 branch)
    위와 같이 설정을 하면 head가 new라는 branch로 옮겨가고 수행하는 작업의 변경사항들이 new에 저장되게 됩니다.

-아래 사진은 다른 수정 작업을 위해 new라는 branch를 생성하여 head를 옮기고 branch의 상태를 확인하고 작업을 수행하는 명령어입니다. 
![branch checkout](https://user-images.githubusercontent.com/81507012/117358833-911ed380-aef1-11eb-9855-bcc2e13e29e8.JPG)


#### merge
-**merge**는 나누어져있던 *branch*를 병합할 때 사용됩니다. 
-**merge**가 수행되고자 하는 branch로 head를 옮겨야하며 보통 master branch에서 merge가 이루어집니다.

1. 이미 생성된 branch에서의 작업이 끝났다.
2. branch에 추가한 작업을 한 데 묶어야 한다.
3. 이때 merge 명령어를 사용하여 병합

    git checkout master //head를 master branch로 변경
    git merge new //new branch를 head branch에 merge
merge가 끝나고 난 뒤에는 해당 변경사항을 push를 통해 원격저장소에 반영해야하며 merge를 하고 비어버린 branch new는 *git branch -d new*로 제거해줘야합니다.

-아래는 merge를 통한 branch 병합 과정과 push를 통해 원격저장소에 반영된 결과를 나타낸 화면입니다. 
![merge use](https://user-images.githubusercontent.com/81507012/117359092-e65ae500-aef1-11eb-9a2d-7258582d19c1.JPG)
![branch merge push result](https://user-images.githubusercontent.com/81507012/117359112-ebb82f80-aef1-11eb-95a2-d514b9100367.JPG)

-merge, push가 모두 끝난 후 빈 branch new를 제거하고 확인하는 명령어 화면입니다. 
![branch delete](https://user-images.githubusercontent.com/81507012/117359305-29b55380-aef2-11eb-8b13-bd518e70020b.JPG)


***


### remote 와 pull
#### remote
remote는 저장소와 관련된 명령어입니다. 
    git remote //원격저장소 확인

**remote rename**을 사용할 경우
1. 저장소가 여러개 있다.
2. 편의를 위해 저장소 이름을 변경하고 싶다.
    git remote rename 원래저장소이름 변경하고자하는이름
3. 위와 같은 명령어로 저장소 이름 변경
   
-아래 사진 속 콘솔의 명령어와 같이 사용하여 기본으로 지정되어 있는 저장소 origin의 이름을 바꿀 수도 있습니다.
![remote rename ](https://user-images.githubusercontent.com/81507012/117361994-b4e41880-aef5-11eb-9c7a-f760c65a6dc0.JPG)

**remote add**를 사용할 경우
-저장소를 더 추가하여 사용할 수도 있는데 이 경우 remote 명령어를 이용하여 저장소를 추가할 수도 있습니다.
    git remote add name URL
위와 같은 명령어를 통해 원격저장소 추가 또한 가능합니다.
-추가한 저장소를 제거할 경우 
    git remote rm name
명령어를 사용하여 해당 name의 저장소를 제거할 수 있습니다.

#### pull
**pull**은 *push*와 반대 개념으로 볼 수 있습니다. push가 로컬저장소에서 원격저장소로 보낸다면 **pull**은 원격저장소에서 로컬저장소로 보내게 됩니다.
이를테면
1. 깃허브에서 README 파일을 생성했다.
2. 이 README 파일을 로컬저장소에서 저장하여 수정해야 한다.
    git pull
명령어를 통해서 원격저장소에 있던 변경사항, 파일들을 데려와 로컬저장소에서 작업할 수 있게 됩니다.

예를 들어 현재 작성중인 README 파일 또한 명령어 *pull*을 이용하여 로컬저장소로 내려받아 수정하여 후에 변경사항을 add commit한 후 push를 통해 다시 원격저장소에 보내 예정인 것처럼 이런 상황에서 작업이 필요할 때 pull 명령어를 유용하게 사용할 수 있습니다. 

-아래 사진은 원격저장소에 있는 것을 로컬저장소로 가져올 때 쓰이는 명령어와 결과 입니다. 
![git pull use](https://user-images.githubusercontent.com/81507012/117361161-a2b5aa80-aef4-11eb-9a36-616bbf40289a.JPG)


***


### rebase와 tag
#### rebase
**rebase**는 commit를 변경할 수 있다는 점에서 *commit --amend*와 비슷해보일 수 있으나 사용환경이나 기능이 더 확장되어 있다고 볼 수 있습니다.
-rebase의 경우 앞선 commit의 내역을 변경하고 필요없는 것이 생겨 지워버려야할 경우 사용하기 좋습니다. 
    git rebase //commit 내역 추정
    git rebase -i HEAD ~number //interaction editor로 열어 편집

위 명령어를 실행하면 아래 사진과 같은 결과를 얻을 수 있습니다. (아래 사진은 HEAD ~3 명령어를 입력하여 commit 3줄)
![rebase i editor](https://user-images.githubusercontent.com/81507012/117362308-0db3b100-aef6-11eb-811b-554c525826d1.JPG)
-아래로 *reword, drop* 등등 commit 앞의 pick이라는 키워드를 원하는 사항을 수행하는 키워드로 바꾸면 편집이 가능합니다.
~~(rebase의 reword를 통해 commit 내역을 변경하고자 했으나 오류 및 충돌로 인해 editor 빠져나오기에 실패)~~

#### tag
변경사항의 내역을 commit을 통해 정리하고 저장하고 있지만 보다 중요한 commit일 경우 tag를 붙이기도 합니다. commit을 참조하기 쉽도록 붙이는 경우도 있습니다.
1. README 파일을 로컬저장소에서 수정하고 저장한 것
2. pull로 받은 파일을 push로 올린다는 점
3. 위와 같은 이유로 중요하다 판단되어 tag 설정
   
-**tag**에는 *lightweight tag*로 이름만 명시가 가능한 것, *Annotated tag*로 이름 뿐만 아니라 설명과 이름, 날짜 정보가 포함가능한 것이 있습니다.
    git tag //포함된 tag 조회
    git tag tagname //lightweight tagfh tagname 붙이기 가능

-아래 사진은 *lightweight tag*로 처음 붙인 tag라는 의미로 *v1.1* 이름의 tag를 붙인 것과 기본 명령어로 tag를 조회한 입력입니다.
![lightweight tag](https://user-images.githubusercontent.com/81507012/117363555-b1ea2780-aef7-11eb-8f46-1f0da7987cb9.JPG)
![tag show](https://user-images.githubusercontent.com/81507012/117363571-b7e00880-aef7-11eb-83d6-b73e0d7364ee.JPG)

