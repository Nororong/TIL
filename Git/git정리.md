# Day 3 정리

## git
> git이란?
> 분산 버전 관리 시스템

- git은 3개의 영역이 존재
1. working directory
   - 현재 수정, 생성, 삭제된 파일들이 위치한 영역
   - 'git status' 확인할 때 파일이 붉은색으로 표시
      - untracked : 새로 성생된 파일을 의미
      - modified : 수정된 파일을 의미
      - deleted : 삭제된 파일을 의미  
   - 해당 영역에 있는 파일은 commit에 기록되지 않음(staging area로 이동을 시켜야 함)
2. staging area
   - aka. 분류소(버전 관리할 파일)
   - 버전 관리할 파일들을 모아두는 임시 영역
   - 'git status'로 자주 확인할 필요가 있음 
      - new file : 생성된 파일
      - modified : 수정된 파일
3. repository
   - 실제 버전 관리 내용이 저장되는 영역  
   - 'git log'를 이용하여 commit 이력을 확인할 수 있음

### git 기본 명령어

- 'git add 파일명'
   - working directory 에서 staging area로 파일을 이동시키는 명령어
   - 'git add .' : 현재 폴더의 모든 파일과 폴더를 staging area로 이동시킬 수 있음
      - 주의 : 버전 관리가 필요없는 파일이나 폴더가 같이 올라갈 가능성이 있어 반드시 staging area 를 확인해야 함
- 'git commit'
   - commit 이력을 남기는 명령어
   - 반드시 commit 메세지를 남겨야 함
   - git commit -m '메세지' : 해당 옵션으로 간단한 commit 메세지를 남길 수 있음
   > (참고)vim 에디터 간단 사용법
   > vim은 두 가지 모드가 있음
   > 1. command 모드(Esc를 누르면 됨) 
   > 2. editor 모드(i를 누르면 됨) 
   > - 저장(:w), 나가기(:q)
   > - 저장하지 않고 나가기 (:q!)

---
   ## remote repository
   > 원격 저장소
   > - 코드와 버전관리 이력을 온라인 상의 특정 위치에 저장하여 여러 개발자가 협업하고 코드를 공유할 수 있는 저장 공간 ex) github, gitlab

- 'git remote add origin(별명 - github, gitlab) remote_repo_url(원격저장소 주소)'
   - .git/ 폴더에 저장
   - remote 당 원격저장소를 일일이 저장해야 함, 여러 원격저장소 연결 가능

- local -> remote : push라고 함 ex) git push origin
- github repository -> local repository : pull or clone
 - pull : 버전정보(commit)가 있는 상태
   -  방금 first_repo를 ssafy에서 만들었으므로 pull
 - clone(최초 1회) : 버전정보(commit)가 없는 상태
   - clone인 분신을 새로 만든다고 생각하면 됨
   - 집의 컴퓨터에는 아예 아무 것도 없으므로 clone을 만들면 됨
   - 이후에는 push를 하면 됨(commit이 생겼기 때문임)
   - clone을 사용하면 git init이 필요가 없음 
- 버전순서(commit)가 꼬이는 경우가 빈번하게 발생
   - 이 때 pull에서 문제가 발생함 
- push를 하기 전에 pull하는 습관을 들여야 함
---
## 원격저장소에는 commit이 올라가는 것

- 한 사이클
   - 1.pull -> 2.add -> 3.commit -m '메세지'-> 4.push

- gitignore(.gitignore)
   - git 에서 특정 파일이나 디렉토리를 추적하지 않도록 설정하는데 사용되는 텍스트 파일
   - git으로 추적하지 않겠다 (black list 개념임)
   - 프로젝트에 따라 공유하지 않아야 하는 것들도 존재하기 때문임
   - git init을 하고나서 생성하는 것이 좋음
   > commit을 해서 추적등록을 하고나서 gitignore를 하면 블랙리스트가 안 됨

## github 활용
* til(today i learn)을 업로드
   * 매일 내가 배운 것을 마크다운으로 정리해서 문서화하는 것