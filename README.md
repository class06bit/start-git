# start-git

## add&commit
```
git add 파일명
git commit -m "메시지"
```

###  ~/.gitconfig 
```
git config --global user.name "자신의 닉네임"
git config --global user.email "자신의 이메일"
```
### 확인&비교
```
git log -p #로그에서 출력되는 버전 간의 차이점을 출력하고 싶을 때
git log --reverse # 거꾸로 
git reflog 
git diff '버전 id'..'버전 id2' # 버전 간의 차이점을 비교할 때
git diff # git add하기 전과 add한 후의 파일 내용을 비교할 때 (마지막 확인!)
```
### add 취소
```
git reset --hard `버전id` # 버전 id로 돌아가는 명령
git revert `버전id` # 버전 id의 커밋을 취소한 내용을 새로운 버전으로 만드는 명령
```
```
# test.txt 에 대한 add 명령을 취소한다.
git reset test.txt
```
### 마지막 커밋 메시지를 수정
```
git commit --amend

git add file1.txt
git commit
# realize you forgot a file
git add file2.txt
git commit --amend --no-edit
```
---
## git branch
### branch 확인
```
git branch
* master
```
### branch 만들기
```
git branch ex
git branch
  ex
* master # 현재 사용중이 브랜치
```
### branch 전환
```
git checkout ex
  Switched to branch 'ex'
git branch
* ex
  master
```
### branch 삭제
```
git branch -d ex
  Deleted branch ex
```
#### 강제삭제
```
git branch -D 'ex'
  Deleted branch ex
```
### branch 비교
```
git log "브랜치명".."비교할 브랜치명"
```
#### 코드비교
```
git diff "브랜치명".."브랜치명"
```

#### 표로 비교
``` git log --branches --graph --decorate --oneline ```

---

## 병합
### merge
```
git checkout master
git merge sec
```
### 충돌확인
``` git status ```
---
## 원격저장소
### 가져오기
``` git clone https://github.com/git/git.git 폴더이름 ```
### remote 저장소 설정
``` git remote add origin https://github.com/~ ```
### remote 변경
```
# 현재 원격 저장소 상태 확인
git remote -v
# 변경하고자 하는 원격저장소 설정
git remote set-url origin https://github.com/~
```
### remote Push
```
git push -u origin master
```
### 동기화
```
git fetch origin
git pull
```
---
## pull request
1. Fork
2. clone, remote설정
3. branch 생성
4. 수정 작업 후 add, commit, push
5. Pull Request 생성
6. 코드리뷰, Merge Pull Reqest
7. Merge 이후 branch 삭제 및 동기화
### 설정
```
# fork후
git clone (Fork한 본인 저장소)
# 원본 프로젝트 저장소를 원격 저장소로 추가
git remote add origin(별명) (원본 프로젝트 저장소)
# 원격 저장소 설정 현황 확인방법
git remote -v
```
### push
```
git checkout -b develop
git add
# develop 브랜치의 수정 내역을 origin 으로 푸시
git push origin develop
```
### 본인 계정 접근
``` 
Compare & pull reqeust 버튼이 활성화 -> click 
PR을 생성
원본 저장소 관리자 -> Merge 여부를 결정
```

### 후행작업
```
# 코드 동기화
git pull real-blog(remote 별명)
# 브랜치 삭제
git branch -d develop(브랜치 별명)
```




