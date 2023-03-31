---
title: "Quartz를 이용해 옵시디언을 깃헙페이지로 올리기"
---

## 선행 지식

git, github, obsidian

## 순서

[매뉴얼](https://quartz.jzhao.xyz/notes/setup/)

1. https://github.com/jackyzha0/quartz 을 fork 한다. (주의! uncheck the ‘Copy the `hugo` branch only’ option)

![[notes/images/Pasted image 20230331192247.png]]

2. fork 한 리포지토리를 clone 한다.  `> git clone 깃 주소`

3. '보관서 폴더 열기' 우측의 '열기' 버튼을 눌러 /content 폴더를 선택한다.

![[notes/images/Pasted image 20230331192856.png]]

4. `_index` 파일과 3개 폴더가 만들어져 있다. 

![[notes/images/Pasted image 20230331193216.png]]

5. Obsidian 링크 설정

![[notes/images/Pasted image 20230331224707.png]]

6. 새 파일을 만들 때마다 문서 상단에 yml 설정 문구 넣는 템플릿 사용

![[notes/images/Pasted image 20230331210814.png]]
![[notes/images/Pasted image 20230331214132.png]]
7. 로컬에서 미리보기하기 위해 go 언어를 설치한 뒤 hugo-obsidian 설치

```shell
> brew install go
> go install github.com/jackyzha0/hugo-obsidian@latest 
```

8. `hugo-obsidain` 파일 경로를 path에 추가 ( 맥: .zshrc 파일에 추가)  `export PATH="$PATH:Users/계정/go/bin"`

9. quartz 폴더 안에서 `make serve 실행` → http://localhost:1313

10. Github Actions 권한 부여: Github → Settings → Actions → General → Workflow permissions

![[notes/images/Pasted image 20230331215923.png]]

11. Github pages 설정: Github → Settings → Pages → Branch

![[notes/images/Pasted image 20230331220230.png]]

12. Github에 올리기

```shell
> git add .
> git commit -m "message"
> git push origin hugo
```

13. config.toml 파일의 baseURL에 깃허브 주소 입력하기. 주소 끝에 '/'를 꼭 붙여야 함.
14. deploy.yaml 파일의 cname에 깃허브 주소 입력하기. 주소 끝에 '/'를 붙이면 안 됨