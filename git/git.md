# GIT 기초

> Git은 분산형 버전관리시스템(DVCS)이다.

Git을 윈도우에서 활용하기 위해서는 git bash 설치

## 1. 저장소 초기화

```bash
$ git init
Initialized empty Git repository in C:/Users/i/Desktop/TIL/.git/

(master) $
```

- 로컬 저장소를 만들고 나면 `.git/` 폴더가 생성되고, bash에 (master)라고 표기 된다.
- 반드시 저장소를 만들기 전에 원하는 디렉토리인지 확인하는 습관을 가지고, 저장소 내부에 저장소를 만들기 X
  - 예) Desktop -> git 저장소, Desktop/TIL -> 다른 git 저장소 (X)

## 2. add

작업한 내용을 커밋 대상 목록에 추가하는 명령어

```bash
# 작업 후 상태
$ git status
On branch master

No commits yet

Untracked files:
# Untracked files => Git으로 관리된적 없는 파일
  (use "git add <file>..." to include in what will be committed)
        git.md
        markdown-images/
        markdown.md

nothing added to commit but untracked files present (use "git add" to track)
```

```bash
$ git add .
```

```bash
# add 명령어 시행 후 상태
$ git status
On branch master

No commits yet

Changes to be committed:
  (use "git rm --cached <file>..." to unstage)
        new file:   git.md
        new file:   markdown-images/img.jpg
        new file:   "markdown-images/\354\272\241\354\262\230.PNG"
        new file:   markdown.md
```

## 3. commit

```bash
$ git commit -m 'Add markdown.md'
[master (root-commit) ccd5fa4] Add markdown.md
 4 files changed, 104 insertions(+)
 create mode 100644 git.md
 create mode 100644 markdown-images/img.jpg
 create mode 100644 "markdown-images/\354\272\241\354\262\230.PNG"
 create mode 100644 markdown.md
```

- 커밋은 버전(이력)을 기록하는 명령어
- 커밋 메시지는 해당하는 이력을 나타낼 수 있도록 작성

```bash
# 커밋 이력을 확인하기 위한 명령어
$ git log
commit ccd5fa4592b01f6ab01e76432c4f606fb680ee23 (HEAD -> master)
Author: SongJaegeun <s930925@naver.com>
Date:   Thu Aug 20 14:58:08 2020 +0900

    Add markdown.md
    
$ git log -1
commit ccd5fa4592b01f6ab01e76432c4f606fb680ee23 (HEAD -> master)
Author: SongJaegeun <s930925@naver.com>
Date:   Thu Aug 20 14:58:08 2020 +0900

    Add markdown.md

$ git log --oneline
ccd5fa4 (HEAD -> master) Add markdown.md

$ git log --oneline -1
ccd5fa4 (HEAD -> master) Add markdown.md

```

- 커밋 후에는 다음과 같은 상태로 변경

```bash
$ git status
On branch master
nothing to commit, working tree clean
```







