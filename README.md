# aws-hardened-golden-ami

## Building CIS hardened Golden Images with EC2 Image Builder
[AWS Image Builder](https://docs.aws.amazon.com/imagebuilder/latest/userguide/what-is-image-builder.html) allows us to create, maintain, and distribute golden images for applications and infrastructure across accounts in an automated way. Now, you can use AWS Marketplace AMIs in EC2 Image Builder Console and use those AMIs as base images in the image build workflows. This makes it easier to seamlessly track and integrate AWS Marketplace AMI subscriptions in image customization workflows.

## Configuration
1. Create a S3 bucket and upload build kits in S3 bucket
2. Create IAM Role and attach following required policies:
  - `arn:aws:iam::aws:policy/service-role/AmazonEC2RoleforSSM`
  - `arn:aws:iam::aws:policy/EC2InstanceProfileForImageBuilder`
3. Create EC2 Image Builder pipeline with base AMI
4. Create Components that you want to use 
5. Select IAM Role that you have created on Step 2
6. Name your pipeline
7. Name your AMI
8. Trigger pipeline
