# Quick Deployment Instructions for NocoBase

## Service Description

NocoBase is a highly extensible open-source no-code development platform. Instead of spending years and millions in R&D,
deploy NocoBase in minutes and instantly have a private, controllable, and easily extensible no-code development
platform.  
Official NocoBase website: [https://www.nocobase.com/](https://www.nocobase.com/).

## Service Architecture

The deployment architecture of the service constructed by this service template is a single ECS deployment.  
![Architecture](architecture_en.png)

## Billing Description

When users deploy the constructed service, resource fees mainly involve:

- Selected ECS instance specifications
- Disk capacity
- Public network bandwidth

Billing methods include:

- Pay-as-you-go (hourly)
- Subscription (yearly/monthly)

Estimated costs can be seen in real-time before deployment.

## Required RAM Account Permissions

This service template requires access and creation operations on ECS, VPC, and other resources. If using a RAM user to
create a service instance, ensure to add the required resource permissions to the RAM user account beforehand. For
detailed operations on adding RAM permissions, please refer
to [Authorize RAM User](https://help.aliyun.com/document_detail/121945.html). Required permissions are shown in the
table below:

| Permission Policy Name              | Description                                                |
|-------------------------------------|------------------------------------------------------------|
| AliyunECSFullAccess                 | Permissions to manage Elastic Compute Service (ECS)        |
| AliyunVPCFullAccess                 | Permissions to manage Virtual Private Cloud (VPC)          |
| AliyunROSFullAccess                 | Permissions to manage Resource Orchestration Service (ROS) |
| AliyunComputeNestUserFullAccess     | User-side permissions for ComputeNest Service              |
| AliyunComputeNestSupplierFullAccess | Supplier-side permissions for ComputeNest Service          |

## Service Instance Deployment Process

### Deployment Parameter Description

| Parameter Group            | Parameter Item    | Description                                                                                                                                                              |
|----------------------------|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Service Instance           | Instance Name     | Must not exceed 64 characters, start with a letter, and can include numbers, letters, hyphens (-), and underscores (_).                                                  |
|                            | Region            | The region where the service instance is deployed.                                                                                                                       |
|                            | Payment Type      | Resource billing type: Pay-as-you-go or Subscription.                                                                                                                    |
| ECS Instance Configuration | Instance Type     | ECS instance specification configuration.                                                                                                                                |
|                            | Instance Password | Length between 8-30 characters, must include at least three of the following: uppercase letters, lowercase letters, numbers, and special characters from ()`~!@#$%^&*-+= |{}[]:;'<>,.?/. |
| Network Configuration      | Availability Zone | The availability zone where the ECS instance is located.                                                                                                                 |

### Deployment Steps

1. Click [Deployment Link](https://computenest.console.aliyun.com/service/instance/create/default?type=user&ServiceName=NocoBase%20%E7%A4%BE%E5%8C%BA%E7%89%88)
to enter the service instance deployment page.

2. Select "Create a New ECS Instance" and configure parameters as prompted. After configuration, click "Next: Confirm
   Order."  
   <img src="img_1_en.png" alt="image" style="width: 800px; height: auto;" />

3. Click "Create Now" and wait for the service instance to complete creation.  
   <img src="img_2_en.png" alt="image" style="width: 800px; height: auto;" />

4. Once the service instance is successfully created, go to the service instance details page. Login information for
   NocoBase can be obtained on the overview page. Initial account: admin@nocobase.com, password: admin123. For other
   default configurations, refer to the NocoBase Docker Compose deployment
   documentation: [NocoBase Docs](https://docs.nocobase.com/welcome/getting-started/installation/docker-compose).  
   <img src="img_3_en.png" alt="image" style="width: 800px; height: auto;" />

5. Click the external network panel address to access the NocoBase service.  
   <img src="img_4.png" alt="image" style="width: 800px; height: auto;" />
