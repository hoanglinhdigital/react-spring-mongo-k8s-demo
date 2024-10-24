# kubernetes-full-stack-example
# Trước khi các bạn thực hiện bất cứ step nào khác, đảm bảo project có thể run bởi docker-compose
docker-compose -f docker-compose.yaml up -d

# truy cập vào localhost:80 để xem web site. Thử add một vài user, view list.
# Giải thích về file cáu trúc project
# Frontend

# Backend

# Database
- Sử dụng image sẵn có của mongo.

# Yêu cầu của assignment: Triển khai lên AWS & cấu hình CICD theo 1 trong 2 phương án sau:
# Lưu ý: riêng phần CICD, có thể triển khai mono repo hoặc tách frontend, backend thành 2 repo.
# Phương án 1:
- Frontend: S3 + CloudFront.
- Backend: ECS, ECR.
- Database: Document DB.
- Load Balance: ALB
- CICD: Jenkins, GithubAction hoặc CodePipeline đều được.
- Chiến lược deploy cho backend: Rolling update hoặc Blue-Green.

# Phương án 2:
- Frontend: Serverside Rendering trên EKS
- Backend: EKS, ECR.
- Database: Document DB.
- Load Balance: ALB
- CICD: Jenkins, GithubAction hoặc CodePipeline đều được.
- Chiến lược deploy cho backend: Rolling update hoặc Blue-Green.