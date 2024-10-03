# AWS Three Tier Web Architecture Workshop

## Description: 
This workshop is a hands-on walk through of a three-tier web architecture in AWS. We will be manually creating the necessary network, security, app, and database components and configurations in order to run this architecture in an available and scalable manner.

## Architecture Overview
![AWS Architecture - DrawIO](https://1drv.ms/i/s!AgPaaDlUA1VAsDpNdaRbROIaQwZW?embed=1&width=1290&height=741)
<img src="https://1drv.ms/i/s!AgPaaDlUA1VAsDpNdaRbROIaQwZW?embed=1&width=1290&height=741" width="1290" height="741" />

In this architecture, a public-facing Application Load Balancer forwards client traffic to our web tier EC2 instances. The web tier is running Nginx webservers that are configured to serve a React.js website and redirects our API calls to the application tier’s internal facing load balancer. The internal facing load balancer then forwards that traffic to the application tier, which is written in Node.js. The application tier manipulates data in an Aurora MySQL multi-AZ database and returns it to our web tier. Load balancing, health checks and autoscaling groups are created at each layer to maintain the availability of this architecture.
