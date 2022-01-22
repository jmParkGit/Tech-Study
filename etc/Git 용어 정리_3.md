# Git 용어 정리_3
## PR(Pull Request)
- 작업내역으 바로 merge하지 않고, 참여하고 있느 프로젝트에 내 작업(branch)를 merge해달라고 요청(Request)를 먼저 보내는 것
- 내가 주인이 아니 다른 repo에 PR을 할려면 fork가 필요

## fork
- fork는 원보 소스코드르 복사해서 새로우 독립적이 소프트웨어로 개발하는 것을 의미

## amend
- 최신으 commit를 수정하는 것을 ammend라고 함.
- ammend로는 가장 최신의 commit만 수정 가능

## revert
- 앞에서 언급한 ammend는 가장 최신의 commit만 되돌리수 있음
- 어떤 내용을 되돌렸는지 새로운 commit을 남기는 것을 revert라고 함.
- 최신 commit뿐만 아니 이전에 했던 commit도 revert로 되돌릴수 있음.

## stash
- 프로젝트 변경사항으 임시적으로 보관할때 사용

## .gitignore
- 공유하거나 공개되면 안되는 파일들은 공개된 repo, 즉, 공개 Github repo에 올라가면 안됨.
- 이 경우 사용하여, 파일들을 없는 것처러 무시하게 하는 설정이 .gitignore
- 파일명을 .gitignore로 만들고 여기에 Git이 무시해야하 파일 또는 폴더이름으 적어주면 됨.
