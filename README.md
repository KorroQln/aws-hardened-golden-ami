# aws-hardening-golden-ami

## Building CIS hardened Golden Images with EC2 Image Builder
[AWS Image Builder](https://docs.aws.amazon.com/imagebuilder/latest/userguide/what-is-image-builder.html) allows us to create, maintain, and distribute golden images for applications and infrastructure across accounts in an automated way. Now, you can use AWS Marketplace AMIs in EC2 Image Builder Console and use those AMIs as base images in the image build workflows. This makes it easier to seamlessly track and integrate AWS Marketplace AMI subscriptions in image customization workflows.

You can deploy CIS Benchmark hardening components via EC2 Image Builder. This gives you the ability to customize the baseline CIS image, and still being able to get to CIS standards baseline. This launch provides a streamlined approach to image hardening by eliminating the need to design, build, and test hardening components.

![Hardening workflow](images/hardeningAMIs.png)

## Configuration
1. Create a S3 bucket and upload build kits in S3 bucket
2. Create IAM Role and attach following required policies:
    - `arn:aws:iam::aws:policy/service-role/AmazonEC2RoleforSSM`
    - `arn:aws:iam::aws:policy/EC2InstanceProfileForImageBuilder`
3. Create EC2 Image Builder pipeline
    - Choose a base image for customizations
4. Create build components for Image Receipt
    - Add any necessary software from the base image
    - Customize settings and scripts 
    - Get a CIS hardening component from S3
    - Execute hardening script
5. Create a pipeline from hardening recipe
6. Trigger pipeline
