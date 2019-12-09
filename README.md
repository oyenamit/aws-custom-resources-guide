# A Guide to Using AWS Custom Resources
[AWS custom resources](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/template-custom-resources.html) are a powerful way to add flexibility to [AWS CloudFormation](https://aws.amazon.com/cloudformation/) templates. While other AWS resources represent a specific service (RDS, EC2 etc.), custom resources act like generic placeholders that can be used to inject any additional logic in CloudFormation templates. A custom resource is typically attached to an [AWS Lambda](https://aws.amazon.com/lambda/) function which can contain any user-specified code. This code gets executed whenever the CloudFormation template is deployed, updated or deleted. This way, custom resources allow you to extend CloudFormation in ways that are not possible with regular AWS services.

![Workflow of a custom resource solution](/html/images/components.png)

This article first presents the architectural components of custom resources and explains how they interact with the CloudFormation service. Then, we look at a simple case study where we implement custom provisioning logic using a lambda-backed custom resource. Prior knowledge of CloudFormation, Lambda and IAM services is required.
