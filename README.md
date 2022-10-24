# study_first
my study file
readme 설명
  ## git remote add 과정에서 다음과 같은 오류가 발생하였다

  ### 원을을 파악하고 해결(조치) 방법은 제시하시오

  #### 오류 코드 : fatal: not a git repository (or any of the parent directories): .git
***
    -원인 : git repository로 사용하기 위한 초기화 작업이 진행되지 않은 상태 오류
    1. 해당 디렉토리에 .git폴더가 있는지 여부 확인
    2. $ git init 명령어로 초기화 및 기본 설정 폴더인 .git 디렉토리 생성
   ![6](https://user-images.githubusercontent.com/105694802/197465559-56a56745-ea6c-4795-9ad0-e6bc7424d68b.jpg)
   ![6-1](https://user-images.githubusercontent.com/105694802/197465831-b1c8d3f9-1812-4a51-99f6-26571b09f7fc.jpg)


***


  ## git remote add 과정에서 다음과 같은 오류가 발생하였다

  ### 원을을 파악하고 해결(조치) 방법은 제시하시오

  #### 오류 코드 :error. failed to push some refs to '~~~'
  #### hint: Updates were rejected because the tip of your current branch is behind

* 원인 현재 작업중인 저장소가 서버에 있는 저장소보다 오래된 내용이기에 발생하는 에러.
* Push를 할 경우 현 서버의 최신 내용이 날라갈 수 있기에 에러가 발생함.
* github remote에 있는 코드에 변경사항이 있으면 현재 upload하려는 코드와 불일치해서 push reject가 된다

*****
*문제 해결*
1. $git pull 을 해준뒤 다시 push 해준다

2. git pull origin 명령어를 통해 반영 후 push 명령어를 사용하면 정상적으로 저장소에 업로드 됨을 확인 가능하다.

그럼에도 오류가 난다면 

강제 push 기존 작업물 유실 주의
push 하려고하는 브랜치 이름 앞에 +를 분여 push 하면 된다

![7-1](https://user-images.githubusercontent.com/105694802/197466299-0df3fa98-295d-4ab7-9e04-0653218cfba1.jpg)
![7-2](https://user-images.githubusercontent.com/105694802/197466303-cb3db23d-6423-4fc0-b8af-2a58652c0cd6.jpg)

***


  ## git remote add 과정에서 다음과 같은 오류가 발생하였다

  ### 원을을 파악하고 해결(조치) 방법은 제시하시오

  #### error. failed to push some refs to '~~~'
  #### hint: Updates were rejected because the remote contains work that you do not have locallyt

    * 원인 : 원인 github에서 레파지토리를 생성할 때 README.md 파일을 생성했기 때문

    *문제 해결*
    1. git pull명령어로 원격 레파지토리를 내 로컬로 fetch한 다음 merge 한다 -git pull origin master

    2. git pull origin master(or branch name) --allow-unrelated-histories
       git status로 확인
       git add .
       git push -u origin master로 커밋
