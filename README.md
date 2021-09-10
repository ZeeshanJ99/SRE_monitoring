## Monitoring with AWS cloud watch

![image](https://user-images.githubusercontent.com/88186084/132836084-f2ec54f2-9827-4a97-8c73-a1ca1a299f77.png)

-------------------------------------------------------------------

## Scalability with Autoscaling group and High availability with ALB Application Load Balancer
Todays task will involve using a launch template to create an autoscaling group on AWS for our app machine in order to monitor it.

------------------------------------------------------------------

## Create a launch template for an existing EC2 instance
In order to create an Auto-scaling group, you must first create a launcg template for the existing EC2 app instance that you have. You can do this by the following:

Select your app instance on AWS and choose `Actions`, `Image and templates`, `Create template` from `instance`.

![image](https://user-images.githubusercontent.com/88186084/132847882-b5f1c6ec-50f9-44f6-a227-3e9c53ffba89.png)


- Provide a name and description. `SRE_zeeshan_Launch_Template`

- Under Auto Scaling guidance, select the check box.

- Under `Network settings` select the security group you are using for the app instance

![image](https://user-images.githubusercontent.com/88186084/132848978-ef1a8d5b-18c8-44b6-bd58-55d269207065.png)

- Select `Create launch template`

----------------------------------------------------------------------------

## Create an Auto Scaling group
From our Launch Template we will now create our Auto Scaling group. In order to create an Auto Scaling group, you can choose `Create Auto Scaling group` from the confirmation page of the Launch template we have just created, or you can navigate to it on the left hand side of the EC2 AWS page.

![image](https://user-images.githubusercontent.com/88186084/132849708-65ba9688-a32f-416f-a7de-558576c6bb9c.png)

---------------------------------------------------------

### Step 1
Once on the Auto Scaling groups page, click `create Auto Scaling group`

- Add a name `SRE_zeeshan_AS` and select the launch template that we have built

![image](https://user-images.githubusercontent.com/88186084/132850054-106536e5-68e9-4607-8060-27574f337d12.png)

------------------------------------------------------

### Step 2 Configure settings

- Adhere to the `launch template`

- Select `subnet 1a`

![image](https://user-images.githubusercontent.com/88186084/132858252-1e74a613-8319-468d-8d09-1747d5d93246.png)

---------------------------------------------------

### Step 3 Configure advanced options

- Attach to a new load balancer

What is a load balancer

![image](https://user-images.githubusercontent.com/88186084/132836129-76b156d9-9524-4cc9-9f2c-1df28e615301.png)

- Create the load balancer scheme 
- `internet facing`
- Add a `name`
- Select `Enable group metrics collection within CloudWatch`

![image](https://user-images.githubusercontent.com/88186084/132859684-e1c87b89-4434-4851-b033-0f5796510e79.png)

----------------------------------------------------------

### Step 4 Configure group size and scaling policies
- Set the group size as follows

![image](https://user-images.githubusercontent.com/88186084/132860461-2221d5d3-fe63-4144-9712-cb463cad39cb.png)

- Select the `Target tracking sales policy`

-------------------------------------------------------------

### Step 5 Add Notifications
= Second Iteration - SNS to send notification email/message 

------------------------------------------------------------

### Step 6 Add Tags
Add a `name` and `description` tag

![image](https://user-images.githubusercontent.com/88186084/132860914-f709d806-1625-4b70-9833-a726a97e2538.png)

-------------------------------------------------------------

### Step 7 Create Auto Scaling group
Now click create the Auto Scaling group!
