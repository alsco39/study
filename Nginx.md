<H1>Nginx</H1>



<H2>Nginx란?</H2>

동시접속 처리에 특화된 웹 서버 프로그램 : 동기

특징으로는 Apache보다 <b>동작이 단순</b>하고 <b>전달자 역할</b>만 하기 때문에 <b>동시접속 처리에 특화</b>되어 있다.

동시접속자가 약 700명이상이라면 서버를 증설하거나 Nginx환경을 권장한다.

아파치가 시장 점유율이 압도적이지만 AWS상에서는 시장 점유율이 44%에 달할 정도로 가볍고 성능이 좋은 엔진이다.



<H2>역할</H2>

1. 정적 파일을 처리하는 HTTP 서버로서의 역할

   웹서버의 역할은 HTML, CSS, Javascript, 이미지와 같은 저보를 웹 브라우저에 전송하는 역할을 한다. (HTTP 프로토콜을 준수)

2. 응용프로그램 서버에 요청을 보내는 리버스 프록시로서의 역할

   리버스 프록시(reverse proxy)는 클라이언트는 가짜 서버에 요청하면 프록시 서버가 배후 서버(reverse server)로부터 데이터를 가져오는 역할을 한다.

   -> 프록시 서버가 Nginx, 리버스 서버가 응용프로그램 서버를 의미한다.

   웹 응용프로그램 서버에 리버스 프록시를 두는 이유는 요청에 대한 버퍼링이 있기 때문이다. 클라이언트가 직접 APP 서버에 직접 요청하는 경우 프로세스 1개가 응답 대기 상태가 되어야만 한다. 따라서 프록시 서버를 둠으로써 요청을 배분하는 역할을 한다.

   
