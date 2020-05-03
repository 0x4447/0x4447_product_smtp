# S3 SMTP

This small project will deploy a S3 bucket with a trigger set to invoke a Lambda function, which will get the object that trigered it, red the content, and based on that create email and send it out the the right recipient. 

Ideal for small websites that have a simple contact form. You create and save a object to S3, and then this project will do the rest for you.

# DISCLAIMER!

This stack is available to anyone at no cost, but on an as-is basis. 0x4447, LLC. is not responsible for damages or costs of any kind that may occur when you use the stack. You take full responsibility when you use it.

# How to deploy

<a target="_blank" href="https://console.aws.amazon.com/cloudformation/home#/stacks/new?stackName=zer0x4447-SMTP&templateURL=https://s3.amazonaws.com/0x4447-drive-cloudformation/SMTP.json">
<img align="left" style="float: left; margin: 0 10px 0 0;" src="https://s3.amazonaws.com/cloudformation-examples/cloudformation-launch-stack.png"></a>

All you need to do to deploy this stack is click the button to the left and follow the instructions that CloudFormation provides in your AWS Dashboard. Alternatively you can download the CF file from [here](https://s3.amazonaws.com/0x4447-drive-cloudformation/SMTP.json).

# What will deploy?

![SMTP Diagram](https://raw.githubusercontent.com/0x4447/0x4447_product_smtp/assets/diagram.png)

- 1x Lambda
- 1x CodePipeline
- 1x CodeBuild
- 1x S3 Bucket
- 3x Roles
- 2x Policies

All project resources can be found [here](https://github.com/topics/0x4447-product-SMTP).

# Manual work

You'll have to configure SES to allow it to send emails out. Either by confirming a domain that you own, or individual emails. In this case it should be just yours.

# Pricing

All resources deployed via this stack will potentially cost you money. But you'd have to do the following for this to happen:

- Invoke Lambdas over 1,000,000 times a month
- Send and receive over 1000 emails a month
- Perform over 10,000 Get and Put operations and over 2000 Delete operations in your S3 Bucket
- Exceed 100 build minutes on CodeBuild
- $1 per active CodePipeline (must run at least once a month to be considered active)

The only payment you'll encounter from Day One is S3 storage fee for emails and CodePipeline artifacts.

# How to generate the CloudFormation file

This repo was build using the [Grapes Frameworks](https://www.npmjs.com/package/@0x4447/grapes). First you need to install the framework:

```
sudo npm install -g @0x4447/grapes
```

Then, go inside this repo and run this command:

```
grapes -s .
```

This will create a `CloudFormation.json` file in the root dir of the repo which you can upload to AWS.

# The End

If you enjoyed this project, please consider giving it a 🌟. And check out our [0x4447 GitHub account](https://github.com/0x4447), where you'll find additional resources you might find useful or interesting.

## Sponsor 🎊

This project is brought to you by 0x4447 LLC, a software company specializing in building custom solutions on top of AWS. Follow this link to learn more: https://0x4447.com. Alternatively, send an email to [hello@0x4447.email](mailto:hello@0x4447.email?Subject=Hello%20From%20Repo&Body=Hi%2C%0A%0AMy%20name%20is%20NAME%2C%20and%20I%27d%20like%20to%20get%20in%20touch%20with%20someone%20at%200x4447.%0A%0AI%27d%20like%20to%20discuss%20the%20following%20topics%3A%0A%0A-%20LIST_OF_TOPICS_TO_DISCUSS%0A%0ASome%20useful%20information%3A%0A%0A-%20My%20full%20name%20is%3A%20FIRST_NAME%20LAST_NAME%0A-%20My%20time%20zone%20is%3A%20TIME_ZONE%0A-%20My%20working%20hours%20are%20from%3A%20TIME%20till%20TIME%0A-%20My%20company%20name%20is%3A%20COMPANY%20NAME%0A-%20My%20company%20website%20is%3A%20https%3A%2F%2F%0A%0ABest%20regards.).