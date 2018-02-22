**Step 5: 페이스북 채널 생성, 연결하기**
===
### 1. 페이스북 페이지 생성
<a href="https://www.facebook.com/pages/create" target="blank">https://www.facebook.com/pages/create</a><br>
위 링크로 들어가서 페이스북 페이지를 만듭니다.
![1](/media/facebook_page.PNG)<br><br>
### 2. Facebook Messenger 설정
<a href="https://developers.facebook.com/" target = "blank">https://developers.facebook.com/</a><br><br>
1. 위 링크로 들어가서 '새 앱 추가'를 눌러 새 앱 ID를 만듭니다.![2](/media/appId.PNG)  
<br><br>
1. +제품 추가에서 Messenger 설정을 누릅니다.
![3](/media/channel3.PNG)
페이지를 선택해서 페이지 엑세스 토큰을 생성합니다.![4](/media/channel4.PNG)
<br><br>
1. 오라클 클라우드 settings 탭, channels 탭에 들어가 다음과 같이 채널을 추가합니다.![5](/media/channel5.PNG)
APP Secret 코드는 페이스북 대쉬보드에서 볼 수 있습니다.
![6](/media/channel6.PNG)
<br><br>
1. 페이스북 Messenger 설정에서 Webhooks 설정을 클릭합니다.![7](/media/channel7.PNG)
콜백 URL과 확인 토큰은 클라우드 settings 탭, channels 탭의 Webhook URL, Verify Token 입니다.
![8](/media/channel8.PNG)
<br><br>
1. 페이스북 Messenger 설정 탭의 Webhooks 에서 페이지를 구독합니다.
![10](/media/channel10.PNG)
