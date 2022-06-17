## README.md 파일?


 개발자라면 적어도 한 번쯤은 들여다 보게 되는 대표적인 오픈소스 사이트인 깃허브(https://github.com/)에서는 저장소 또는 레포지토리(repository)라는 기능이 있습니다. 각 저장소는 프로젝트의 소스코드를 업로드 할 수 있고, 유저 혹은 기능 별로 브랜치를 나누어 브랜치 별로 작업공간을 나누고 합치면서 버전관리를 할 수 있습니다. 이러한 저장소는 README.md 파일을 사용하여 각 저장소에 저장되어 있는 소스코드에 대한 설명이나 API 등을 명시하거나 프로젝트 자체를 소개하기도 합니다.



 README.md 파일 뒤에 붙는 확장자 '.md'는 마크다운 파일의 확장자로, 마크다운 파일은 HTML처럼 작성자가 본인의 입맛대로 게시물의 글 또는 그림 등의 소스의 배치나 칸의 배치 등을 조절 할 수 있습니다.



## 깃허브에 본인의 프로필 명시하기

   
 이 저장소와 README.md 파일을 활용하여 자신의 소개가 담긴 내용을 본인의 프로필을 들어갔을 때 대문짝만하게 표시할 수 있습니다. 방법은 다음과 같습니다.



**1. 본인의 이름과 동일한 이름의 저장소 만들기**


 해당 방법은 본인의 이름과 동일한 이름의 저장소가 없을 때, 깃허브 자체가 본인 이름으로 저장소를 만들어 주겠다는 제안을 해주므로 깃허브에서 안내해주는 대로 따라가도 됩니다. 그 외에는 하단의 방법을 따라하면 됩니다.

<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20220602062550/img.png?raw=true" width="100%" height="30%" title="create_new_repo" alt="create_new_repo"></img>
 > 우측 상단의 New 버튼을 눌러 새 저장소 생성   

<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20220602062550/img%20(1).jpg?raw=true" width="100%" height="30%" title="add_readme" alt="add_readme"></img>
 > 저장소 이름을 내 깃허브 닉네임과 동일하게 설정한다(필자는 이미 생성해 놓은 저장소가 있기 때문에 하단의 오류가 떴습니다).

<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20220602062550/img%20(2).jpg?raw=true" width="100%" height="30%" title="first_view" alt="first_view"></img>
 > 스크롤해서 내린 후 Add a README file를 체크한 후 Create repository를 클릭한다
저장소를 만들고 나면 다음과 같은 화면을 보실 수 있습니다.
   
<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20220602062550/img%20(3).jpg?raw=true" width="100%" height="30%" title="write_readme" alt="write_readme"></img>
 > 저장소를 만들고 난 후 볼 수 있는 화면
    
 우측 상단에 파란색 상자에 표시된 내용 처럼 본인의 이름으로 된 저장소는 자신의 프로필을 소개하는데 쓰입니다. README.md 파일의 제목 우측의 펜 모양을 클릭해 내용을 수정할 수 있습니다. 



**2. README.md파일 작성하기**

<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20220602062550/img%20(4).jpg?raw=true" width="100%" height="30%" title="badge" alt="badge"></img>
   
 README.md를 작성하시면서 현재까지 작성된 내용의 preview를 보고 싶다 하시면 Edit file 옆에 Preview 버튼을 클릭하여 실시간으로 외부에 어떻게 보이는지 확인할 수 있습니다.



 README.md파일은 무조건 마크다운 형식으로만 작성해야하는 것은 아니며, 자신이 HTML이 좀더 친숙하다 싶으시다면 HTML로 작성하셔도 무관합니다. 



 일반적인 윈도우 사용자나 개발자가 아닌 분들은 좀 낯설 수 있는 마크다운 파일에 대한 마크다운 파일 작성법은 하단의 내용을 통해 참조하시면서 작성하시길 바랍니다.

[https://gist.github.com/ihoneymon/652be052a0727ad59601](https://gist.github.com/ihoneymon/652be052a0727ad59601)


 프로필을 작성할 때, 자신의 기술 스텍이나 자신의 연락처 등을 남길 때, 단순히 링크만 올리는 것이 부담되는 경우에는 다음과 같이 뱃지를 사용하여 표현하거나 뱃지에 링크를 걸 수 있습니다.


<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20220602062550/img%20(5).jpg?raw=true" width="100%" height="30%" title="myrepo" alt="myrepo"></img>
   
 깃허브를 꾸밀 때 자주 사용할 수 있는 뱃지들을 잘 정리해 놓은 저장소는 하단에 링크에 첨부해 두었습니다. 해당 글에 표시된 URL을 그대로 복사하여 붙여 넣으시거나 URL의 내용을 살짝 수정해 크기나 색깔을 조절할 수 있습니다. 뱃지 말고도 내 README.md파일이 열람된 횟수를 볼 수 있는 hits기능 등의 여러 기능들도 첨부되어 있으니 참고 바랍니다.

[https://github.com/alexandresanlim/Badges4-README.md-Profile#-frameworks-](https://github.com/alexandresanlim/Badges4-README.md-Profile#-frameworks-)


 이모티콘을 통해 좀 더 재밌는 표현을 사용할 수 있습니다.

[https://getemoji.com/](https://getemoji.com/)


 하단의 링크는 참조용으로 첨부해 놓은 제 깃허브 프로필 링크입니다. 여러분들의 깃허브 프로필을 작성하실 때 참고가 되면 좋겠습니다!



[https://github.com/bnbong](https://github.com/bnbong)

<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20220602062550/img%20(6).jpg?raw=true" width="100%" height="30%" title="i_cant" alt="i_cant"></img>
   
 > 깃허브에 업로드된 README.md파일에서 우측의 Raw 버튼을 누르면 해당 본문에 사용된 HTML코드나 md코드를 볼 수 있습니다.
