# Scalable-Web-App-with-ALB-Auto-Scaling-

🧠 Objective
=
This project focused on designing and deploying an automated scaling infrastructure using Amazon Web Services (AWS). The primary objective was to set up an environment that dynamically scales based on the workload, ensuring high availability and cost efficiency. The process involved several key AWS services, including EC2, AMI, Launch Template, Auto Scaling Group (ASG), Load Balancer (ALB), and Target Group, along with proper. security configurations to ensure safe and optimized operations

🏗️ Architecture Overview
=
🔁 Flow:
1. Users send requests to the application.
2. Requests hit the Application Load Balancer (ALB).
3. The ALB distributes traffic to one or more EC2 instances inside an Auto Scaling Group.
4. CloudWatch monitors resource metrics (e.g., CPU utilization).
5. Based on scaling policies, EC2 instances are automatically added or removed.
6. New instances are registered with the Load Balancer seamlessly.
