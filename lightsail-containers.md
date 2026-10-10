
aws lightsail push-container-image --region <Region> --service-name <ContainerServiceName> --label <ContainerImageLabel> --image <LocalContainerImageName>:<ImageTag>

docker buildx build --platform linux/amd64,linux/arm64 -t 535002879962.dkr.ecr.us-east-1.amazonaws.com/cloudnautic/pythonapp:latest --push .

aws lightsail push-container-image --region us-east-1 --service-name <ContainerServiceName> --label <ContainerImageLabel> --image 535002879962.dkr.ecr.us-east-1.amazonaws.com/cloudnautic/pythonapp:latest

aws lightsail push-container-image \
  --region ap-south-1 \
  --service-name container-service-1 \
  --label pythonapp \
  --image 535002879962.dkr.ecr.us-east-1.amazonaws.com/cloudnautic/pythonapp:latest

brew install aws/tap/lightsailctl









