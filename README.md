# Draft 작성 규칙
 - Category는 My_Daily_Life, IT, Development, Study, Game, Hobby로 통일한다.

 - 폴더는 [**Category**]-[**작성 일자(수정 일자)**]로 구성되어야한다.  

 - 파일은 [**Category**]-[**작성 일자(수정 일자)**]-**post.md**, [**Category**]-[**작성 일자(수정 일자)**]-**title.txt**, [**Category**]-[**작성 일자(수정 일자)**]-**thumbnail.txt**로 구성되어야 한다.   

 - 작성 일자(혹은 수정 일자)는 작성 시작한 날짜+시간(24시 기준)을 띄어쓰기 및 기호 없이 붙여 쓴다.   

 - 작성 시 main branch에 작성하지 않고 [Category-최초 작성 일자]로 명명된 branch를 새로 개설하여 해당 branch에서 글을 작성한다.   
 
 - 작성이 완료되면 main branch로 PR을 날린다.   

 # Repository pulling 시 불필요한 static files(.png & .gif or etc..) 파일들 제거하는 방법
 ### Pull remote repo change   
```
 > git pull origin [branch]
```
   
### Set assume-unchanged files like .png, .gif, or etc..   
```
 > git update-index --assume-unchanged posts/**/**/*.png
 > git update-index --assume-unchanged posts/**/**/*.gif
```
   
### Remove them from local   
```
 > rm posts/**/**/*.png
 > rm posts/**/**/*.gif
```
   
# License   
Applied Apache-2.0 License: [License](https://github.com/bnbong/Myblog_posts/blob/master/License)
