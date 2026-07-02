1 application ( language, java, nodejs, python 등..)
auth기능, users기능 posts기능 market기능 등등.. 다들어있음

자바라고치면 jar파일이 하나 나오면
pod 하나에서 이런게 다 돌아가는데 ( 모놀리식 어플리케이션 )

쿠버네티스를 사용하면서 여러개의 pod를 관리하기가 쉬워졌다
이걸 쪼개는거임
auth app, users app, posts app, market app 각각의 하나가 독립적 어플리케이션
얘네들을 pod 에다가 넣어서 실행
기능별로 따로 만드는 구조가 가능하다 
디비도 각각 따로 갖고있다는거임
auth db, users db, posts db, market db

인증처리를 할때 사용자 정보가 필요하기도 한데 서로간 pod들이 데이터를 주고받을 일이있다
api를 통해서 서로 의존정보가있으면 서로 데이터를 주고받을수있다