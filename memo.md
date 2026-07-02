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

```bash
# chart를 압축해서 docs/ 폴더 안에 저장
helm package . -d docs/

# index.yaml 파일을 docs/ 폴더 안에 자동 생성하기
helm repo index docs --url https://changsiuuuu.github.io/helm-micro/

```
https://changsiuuuu.github.io/helm-micro/
### 깃헙 페이지 설정
세팅즈 페이지스 마스터 /docs save
https://changsiuuuu.github.io/helm-micro/
```bash
helm repo ls
# 방금 만든 helm chart 의 위치를 헬름  저장소로 등록
helm repo add msa https://changsiuuuu.github.io/helm-micro/

helm repo ls
[user1@master step24_microservice_helm]$ helm repo ls
NAME                    URL                                               
cnpg                    https://cloudnative-pg.github.io/charts           
argo                    https://argoproj.github.io/argo-helm              
my-repo                 https://changsiuuuu.github.io/mychart/            
prometheus-community    https://prometheus-community.github.io/helm-charts
msa                     https://changsiuuuu.github.io/helm-micro/ 

# 동기화
helm repo update

# 차트 검색
helm search repo msa

helm uninstall msa-release -n msa

k delete ns msa
```