## 시작하며..
작년 이맘때 쯤, 일부 뉴스를 통해서만 이슈가 되었던 코로나 사태는 올해 1년간 전 세계를 뒤집어 놓았고 이제는 마스크가 필수가 아니던 시절에 대한 기억도 희미해졌습니다. 전세계 대유행 바이러스로 인해 사람들은 유례없는 언택트 시대에 적응해 살아가야 했고 이 사태는 여전히 현재 진행중입니다. 

 

대학생 2학년 이자, 소프트웨어 학과에 재학중인 본인은 올해도 작년처럼 전액 등록금을 학교에 울면서 납부하며 제 전공인 소프트웨어 전공수업을 수강했습니다. 그러나 기초적인 언어에 대해서만 배웠던 작년과 달리, 올해는 언어에 대한 내용보다는 현업 개발자는 어떤 식으로 개발을 진행할까? 같은 어쩌면 언어 공부보다 더욱 개발자를 꿈꾸는 사람들에게 피와 살이 될 수 있는 개발 실무에 대한 내용을 프로젝트에 적용시키며 학습했습니다.

 

사실, 올해 진행했던 프로젝트는 전부 교수님이 해결하라고 제공하신 기말 혹은 중간 과제가 계기가 되어 진행되었습니다. 그러나 시시하고 미비했던 시작과는 달리 프로젝트를 진행하고 나서 얻은 결과는 매우 값졌다고 생각합니다. 이하는 올해 상반기와 하반기에 진행했던 프로젝트 중 가장 인상깊었고 회고하고 싶은 프로젝트에 대한 내용입니다.         

 

 

## 1. 채팅앱 Awesome_ChattingApp 프로젝트
<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C.png?raw=true" width="100%" height="30%" title="Awesome_chatting_app_logo" alt="Awesome_chatting_app_logo"></img>
<!-- ![Awesome_chatting_app_logo](https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C.png?raw=true) -->

 > 프로젝트 팀원과 같이 제작했던 앱 로고
      
