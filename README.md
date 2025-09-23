🚀 การทำงานของ Argo CD

มี 2 วิธีหลักในการสร้างแอปใน Argo CD:

1. Declarative (ที่เราใช้)

เราสร้างไฟล์ application/todolist-app.yaml ขึ้นใน Git

แล้ว apply เข้า cluster ด้วย:

kubectl apply -f application/todolist-app.yaml


จากนั้น Argo CD จะดึง config และ deploy แอปโดยอัตโนมัติ

2. Imperative (ทางเลือกอื่น)

ใช้ Argo CD CLI หรือ UI สร้างแอปได้ทันที (ไม่ต้องมี YAML ใน Git)

📦 Docker Image

แอป todolist มี 2 ส่วน:

Backend: registry.nipa.cloud/front-test-1/tasks-api:1.0.1

Frontend: registry.nipa.cloud/front-test-1/my-app:1.0.1

ก่อน deploy ให้แน่ใจว่า image เหล่านี้ pull ได้:

# ตรวจสอบ docker version
docker --version

# Login เข้า NIPA Registry
docker login registry.nipa.cloud

# Pull backend
docker pull registry.nipa.cloud/front-test-1/tasks-api:1.0.1

# Pull frontend
docker pull registry.nipa.cloud/front-test-1/my-app:1.0.1

