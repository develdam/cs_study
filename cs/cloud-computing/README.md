# cloud-computing

1. IaaS(인프라 서비스): 가상 컴퓨터, 가상 네트워크, 가상 드라이브를 통째로 빌려주는 서비스이다.
- Virtual Machine(가상 서버): **AWS EC2**, Azure Virtual Machines, Google Cloud Computer Engine
- Storage: **AWS S3(Simple Storage Service)**, Google Cloud Storage
- Network: AWS VPC(Virtual Private Cloud)

2. PaaS(플랫폼 서비스): 개발자가 코드를 올리면 실행될 수 있도록 운영체제, 런타임 환경, 데이터베이스를 제공하는 서비스이다.
- Web Hosting: AWS Elastic Beanstalk, Azure App Service, Google Cloud App Engine, Heroku, **Vercel**
- Managed DB: AWS RDS, Google Cloud SQL

3. Serverless(서버리스): 서버가 24시간 켜져 있지 않고, 요청(이벤트)이 들어올 때만 0.1초 만에 켜져서 작동하는 서비스이다.
- FaaS(서비스형 함수): **AWS Lambda**, Azure Functions, Google Cloud Functions, **Cloudflare Workers**
- BaaS(서비스형 백엔드): Google Firebase, **Supabase**
- Serverless Database: AWS DynamoDB

---

Spring으로 보는 IaaS vs Serverless
1. IaaS(ex. AWS EC2)
- 24시간 내내 스프링 서버가 켜져서 대기한다.
- 접속자가 0명이어도 한 달 내내 고정 비용이 발생한다.
- 스프링 본연의 성능을 100% 활용할 수 있다.
2. Serverless(ex. AWS Lambda)
- 요청이 올 때만 스프링 서버가 켜져서 코드를 실행한다.
- 접속자가 없으면 비용이 0원이고, 요청당 비용이 발생한다.
- 첫 요청 시 스프링이 켜지는 시간 때문에 무겁고 느릴 수 있다.

일반적으로 규모가 크고 무거운 스프링(Spring Boot) 백엔드 서버는 AWS EC2나 AWS ECS(컨테이너 기반)에 24시간 켜두는 방식으로 가장 많이 운영한다.