**Github Link** : [https://github.com/bnbong/Awesome_ChattingApp](https://github.com/bnbong/Awesome_ChattingApp)    
**Github Page Link** : [https://bnbong.github.io/Awesome_ChattingApp/](https://bnbong.github.io/Awesome_ChattingApp/)
 
      
아마도 소프트웨어 학과의 학생이 되고 난 이후로 가장 신경을 많이 썼고 많은 시간을 정직하게(?) 투자했던 프로젝트라고 생각이 듭니다.

 

해당 프로젝트의 GOAL은 오픈 소스라는 개념을 좀 더 명확히 깨우치면서 오픈 소스를 받아오는 입장이 아닌 오픈 소스를 남들에게 공유를 하는 입장에서는 어떤 작업을 해야할까? 라는 질문에 대한 구체적인 답변을 알아가는 것이었습니다.

 

소프트웨어 개발을 개방형 협업으로 진행하는 것의 의의를 둔 오픈 소스는 가장 트랜디한 형태의 소프트웨어 개발 형태입니다. 한정된 인원 및 팀끼리만 공유하고 작업을 할 수 있었던 기존의 개발 방식과는 달리 누구나 접근 가능하고 수정이 가능한 형태의 소스를 공개함으로써 더 좋은 소프트웨어를 개발하자는 의도가 녹아있습니다.

 

그러나 누구나 접근이 가능하다는 특징은 때로는 단점이 되어 프로젝트의 진행을 방해하기도 합니다. 예를 들어 어떤 개발자는 변수 명을 지정할 때 변수 명에 딱히 의미를 부여하지 않고 자신이 그때그때 생각나는 변수를 빠르게 지정하기도 하는 개발자가 있는 반면, 어떤 개발자는 많은 시간을 들여 해당 소스에 적절한 변수 이름을 생각하여 사용하는 개발자가 있습니다. 이렇게 각기 다른 개발 성향을 가지고 있는 개발자가 어떠한 규칙 없이 하나의 프로젝트에 협업을 하게 되는 상황이 오면 불필요한 노력과 시간이 추가적으로 소모되어 개발 진척에 걸림돌이 될 수 있습니다.

 

때문에 오픈 소스 개발 방식은 원활한 협업을 위해 일종의 틀 혹은 규칙을 오픈 소스 기여자에게 제공합니다. github를 통해 오픈 소스 기여자가 열람 가능한 문서들은 기존 프로젝트 오너가 아닌 외부인이 해당 오픈 소스 프로젝트에 기여를 할 때 소스코드의 사용 및 접근 권한 취득에 대한 내용을 담은 [CONTRIBUTING](https://github.com/bnbong/Awesome_ChattingApp/blob/master/CONTRIBUTING.md) 문서, 혹은 해당 프로젝트의 릴리즈 버전의 보안 정책에 대한 내용을 담은 [SECURITY](https://github.com/bnbong/Awesome_ChattingApp/blob/master/SECURITY.md) 문서, 오픈 소스 기여자가 메인 github페이지로 PR을 보낼 때 해당 변경 사항을 빠르게 확인이 가능한 [PULL_REQUEST_TEMPLATE](https://github.com/bnbong/Awesome_ChattingApp/blob/master/PULL_REQUEST_TEMPLATE.md) 문서 등이 있습니다. 

 

위 문서들은 github community에서 repository 관리자에게 커뮤니티 문서에 대한 추천 리스트를 제공하는 문서입니다. repository의 Insights 탭에서 다음과 같이 확인하실 수 있습니다.
   
<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(1).png?raw=true" width="100%" height="30%" title="Awesome_chatting_app_community" alt="Awesome_chatting_app_community"></img>
<!-- ![Awesome_chatting_app_community](https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(1).png?raw=true) -->

 > github repository의 Insight탭에서 Community탭을 누르면 다음과 같은 창이 나온다.
 

이 외에도 개발자들의 코딩 규칙을 통일하는 코딩 컨벤션 또한 굉장히 중요한 협업 문서입니다. 그러나 저희 팀은 코딩 컨벤션에 대해서는 별 다른 가이드라인을 제공하지는 않았고 이는 프로젝트 완성 후 교수님께서 진행하신 프로젝트 점검에서 점수가 까이는 계기가 되었습니다ㅠㅠ 코딩 컨벤션은 전역 변수명 설정 방법에 대한 내용이나 굉장히 작게는 함수 선언 뒤에 붙는 괄호 혹은 콜론 ':' 앞에 띄어쓰기를 몇 칸 정도 넣어야 하는지에 대한 내용이 들어갈 수 있습니다.

 

해당 프로젝트는 안드로이드 스튜디오 프레임워크를 사용한 Java 기반의 채팅 앱 프로젝트 입니다. 교수님께서 제공하신 프로젝트 주제는 다양했으나 저희 팀은 많은 라이브러리와 예시가 존재하여 손쉽게 제작이 가능한 채팅앱을 제작하기로 결정했습니다. 프로젝트의 주제를 선정한 이후, 4명밖에 없는 팀원의 업무를 backend, frontend, issue관리로 분류하여 개발을 진행했습니다.

 

- **프로젝트를 진행하면서 좋았던 점**      

일단, 오픈 소스 제공자의 입장에서 github를 적극적으로 활용하여 최대한 다양한 가이드라인을 제공하고자 노력했다는 점이 프로젝트를 성공적으로 진행할 수 있었던 가장 큰 이유라고 생각이 듭니다.

 

앞서 하이퍼링크를 통해 걸어 두었던 여러 오픈 소스 기여에 대한 문서들을 한글 버전과 영문 버전으로 제작했으며 또한 해당 프로젝트의 라이센스로 [MIT License](https://github.com/bnbong/Awesome_ChattingApp/blob/master/LICENSE)를 채택하여 프로젝트의 라이센스 명시를 진행했습니다.

 

개발 방식에 대해서는 소규모의 팀이 가볍게 채택할 수 있는 워터폴 방식으로 개발을 진행했습니다. github에 원격 브랜치로 master, backend, db_debug(채팅 로그에 대한 db의 기록을 담당하던 firebase의 I/O확인 용 브랜치), frontend를 두어 팀 내에서 맡은 역할대로 분업을 진행하여 개발을 진행하였습니다. 이러한 형태의 branching 전략은 각 인원이 담당했던 작업을 하나의 브랜치에 올려서 생기는 커밋들 간의 충돌이나 어떤 작업의 커밋인지 구분이 힘들어지는 문제를 해결할 수 있었습니다. 또한 개발자간의 소통도구로 음성을 통해 진행하는 개발 회의는 discord를, 개발 과정 중에 발생하는 이슈나 해결해야하는 과제 혹은 기타 사항을 자유롭게 글 형태로 작성이 가능한 공유 docs문서를 개설하여 적극 활용했습니다.

 

이 [공유 docs문서](https://docs.google.com/document/d/1BNw_6XDqAEb_z2QM1GEHxnfU61NbPqQNSCarEJzmlIg/edit)의 경우는 협업을 진행하면서 다양한 보고 사항이 생길 수 있는데 그 보고들을 한번에 기록할 수 있는 장소가 있으면 좋겠다고 생각하여 나온 아이디어입니다. 자유로운 형태의 글쓰기가 가능한 대신, 글의 양식이나 글의 작성 방법에 대한 일종의 작성 규칙을 부여하여 난잡해보이지 않고 나름대로 깔끔하게 문서로된 소통이 가능하게 하였습니다. 프로젝트의 권한을 얻지 않은 외부인이 해당 문서의 무분별한 수정을 방지하기 위해 담당자가 따로 문서를 사용할 사용자에게 권한을 부여하는 형태로 보안문제를 해결했다는 점도 있습니다.

 

github에서는 프로젝트의 wiki문서, 프로젝트 관리, issue 관리, PR 관리 등 소스코드의 명시 이외에도 프로젝트에 대한 다양한 정보를 제공하는 기능이 있습니다. 저희 팀 또한 개발과정중에 발생하는 프로젝트 이슈에 enhancement, bug 등의 태그를 부여하여 이슈의 특징에 대한 태깅을 진행했고 github project 탭을 기준으로 개발 진행에 대한 진행상황 관리 및 앞으로 해야하는 개발상황에 대한 분석을 진행하였으며 github wiki 문서를 작성하여 프로젝트에 대한 자세한 정보를 제공하고자 노력했습니다.

<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(2).png?raw=true" width="100%" height="30%" title="Awesome_chatting_app_wiki" alt="Awesome_chatting_app_wiki"></img>
<!-- ![Awesome_chatting_app_wiki](https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(2).png?raw=true) -->

 > Awesome_ChattingApp프로젝트의 github wiki페이지
 

소스코드에 대한 버전관리를 진행하는 github사이트 외에도 소스코드 기여자가 아닌 일반인이 볼 수 있는 사이트인 [github page](https://bnbong.github.io/Awesome_ChattingApp/)를 운영하였습니다. 해당 페이지의 첫 화면에는 github readme와 비슷한 구성의 문서를 볼 수 있습니다. 첫 화면에 볼 수 있는 내용은 프로젝트 및 앱에 대한 개요와 기능, 라이센스, 다운로드 버전 및 다운로드 방법과 권장사양, 이슈 리포트와 troubleshooting 가이드, wiki페이지 링크와 개발자 소개 그리고 마지막으로 프로젝트 기여 방법과 보안정책 및 PR 방법에 대한 설명을 기재했습니다. github page는 다양한 템플릿이 존재하는데, 저희 팀은 jekyll-theme-architect 템플릿을 사용했습니다. 해당 템플릿의 좋은 점은 최신 버전의 릴리즈를 zip 혹은 tar.gz 파일형태로 다운이 가능하다는 점입니다. 깔끔하고 직관적인 UI배치도 마찬가지구요.

 

이슈 리포트 또한 이슈 형태에 따라(bug report, feature request 등) 이슈 작성 템플릿을 제공했습니다. 다만, 이 이슈템플릿은 프로젝트 막바지에 추가한 템플릿이라 그동안 개발하면서 발생했던 이슈들은 해당 템플릿을 사용하여 이슈보고를 진행하지 않았다는 점이 아쉬웠습니다.

 

 - **프로젝트를 진행하면서 아쉬웠던 점**      

가장 아쉬웠던 점은 이슈 관리의 부재입니다. 올해 하반기에 자세하게 배운 내용이지만, 프로젝트의 이슈관리는 더 좋은 품질의 결과물을 제작하는데 필수입니다. 팀 내에서 이슈에 대한 관리를 맡는 팀원을 두어 프로젝트를 진행했지만, github에서 제공하는 issue탭 만으로는 발생한 이슈들에 대한 관리가 어려웠습니다. 특히 발생한 이슈가 프로젝트의 어떤 기능에서 발생했는지 빠르게 파악하지 못해 프로젝트 진행에 불필요한 시간이 걸리기도 했었습니다. 이슈에 대한 관리를 외부 툴을 사용하여(JIRA 등) 진행했다면 어떤 기능에서 이슈가 많이 발생하는지 이슈 해소에 얼마나 오랜 시간이 소요 되는지 등의 통계 자료를 추출하여 프로젝트의 관리를 진행할 수 있었지만 그러지 않았다는 점이 제일 아쉬웠습니다.

 

또 다른 아쉬운 점으로는 개발 프로세스의 느슨한 관리였습니다. 워터폴 방식으로 한 사람이 하나의 기능을 맡아 기능이 완성되는 대로 바로 적용시켜 마치 폭포의 물줄기가 흐르는 것처럼 빠르게 결과물을 제작하는 개발방식을 채택했으나, 각 팀원이 맡은 기능에 대한 개발 기한을 부여하지 않고 개발을 진행했다는 점과 개발 후 프로젝트 품질 검수를 진행하지 않았다는 점입니다. 기능에 대한 개발 기한을 두어 개발을 진행했었다면 개발에 약간의 긴장을 부여하여 빠른 시일 내에 개발이 가능하게 하고 개발 스케쥴을 설정할 수 있어 개발 진행도 관리와 유연한 상황대처 및 사후 처리도 가능했으리라 생각이 듭니다. 이는 저를 포함한 팀원들의 개발 프로세스에 대한 지식 부족으로 인한 실책이라고 볼 수 있습니다.

 

## 2. Demo project Space Invaders

<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(3).png?raw=true" width="100%" height="30%" title="Space_invaders_logo" alt="Space_invaders_logo"></img>
<!-- ![Space_invaders_logo](https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(3).png?raw=true) -->
 > space invaders 로고
**원본 Space Invaders github 주소** : [https://github.com/RobertoIA/Invaders](https://github.com/RobertoIA/Invaders)
      
**Github Link** : [https://github.com/ERICA-SWDevelopmentPractice-JunhyeokLee/SETB-BestPractice](https://github.com/ERICA-SWDevelopmentPractice-JunhyeokLee/SETB-BestPractice)
       
   
많은 사람들의 사랑을 받았고 지금까지도 변형된 형태로 나오고 있는 유명 고전 게임 space invaders 입니다. 2020년도 하반기에 진행했던 해당 프로젝트는 상단의 Java로 작성된 space invaders 소스를 가지고 추가적인 기능 추가 및 버그 수정 등을 진행하는 작업을 했습니다. 이번 프로젝트는 Awesome ChattingApp 처럼 오픈 소스를 제공하는 목적이 아니라 가상의 소프트웨어 개발회사의 기획 혁신팀으로 배정이 되어 있는 시나리오에서 모 회사의 원활한 개발을 위한 Best Practice를 구상하고 Space invader을 Best Practice를 적용시킬 demo project로 설정해서 Best Practice를 검증을 하는 용도의 프로젝트 였습니다.

 
<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(4).png?raw=true" width="100%" height="30%" title="SETB_logo" alt="SETB_logo"></img>
<!-- ![SETB_logo](https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(4).png?raw=true) -->
 > 시나리오 상에만 존재하는 가상의 SW 회사 SETB로고
 

고객에게 고객 맞춤 소프트웨어를 제공하는 가상의 회사 SETB 사의 Best workflow를 구성함과 동시에 고객에게 프로젝트를 납품하고 사후 관리를 진행하는 flow과정 또한 구상했습니다. 해당 flow는 다음과 같습니다.

 
<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(5).png?raw=true" width="100%" height="30%" title="Deploy_cycle" alt="Deploy_cycle"></img>
<!-- ![Deploy_cycle](https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(5).png?raw=true) -->
 > 전체적인 개발 과정 및 고객 납품, 사후처리 방식
 

이번 프로젝트 부터 보다 나은 git branching 전략에 대해 구상하는 과정도 진행했습니다. 브랜칭 전략 또한 팀 내에서 프로젝트를 진행하면서 변화를 주었으나 초반에 구상을 해뒀던 branching 전략은 다음과 같습니다.

 

- Master branch : develop branch에서 개발이 완료된 기능들을 중간 정리 및 관리를 하는 용도이며 프로젝트를 완성하여 배포를 진행하기 전, 배포 전략에 대한 구상을 하는 용도로도 사용이 된다. 완성된 배포 전략에 따라 release branch로 넘어가서 배포를 진행한다.
- Develop branch : 주요 기능을 개발하고 features branch에서 개발된 모든 feature들을 병합하고 관리하는 용도이며 상시로 버그를 수정한 커밋들이 추가되고 새로운 기능 추가가 있을 경우 해당 기능에 대한 이름을 가진 features branch를 생성하여 작업한다.
- Features branch : develop에서 파생되어 추가적인 feature을 개발할 때 사용하는 용도이며 추가 feature 개발이 완료되면 features branch에 존재하는 모든 commit들은 develop branch로 rebase한다.
- Hotfix branch : 프로젝트에서 발생하는 버그의 수정이나 취약점을 보완, 또는 성능 향상을 위해 긴그밯게 배포되는 패치가 필요할 때 사용되는 branch.
- Release branch : 새로 출시하는 버전의 배포를 진행하는 브랜치이다. develop 브랜치에서 배포할 수 있는 수준의 기능이 모이거나, 배포 일정이 될 때 배포를 진행한다. 최종적인 버그 수정이나 문서 작성등을 진행하며 release 브랜치와 직접적으로 관련된 작업이 아니라면 새로운 기능을 추가로 병합하지는 않으며 release 후 master branch에 병합한다.

<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(6).png?raw=true" width="100%" height="30%" title="branch" alt="branch"></img>
<!-- ![branch](https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(6).png?raw=true) -->
> 설정한 branching 전략대로 branch 별 커밋을 작성한 모습. git log를 통해 확인했습니다.
   
이 workflow structure는 따로 프로젝트를 진행하면서 얻은 노하우를 통해 도출된 workflow가 아니라 단순히 개발 실무에 사용하는 workflow는 어떤 것이 있으며 git 을 사용한 workflow 전략으로 branching 방법에 대한 단순한 개념을 토대로 도출한 workflow 입니다.

 

이 branching 전략에서 아쉬운 점과 고쳐야할 점은 release branch의 필요성에 대한 것입니다. 실무를 진행하신 경험이 있던 교수님의 피드백으로는 release branch는 최근 실무에는 많이 도태되고 있는 branch라고 설명을 하셨습니다. 저희 팀에서도 workflow를 구성하면서 어차피 완성된 기능들은 모두 master branch에 모여 병합이 될 터인데, 굳이 release branch를 또 나눠서 프로젝트 배포를 진행해야하는 이유에 대해서는 명확한 근거가 생각나지 않았습니다.

 

위 workflow 전략에 대한 피드백을 바탕으로 brancing 전략을 수정하여 demo project Space Invaders에 적용했습니다. 해당 프로젝트는 저희 팀이 설정해 놓은 Best Practice를 적용시켰는데, 전체적인 Best Practice 개요는 다음과 같습니다.

 

<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(7).png?raw=true" width="100%" height="30%" title="Best_practice" alt="Best_practice"></img>
<!-- ![Best_practice](https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(7).png?raw=true) -->
 > 팀에서 최종 도출이 된 Best Practice 개요

저번 Awesome ChattingApp 프로젝트와 개발 과정에 대하여 변화한 점은 정형화된 개발 프로세스의 도입과 이슈관리 및 프로젝트 스프린트 관리를 진행할 수 있는 새로운 툴 Jira의 도입, Jenkins와 sonarqube 관련 플러그인을 도입하여 코드 품질에 대한 검사와 Jenkins를 통한 프로젝트 빌드 및 실행가능하며 배포가 가능한 형태의 파일을 제작한 것입니다. 

 

가장 먼저 개발 프로세스 '애자일 프로세스'를 도입하여 개발을 진행한 점입니다. 애자일 소프트웨어 개발 프로세스는 일정한 주기의 개발 주기를 설정하고 진행하던 개발 주기가 끝나면 그 주기 동안 개발된 기능을 제 3자가 체험할 수 있는 프로토타입을 제공하여 피드백 등을 얻는 개발 프로세스 입니다. 가상의 SW 개발 회사 SETB사가 고객과의 원활한 소통을 통해 고객이 원하는 형태의 소프트웨어를 개발한다는 것이 장점으로 알려져 있는 회사로 설정이 되어 있기에 애자일 프로세스가 가장 적합하다고 판단이 되어 개발 프로세스로 채택하였으며, 애자일 프로세스 중 스크럼 프로세스를 선택했습니다.

 

이슈 관리 도구인 Jira에서는 이슈 관리 뿐만아니라 애자일 방법론의 개발 주기에 해당하는 스프린트의 일정이나 작업 상황에 대한 관리를 진행할 수 있는 템플릿을 제공합니다. Jira의 scrum 템플릿을 적용하여 실제 스프린트 기한보다는 짧은 기간인 3일을 기준으로 스프린트 기한을 주었으며 주어진 3개의 요구사항을 에픽 이슈로 생성하여 하나의 스프린트는 하나의 에픽 이슈를 해소하는 형식으로 개발을 진행했습니다.

 

<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(8).png?raw=true" width="100%" height="30%" title="Issues" alt="Issues"></img>
<!-- ![Issues](https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(8).png?raw=true) -->
> 주어진 요구사항을 토대로 간단한 문서화 작업 후 에픽 이슈로 분류한 모습
 

- **프로젝트를 진행하면서 좋았던 점**
   
우선, 정형화된 개발 프로세스 덕분에 개발에 소요되는 시간이 획기적으로 줄었다는 점입니다. 저희 팀이 설정한 Best Practice의 효율성을 검증하기 위해 본격적인 개발에 앞서 Best Practice를 적용하지 않고 개발을 진행한다면 어느 정도의 작업 효율을 보일까? 라는 궁금증이 들어 Best Practice를 적용시키지 않고 개발자의 업무만 분담한 채로 개발을 진행해 보았습니다. 그 결과는 다음과 같습니다.

 

<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(9).png?raw=true" width="100%" height="30%" title="Compare" alt="Compare"></img>
<!-- ![Compare](https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(9).png?raw=true) -->
    
보다시피 개발 후 도출물에 대한 퀄리티는 Best Practice를 적용한 쪽이 더 좋은 모습을 볼 수 있었습니다. 또한 Best Practice를 적용시켜 개발을 진행한 것이 개발 과정 중 발생하는 이슈에 대한 대처가 훨씬 깔끔했던 모습을 보이기도 했습니다.

 

<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(10).png?raw=true" width="100%" height="30%" title="JUnit_testcases" alt="JUnit_testcases"></img>
<!-- ![JUnit_testcases](https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(10).png?raw=true) -->
 > 프로젝트의 JUnit 테스트 케이스 일부
   
또한 이전 Awesome Chatting App에서는 진행하지 못했던 테스트 케이스를 작성하고 모듈 별로 테스트를 진행하여 코드의 이상이 없는지 검증하는 과정을 거쳤습니다. Java는 JUnit이라는 외부 테스트 프레임워크가 존재합니다. 저희 팀은 이 프레임워크를 활용하여 함수 및 모듈에 대한 테스트를 진행했습니다.

 

 

<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(11).png?raw=true" width="100%" height="30%" title="Sonarlint" alt="Sonarlint"></img>
<!-- ![Sonarlint](https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(11).png?raw=true) -->
 > Intellij sonarqube 관련 플러그인 sonarlint
   
코드 품질에 대한 검사도 진행했습니다. Best Practice를 완전히 따른다면 Sonarqube의 환경을 설정하여 정적 검사를 진행해야 했으나 팀끼리 공유 가능한 Jenkins와 sonarqube의 서버를 구축하는데 실패하여 local 환경에서 IDE의 플러그인을 설치하여 코드 정적 분석을 진행했습니다. 코드 룰셋의 경우는 플러그인이 default로 제공하는 룰셋을 사용했으며 위의 사진은 sonarlint 플러그인의 분석을 진행하여 나온 결과입니다.

 

CI/CD의 자동화가 가능한 툴인 Jenkins를 사용한 것도 이번 프로젝트의 잘했던 점 중 하나입니다.

<img src="https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(12).png?raw=true" width="100%" height="30%" title="Local_build" alt="Local_build"></img>
<!-- ![Local_build](https://github.com/bnbong/Myblog_posts/blob/master/posts/Development/20201228001823/%EB%8B%A4%EC%9A%B4%EB%A1%9C%EB%93%9C%20(12).png?raw=true) -->
 > local 환경에 jenkins를 올려 프로젝트 빌드를 진행한 모습
   
좌측 하단에서 보실 수 있는 것처럼 github repository와 연동하여 커밋이 올라갈 때마다 혹은 수동으로 빌드를 실행할 수 있고 완성된 빌드 버전을 토대로 고객에게 개발 후 도출된 기능을 체험해 볼 수 있는 프로토타입을 제작하여 제공할 수 있었습니다.

 

전체적으로 팀에서 설정해둔 Best Practice를 그대로 따라가며 개발을 진행했으며, Best Practice의 효율성에 대한 검증을 진행할 수 있었던 점도 이번 프로젝트를 진행하면서 좋았던 점 중 하나였습니다.

 

- **프로젝트를 진행하면서 아쉬웠던 점**
   
가장 아쉬웠던 점은 Jenkins와 Sonarqube의 기능들을 제대로 활용하지 못한 것이었습니다. Jenkins의 경우 프로젝트의 github과 연동을 하여 github에 올라가 있는 소스들에 대한 빌드는 가능했으나, 빌드 후 github release에 deploy 하는 과정을 자동화 시키지 못했으며, Sonarqube의 경우는 프로젝트를 연동시키는 것 자체를 진행하지 못하여 Jenkins 연동이 불가능해 빌드 중 정적분석을 진행하지 못했습니다. 때문에 차선책으로 Intellij의 sonarlint플러그인을 사용하여 정적 분석을 진행했습니다. Jenkins와 Sonarqube둘다 공통적으로 팀원 모두가 사용이 가능한 서버에 올리지 못해 빌드와 정적 분석결과에 대한 공유를 하지 못했습니다.

 

아무래도 Jenkins와 Sonarqube 둘다 많은 소프트웨어 개발 기업에서 채택하는 도구이나, 일반 개발자나 규모가 작은 프로젝트에서는 두 도구의 기능들을 제대로 사용하기에는 신경써야하는 설정도 많고 여러모로 무리가 있어보였습니다. 프로젝트에 참여한 팀원 모두가 해당 툴들을 처음 접해보았기에 이러한 실책이 발생하지 않았나 싶습니다. 프로젝트는 CI/CD와 코드품질검사 자동화를 제외한 개발 과정에는 큰 흠이 없었지만 Jenkins와 Sonarqube 활용법에 대한 연구를 좀 더 진행하고 프로젝트를 마무리 지었으면 좀 더 좋았을껄.. 하는 생각이 들었습니다.

 

 

## 마치며..
올 한해는 작년과 달리 단순히 프로그래밍 언어에 대한 공부가 아니라 현업 소프트웨어 개발은 어떤 식으로 진행되어야 하는가에 대한 내용을 공부할 수 있었던 의미있는 한 해였습니다. 어쩌면 길게 느껴지기도, 짧게 느껴지기도 했던 한 해였지만 이렇게 회고 형식으로 한 해 동안 진행했던 프로젝트의 회고를 진행해보니 고쳐야할 점도 많이 보이고, 잘했던 점도 인지 할 수 있게 되어 2020년 한 해 동안 좋은 경험을 하지 않았나 싶습니다. 현재는 창업 팀에서 웹 백앤드 개발을 담당하여 웹개발에 집중을 하고 있고 게임 개발 쪽으로도 관심이 있어서 앞으로도 다양한 프로젝트를 스스로 진행해보고 싶습니다. 그러나 하고싶은건 많은데 시간이 이를 허락해줄지는 모르겠네요. 여러모로 아쉬웠던 2020년도였지만 곧 다가오는 2021년에는 좋은 일만 가득했으면 좋겠습니다.
