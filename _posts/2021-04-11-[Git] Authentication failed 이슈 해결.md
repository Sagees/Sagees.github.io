---
title: "Authentication failed 이슈 해결"
date: 2021-04-11
categories: Git
toc: true
toc_sticky: true
---

<span style="color:blue">**현재 git 사용 환경 : VS Code & Git Bash (Windows 10)**</span>

Git을 사용할 때, 매커니즘에 완벽하게 익숙지 못해서 그런지 자주 충돌하게끔 commit, push한다...

그런데 오늘 어제 commit 해 놓은 것을 push하려고하니 갑자기 처음 보는 **'Authentication failed for #.git'** 에러가 떠서 머리가 띵했다. :sob:

 fail이 뜨고 나서 로컬 저장소에 있던 폴더 및 파일들이 다 날아갔다. 어쩔 수 없이 다시 `git clone`해서 불러왔으나, commit을 해도 `git push`에서 다시 오류가 떠서 또 날아갔다. :tired_face:

해결 방법을 찾았기에 공유하려고 한다.
<span style="color:grey">*찾아보니 clone할 때도 이런 오류가 뜰 수 있다고 한다.*</span>


### 해결 방안

**Authentication failed**이기에 자격 증명과 관련이 있다.

Windows 10 환경에서 <span style="color:red">[시작] - "자격 증명 관리자" 검색 - Windows 자격 증명</span>란에 들어가면 다음과 같은 창이 뜬다.

![screenshot](../assets/images/windows_authentication.png)

**github**과 관련된 자격 증명을 선택하면 <span style="color:blue">편집</span> 및 <span style="color:blue">제거</span> 버튼이 있다.

![screenshot](../assets/images/github_authentication.png)

다음과 같이 편집 버튼을 클릭하여 사용자 이름(user id)와 암호(password)를 재입력할 수 있다.

이후 다시 `git clone`하면은 동작이 원활하게 함을 알 수가 있다:exclamation: