# Network 

## Index 

## VPC ( Virtual Private Cloud )

논리적으로 격리된 가상 네트워크에서 각 클라우드의 리소스를 시작할수 있습니다. 

VPC에서는 리전의 각 가용성을 영역에 하나의 서브넷이 있고, 각 서브넷에 인스턴스가 있고, VPC의 리소스와 인터넷 간의 통신을 허용하는 인터넷 게이트웨이가 있습니다.   

> [https://docs.aws.amazon.com/ko_kr/vpc/latest/userguide/what-is-amazon-vpc.html](https://docs.aws.amazon.com/ko_kr/vpc/latest/userguide/what-is-amazon-vpc.html)        
> [https://cloud.google.com/vpc/docs/vpc?hl=ko](https://cloud.google.com/vpc/docs/vpc?hl=ko)    

### Virtual Private Cloud(VPC)

VPC는 자체 데이터 센터에서 운영하는 기존 네트워크와 아주 유사한 가상 네트워크입니다. VPC를 생성한 후 서브넷을 추가할 수 있습니다.

### 서브넷 

서브넷은 VPC의 IP 주소 범위입니다. 서브넷은 단일 가용 영역에 상주해야 합니다. 서브넷을 추가한 후에는 VPC에 AWS 리소스 배포할 수 있습니다.

> [서브넷](https://physicallaw.tistory.com/106)   

일반적으로 사용되는 IP 주소는 A, B, C 클래스로 나누어져 있다.  

A 클래스의 네트워크 ID는 24비트 이며 IP주소를 1677만 7214개를 사용할 수 있다.  
만약 그 많은 수의 컴퓨터가 브로드캐스트 패킷을 전송하면 모든 컴퓨터에 패킷이 전송되고 네트워크가 혼잡해질 것이다.    


- 서브넷팅의 예시 

호스트 ID에서 비트를 빌려 서브넷으로 만든다. 그러면 기존 네트워크 ID와 호스트 ID로 구성되어 있던 것이 네트워크, 서브넷, 호스트 ID로 나뉘게 된다. 

- 서브넷 마스크란?     

예시의 IP주소를 보면 192.168.32.0/24 처럼 /24 같은 표시가 붙어있는 것을 확인할 수 있다. 이것은 서브넷 마스크의 bit 수(왼쪽에서부터 1의 개수)를 나타낸다. 즉 /24는 해당 IP의 서브넷 마스크의 왼쪽에서부터 24개가 1이라는 것을 의미한다.   

그런데 애초에 IP클래스들은 Network ID를 나타내는 부분과 Host ID를 나타내는 부분이 이미 구분되어 있는데 굳이 서브넷 마스크가 필요한 이유가 무엇일까? 위에서도 설명했지만 서브넷팅을 하여 효율적인 네트워크의 사용을 위해서다.

- 서브넷팅 

서브넷팅은 IP 주소 낭비를 방지하기 위해 원본 네트워크를 여러개의 서브넷으로 분리하는 과정을 뜻한다. 서브넷팅은 서브넷 마스트의 bit 수를 증가시키는 것이라고 생각하면 이해가 편하다.  
서브넷 마스크의 bit수를 1씩 증가시키면 할당할 수 있는 네트워크가 2개수로 증가하고 호스트 수는 2배수로 감소한다.      

192.168.32.0/24는 원래 하나의 네트워크였다. 이때 할당 가능한 host의 수는 2^8-2=254개이다.         
여기서 2개를 빼는 이유는 첫번째 주소인 192.168.32.0은 Network Address로 쓰이고 마지막 주소인 192.168.32.255는 Broadcast로 쓰이기 때문에 호스트에 할당할 수 없기 때문이다.    

## 환경 구성 ( AWS Subnet Configure)

> [AWS Configure Subnet](https://docs.aws.amazon.com/ko_kr/vpc/latest/userguide/configure-subnets.html)

## 단순 참조 ( 이해 용도 )

> [서브넷의 구조](https://greate-future.tistory.com/38)         
> [서브넷, 서브넷마스크, 서브넷팅이란?](https://code-lab1.tistory.com/34)    
> [서브넷의 구조](https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=nieah914&logNo=221383899425)

# CIDR 블록 

- [Classless Inter-Domain Routing](https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing)

- [](https://dev.classmethod.jp/articles/vpc-3/)

