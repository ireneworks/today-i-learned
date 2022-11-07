# 깃 Git

### git init

> Create an empty Git repository or reinitialize an existing one

새로운 깃 레파지토리를 만들거나, 기존 것을 초기



### git add

> Add file contents to the index

처음/새로 트래킹 할 파일을 추가,  기존 트래킹된 파일 중에서도 선택할 수 있음

```bash
$ git add 추가할 파일
$ git add . //현재 디렉터리의 모든 변경 사항을 추가
```



### git commit

> Record changes to the repository

의미있는 변화인 버전, 작업이 완결된 상태의 버전을 만드는 것

```shell
$ git status //현 파일 상태 확인
$ git add . //현재 디렉터리의 모든 변경 사항을 추가
$ git commit -m "initial commit" //메시지 추가
```

### stage

<figure><img src="../.gitbook/assets/lifecycle.png" alt=""><figcaption><p>File Life Cycle <a href="https://git-scm.com/book/ko/v2/Git%EC%9D%98-%EA%B8%B0%EC%B4%88-%EC%88%98%EC%A0%95%ED%95%98%EA%B3%A0-%EC%A0%80%EC%9E%A5%EC%86%8C%EC%97%90-%EC%A0%80%EC%9E%A5%ED%95%98%EA%B8%B0">1)</a></p></figcaption></figure>

