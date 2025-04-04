gcloud auth login  
gcloud config set project sit323-25t1-meng-d6abc93  
gcloud services enable artifactregistry.googleapis.com  
gcloud auth configure-docker australia-southeast2-docker.pkg.dev  
docker build -t australia-southeast2-docker.pkg.dev/sit323-25t1-meng-d6abc93/sit323-2025-prac5d/myfirstproject .  
gcloud artifacts repositories create sit323-2025-prac5d \  
  --repository-format=docker \  
  --location=australia-southeast2 \  
  --description="Private Docker repository for SIT323 Prac5D"  
docker push australia-southeast2-docker.pkg.dev/sit323-25t1-meng-d6abc93/sit323-2025-prac5d/myfirstproject  
docker run -d -p 3000:3000 australia-southeast2-docker.pkg.dev/sit323-25t1-meng-d6abc93/sit323-2025-prac5d/myfirstproject  
open localhost:3000  
