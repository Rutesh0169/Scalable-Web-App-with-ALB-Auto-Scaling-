step 1 : first we should have the AWS account created or with IAM User you can login.
=
<img width="1918" height="760" alt="image" src="https://github.com/user-attachments/assets/caa52312-8ebf-41b7-8fa8-a38b4abd6974" />

Step 2.AMI creation.
=

An EC2 instance was launched using Amazon Linux 2023. After connecting via SSH, necessary software such as Apache (httpd) was installed and configured to display a basic webpage. Once the instance was set up, it was converted into an Amazon Machine Image (AMI) to enable consistent replication of the configured environment.
<img width="1918" height="794" alt="image" src="https://github.com/user-attachments/assets/0d1a4553-bb49-477e-9853-23696e0e70b2" />


Step 3. Security Group Configuration:
=


A security group was created to control access to the instance. Inbound rules were added to allow HTTP (port 80) from anywhere and SSH (port 22) from a specific IP. Outbound rules were left at default to permit all traffic. This ensured secure and functional access for both web and administrative purposes.
: Inbound rules showing HTTP and SSH
<img width="1910" height="800" alt="image" src="https://github.com/user-attachments/assets/d51c8c45-cfc3-4c63-8b20-d641c71ca5f7" />


Step 4. Launch Template Configuration.
=
Next, a Launch Template was created using the previously configured AMI. This template specified the instance type, key pair, and other configurations such as startup scripts (if any). The Launch Template serves as a reference for<img width="1901" height="767" alt="image" src="https://github.com/user-attachments/assets/6e2b7785-9fe5-4ab4-8b23-e9dc4cf2796a" />

the Auto Scaling Group (ASG) to launch new instances based on the same settings, allowing for consistency and scalability in the infrastructure

Step 5. Auto Scaling Group Setup:
=
An Auto Scaling Group (ASG) was configured with the Launch Template. It was set with a minimum of 1, desired capacity of 2, and a maximum of 3 instances. Health checks and a target tracking scaling policy were configured to maintain optimal performance based on CPU usage.
: ASG creation page with minimum, maximum, and desired capacity settings.
<img width="1908" height="766" alt="image" src="https://github.com/user-attachments/assets/7ba15596-b309-419d-90f7-858dc53d7487" />
<img width="1912" height="772" alt="image" src="https://github.com/user-attachments/assets/fc25ae0b-383f-4c2c-9d1b-905a8965f381" />


Step 6. Load Balancer and Target Group
=
An Application Load Balancer (ALB) was created and linked to a Target Group. The ASG was associated with this Target Group to ensure traffic was distributed evenly across healthy instances.

<img width="1904" height="758" alt="image" src="https://github.com/user-attachments/assets/cd5f60b9-98c3-4a22-8f88-267b4c2f1c85" />
<img width="1920" height="472" alt="image" src="https://github.com/user-attachments/assets/ab7841e5-04b5-41be-85d5-68cd695dc55a" />


Step 7. Testing and Scaling Verification.
=
The final step involved testing the setup by simulating a scaling event. This was done by generating CPU load on the instances, triggering the ASG to scale in or out. The ALB’s traffic distribution was verified to ensure that requests were being appropriately routed to healthy instances. The scaling policies worked as expected, confirming that the system could handle varying levels of load and scale automatically as needed
<img width="1740" height="820" alt="image" src="https://github.com/user-attachments/assets/85924389-b323-4296-b130-b030785924bc" />
