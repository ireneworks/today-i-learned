# 깃 Git

### git init

> Create an empty Git repository or reinitialize an existing one

새로운 깃 레파지토리를 만들거나, 기존 것을 초기화



### git add

> Add file contents to the index

처음/새로 트래킹 할 파일을 추가,  커밋하고자 하는 파일만 선택

`git add`하면 stage area에 올라감(커밋 대기 상태)

```bash
$ git add <추가할 파일>
$ git add . //현재 디렉터리의 모든 파일 추가
```



### git commit

> Record changes to the repository

의미있는 변화인 버전 또는 작업이 완결된 상태의 버전을 만드는 것

`git commit`을 하면 stage area에 있는 파일들이 새로운 버전

```shell
$ git status //현 파일 상태 확인
$ git add . //현재 디렉터리의 모든 변경 사항을 추가
$ git commit
$ git commit -m "initial commit" //메시지 추가
```



### stage area

<figure><img src="../.gitbook/assets/lifecycle.png" alt=""><figcaption><p>File Life Cycle <a href="https://git-scm.com/book/ko/v2/Git%EC%9D%98-%EA%B8%B0%EC%B4%88-%EC%88%98%EC%A0%95%ED%95%98%EA%B3%A0-%EC%A0%80%EC%9E%A5%EC%86%8C%EC%97%90-%EC%A0%80%EC%9E%A5%ED%95%98%EA%B8%B0">1)</a></p></figcaption></figure>

커밋 대기 상태

stage - repository



### git log

```shell
$ git log //커밋 기록 확인
$ git log -p //각 커밋 별 소스별 차이
```



### git diff

```shell
$ git diff //변경된 파일들과 이전 커밋의 차이
$ git diff <커밋 고유 번호 1>..<커밋 고유 번호 2> 
```



### git reset

```shell
$ git reset <커밋 고유 번호> --hard //돌아가려는 커밋
```

### git revert

