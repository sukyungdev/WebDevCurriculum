# Quest 00. 형상관리 시스템

## Introduction

-   git은 2021년 현재 개발 생태계에서 가장 각광받고 있는 버전 관리 시스템입니다. 이번 퀘스트를 통해 git의 기초적인 사용법을 알아볼 예정입니다.

## Topics

-   git
    -   `git clone`, `git add`, `git commit`, `git push`, `git pull`, `git branch`, `git stash` 명령
    -   `.git` 폴더
-   GitHub

## Resources

-   [Resources to learn Git](https://try.github.io)
-   [Learn Git Branching](https://learngitbranching.js.org/?locale=ko)
-   [Inside Git: .Git directory](https://githowto.com/git_internals_git_directory)

## Checklist

-   형상관리 시스템은 왜 나오게 되었을까요?

    ```
    형상관리 시스템이 나오기 전에는 파일을 이용하여 버전 관리를 했었다.

    > 파일 관리 시스템의 단점

    1. 코드를 여러명이 동시에 개발하고 합치는 것이 번거롭다.
    2. 이전 데이터로 복구할 수 없다.
       (각각의 버전을 따로 저장해서 보관해야 한다.)
    3. 변경 사항을 관리하는 것이 매우 불편하다.

    이와 같은 단점을 보완하고자 나온것이 형상관리 시스템이다.

    > 형상관리 시스템의 장점

    1. 이전 데이터 복귀 가능.
    2. 동시에 한 파일로 협업 가능.
    3. 변경 사항을 관리하는 것에 특화되어 있다.
    4. 파일이 삭제될 경우를 대비한 backup 가능.
    ```

-   git은 어떤 형상관리 시스템이고 어떤 특징을 가지고 있을까요? 분산형 형상관리 시스템이란 무엇일까요?

    > git은 분산관리식의 형상관리 시스템이다.

    git의 특징

    ```
    1. 분산적 개발
    2. 효율적 개발
    3. 비선형적 개발
    4. 변경이력 보장
    5. git 호스팅 서비스(Github, Bitbucket, GitLab)
    ```

    [[Git] 1. Git이란?(입문)](https://linked2ev.github.io/devlog/2018/08/27/Git-1.-What-is-Git/)

    분산형 형상관리 시스템이란?

    > 형상관리 시스템에는 대표적으로 중앙집중식의 svn과 분산관리식의 git이 있다.  
    > 분산형 형상관리 시스템은 소스코드를 여러 곳에 분산하여 저장한다.  
    > 때문에 중앙서버에 문제가 생길 경우 유연하게 대처가 가능하고, 협업에 유리하다.  
    > (병렬적인 작업이 가능)  
    > [[간단정리] Git, SVN 특징 및 차이점](https://hahahoho5915.tistory.com/40)  
    > [[git] git이란? (형상관리, 정의, 장단점, 설치)](https://velog.io/@lazysia/git-git)

-   git은 어떻게 개발되게 되었을까요? git이 분산형 시스템을 채택한 이유는 무엇일까요?

    git의 개발 배경  
    [짧게 보는 Git의 역사](https://git-scm.com/book/ko/v2/%EC%8B%9C%EC%9E%91%ED%95%98%EA%B8%B0-%EC%A7%A7%EA%B2%8C-%EB%B3%B4%EB%8A%94-Git%EC%9D%98-%EC%97%AD%EC%82%AC)

    git이 분산형 시스템을 채택한 이유?

    > git은 빠른속도와 비선형적인 개발, 완벽한 분산을 목표로 만들어진 시스템이기 때문에
    > 이러한 목표를 이루기 위해 분산형 시스템을 채택했다.

-   git과 GitHub은 어떻게 다를까요?

    > git은 소스코드를 관리하는 분산 버전 관리 시스템
    > github는 git으로 관리하는 git 파일은 업로드 하는 장소.(웹호스팅도 제공)

-   git의 clone/add/commit/push/pull/branch/stash 명령은 무엇이며 어떨 때 이용하나요? 그리고 어떻게 사용하나요?

<<<<<<< HEAD
=======
    -   git clone : 원격 저장소를 로컬에 복제해오는 명렁어

    ```
    git clone [원격 저장소 주소]
    ```

    -   git add : 작업 디렉토리(working directory)상의 변경 내용을
        스테이징 영역(Staging Area)에 추가하는 명령서

    ```
    git add
    git add.
    git add -A
    git add -p
    git add -u
    ```

    [git add 기본 개념/사용법](https://www.daleseo.com/git-add/)
    [git add -A 와 git add .의 차이](https://github.com/sukyungdev/TIL/blob/main/git_github/git_add.md)

    -   git commit : 로컬에 변경 사항을 기록하는 명령어

    ```
    git commit
    git commit -m "커밋 메세지를 간단하게 작성할때 사용한다"
    ```

    -   git push : commit으로 인한 기록을 원격 저장소에 저장하는 명령어

    ```
    git push [원격저장소][브랜치명]
    ```

    [What are the differences between "git commit" and "git push"?](https://stackoverflow.com/questions/2745076/what-are-the-differences-between-git-commit-and-git-push)

    -   git pull : 원격 저장소에서 로컬 저장소로 코드를 가져오는 명령어
        > fetch와 비슷하나 merge를 하고 안하고에 따른 차이가 있다.

    ```
    git pull [원격저장소][브랜치명]
    ```

    [pull과 fetch의 차이는 무엇일까?](https://devlog-wjdrbs96.tistory.com/236)

    -   git branch : 동시에 다양한 작업을 할 수 있는 개별적인 작업공간인 branch를 만드는 명령어.

    ```
    git branch [브랜치명]
    ```

    [3.1 Git 브랜치 - 브랜치란 무엇인가](https://git-scm.com/book/ko/v2/Git-%EB%B8%8C%EB%9E%9C%EC%B9%98-%EB%B8%8C%EB%9E%9C%EC%B9%98%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%B8%EA%B0%80)

    -   git stash : 변경사항을 임시로 저장하는 명령어

    ```
    git stash
    git stash -m "메세지 입력 가능"
    ```

    [7.3 Git 도구 - Stashing과 Cleaning](https://git-scm.com/book/ko/v2/Git-%EB%8F%84%EA%B5%AC-Stashing%EA%B3%BC-Cleaning#_git_stashing)

>>>>>>> d4ae4af (Add content_20220802)
-   git의 Object, Commit, Head, Branch, Tag는 어떤 개념일까요? git 시스템은 프로젝트의 히스토리를 어떻게 저장할까요?
-   리모트 git 저장소에 원하지 않는 파일이 올라갔을 때 이를 되돌리려면 어떻게 해야 할까요?

## Quest

-   GitHub에 가입한 뒤, [이 커리큘럼의 GitHub 저장소](https://github.com/KnowRe-Dev/WebDevCurriculum)의 우상단의 Fork 버튼을 눌러 자신의 저장소에 복사해 둡니다.
-   Windows의 경우 같이 설치된 git shell을, MacOSX의 경우 터미널을 실행시켜 커맨드라인에 들어간 뒤, 명령어를 이용하여 복사한 저장소를 clone합니다.
    -   앞으로의 git 작업은 되도록 커맨드라인을 통해 하는 것을 권장합니다.
-   이 문서가 있는 폴더 바로 밑에 있는 sandbox 폴더에 파일을 추가한 후 커밋해 보기도 하고, 파일을 삭제해 보기도 하고, 수정해 보기도 하면서 각각의 단계에서 커밋했을 때 어떤 것들이 저장되는지를 확인합니다.
-   `clone`/`add`/`commit`/`push`/`pull`/`branch`/`stash` 명령을 충분히 익혔다고 생각되면, 자신의 저장소에 이력을 push합니다.

## Advanced

-   Mercurial은 어떤 형상관리 시스템일까요? 어떤 장점이 있을까요?
-   실리콘밸리의 테크 대기업들은 어떤 형상관리 시스템을 쓰고 있을까요?
