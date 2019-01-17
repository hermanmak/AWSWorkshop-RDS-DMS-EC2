# Migrate your first workflow to AWS
This workshop is intended to demonstrate the use of AWS CloudDevelopmentKit, hereby referred to as AWS CDK. Using AWS CDK we will go through step by step how to create a serverless web application from scratch. 

#### What is AWS CDK?
*Quoted directly from the open-source [repo](https://github.com/awslabs/aws-cdk)*: The AWS Cloud Development Kit (AWS CDK) is an open-source software development framework to define cloud infrastructure in code and provision it through AWS CloudFormation. The CDK integrates fully with AWS services and offers a higher level object-oriented abstraction to define AWS resources imperatively. Using the CDK’s library of infrastructure constructs, you can easily encapsulate AWS best practices in your infrastructure definition and share it without worrying about boilerplate logic. The CDK improves the end-to-end development experience because you get to use the power of modern programming languages to define your AWS infrastructure in a predictable and efficient manner.

#### Why should I use AWS CDK, or infrastructure as code?!?!
One of major reasons for unforseen outages and customer impacting issues is due to lack of change management.

#### What will we build?
We will build a simple serverless architecture that sends emails to a specified email address. This will start at a static website, go through a api gateway and then send and email.
![Architecture](/images/architecture.png)

#### Pre-reqs
1. A **personal** AWS Account
2. A **personal** email address

## Step 0 - Setup a clean development environment
Since everyone has their own preconfigured laptops with their own customized development environments, things could get pretty messy. So, lets use AWS Cloud9 for the sake of this lab, AWS Cloud9 provides a hosted IDE to write, run and debug code. It also comes with awscli preinstalled!
![AWS Cloud9 Console](/images/c9-console.png)

1. In the console, the Services button in the top left will reveal a dropdown with all the services.
2. Find or search for **Cloud9**.
3. In the middle right click **Create Environment**.
4. Give the Cloud9 environment a name (for example *cdk-cfn-demo-env*) and leave everything else as standard, create your environment.
5. In the bottom there is a terminal, lets install and initalize the CDK
    ```
    nvm install --lts
    nvm update npm
    npm install -g aws-cdk
    cdk --version

    mkdir myFirstCDKApp
    cd myFirstCDKApp
    cdk init --language typescript
    ```
