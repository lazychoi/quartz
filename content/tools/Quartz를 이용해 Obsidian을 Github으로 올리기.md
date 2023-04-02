---
title: "Quartz를 이용해 Obsidian을 Github으로 올리기"
---

## 선행 지식

git, github, obsidian

## 절차 

### 매뉴얼

- https://quartz.jzhao.xyz/notes/setup/
- [[tools/Quartz documents]]

### Quartz 소스 가져오기

1. https://github.com/jackyzha0/quartz 을 fork 한다. (주의! uncheck the ‘Copy the `hugo` branch only’ option)

![[tools/images/Pasted image 20230331192247.png]]

2. fork 한 리포지토리를 clone 한다.  `> git clone 깃 주소`
3. config.toml 파일의 baseURL에 깃허브 주소 입력하기. 주소 끝에 '/'를 꼭 붙여야 함.
4. deploy.yaml 파일의 cname에 깃허브 주소 입력하기. 주소 끝에 '/'를 붙이면 안 됨. 

### Obsidian vault 만들고 설정하기

1. '보관서 폴더 열기' 우측의 '열기' 버튼을 눌러 /content 폴더를 선택한다.

![[tools/images/Pasted image 20230331192856.png]]

2. `_index` 파일과 3개 폴더가 만들어져 있다. 

![[tools/images/Pasted image 20230331193216.png]]

3. Obsidian 링크 설정

![[tools/images/Pasted image 20230331224707.png]]

4. 새 파일을 만들 때마다 문서 상단에 yml 설정 문구 넣는 템플릿 사용

![[tools/images/Pasted image 20230331210814.png]]
![[tools/images/Pasted image 20230331214132.png]]

### 작성한 파일 미리보기

1. 로컬에서 미리보기하기 위해 go 언어를 설치한 뒤 hugo-obsidian 설치

```shell
> brew install go
> go install github.com/jackyzha0/hugo-obsidian@latest 
```

2. `hugo-obsidain` 파일 경로를 path에 추가 ( 맥: .zshrc 파일에 추가)  `export PATH="$PATH:Users/계정/go/bin"`

3. quartz 폴더 안에서 `make serve 실행` → http://localhost:1313

### Github 설정 및 파일 업로드

1. Github Actions 권한 부여: Github → Settings → Actions → General → Workflow permissions

![[tools/images/Pasted image 20230331215923.png]]

2. Github pages 설정: Github → Settings → Pages → Branch

![[tools/images/Pasted image 20230331220230.png]]

3. Github에 올리기

```shell
> git add .
> git commit -m "message"
> git push origin hugo
```

