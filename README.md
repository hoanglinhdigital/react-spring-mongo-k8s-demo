# kubernetes-full-stack-example
## Trước khi các bạn thực hiện bất cứ step nào khác, đảm bảo project có thể run bởi docker-compose
- ```docker-compose -f docker-compose.yaml up -d```
- Sau đó truy cập vào localhost:80 để xem website. Thử add một vài user, view list users.

## Giải thích về file cấu trúc project
### Frontend
- Nodejs project có nhiệm vụ list, add, delete users.
- Dockercompose file build ra static image chạy trên nginx.
- Docker image nhận biến môi trường: baseURL là url của API Backend.
### Backend
- Java Spring boot có nhiệm vụ cung cấp API list, add, delete users.
- Dockercompose file build ra static image chạy trên Java OpenJDK.
- Docker image nhận biến môi trường: MONGO_URL là url của MongoDB.
### Database
- Sử dụng image sẵn có của Mongo.

### Yêu cầu của assignment: Triển khai lên AWS & cấu hình CICD theo 1 trong 2 phương án sau:
### Lưu ý: riêng phần CICD, có thể triển khai mono repo hoặc tách frontend, backend thành 2 repo.
### Phương án 1:
- Frontend: S3 + CloudFront.
- Backend: ECS, ECR.
- Database: Document DB.
- Load Balance: ALB
- CICD: Jenkins, GithubAction hoặc CodePipeline đều được.
- Chiến lược deploy cho backend: Rolling update hoặc Blue-Green.

### Phương án 2:
- Frontend: Serverside Rendering trên EKS
- Backend: EKS, ECR.
- Database: Document DB.
- Load Balance: ALB
- CICD: Jenkins, GithubAction hoặc CodePipeline đều được.
- Chiến lược deploy cho backend: Rolling update hoặc Blue-Green.

## Chúc các bạn deploy thành công!