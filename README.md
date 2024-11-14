<h1>AWS Lift-and-Shift VProfile Project</h1>

<h2 id="overview">Overview</h2>
<p>
  This project demonstrates the deployment of a multi-tier web application stack on AWS, using a lift-and-shift strategy to migrate a production environment. The architecture leverages 
  AWS services such as EC2, ELB, S3, Route 53, IAM, and Auto Scaling to create a scalable, reliable, and secure environment.
</p>

<h2 id="architecture">Architecture</h2>

![image](https://github.com/user-attachments/assets/e92cbfe0-d45c-4beb-8505-44669a561570)


<p>
    The architecture for this project includes the following components:
</p>
<ul>
    <li><strong>Elastic Load Balancer (ELB)</strong>: Distributes incoming traffic across multiple EC2 instances to ensure reliability.</li>
    <li><strong>Auto Scaling</strong>: Automatically adjusts the number of EC2 instances based on demand, maintaining availability and cost-effectiveness.</li>
    <li><strong>EC2 Instances</strong>: Hosts different parts of the application including:
        <ul>
            <li><strong>Tomcat</strong>: Runs the VProfile application.</li>
            <li><strong>RabbitMQ</strong>: Manages message queues for asynchronous communication.</li>
            <li><strong>Memcached</strong>: Provides distributed caching to improve application speed.</li>
            <li><strong>MySQL</strong>: Stores the application’s data in a managed relational database.</li>
        </ul>
    </li>
    <li><strong>S3 Bucket</strong>: Stores the WAR file for deployment, fetched by the Tomcat servers on startup.</li>
    <li><strong>Route 53</strong>: Provides DNS routing, mapping a custom domain to the application’s ELB.</li>
    <li><strong>IAM</strong>: Manages access and permissions to AWS resources for security.</li>
    <li><strong>ACM</strong>: Provides SSL certificates for HTTPS.</li>
</ul>

<h2 id="prerequisites">Prerequisites</h2>
<p>Before deploying this application, make sure you have the following:</p>
<ol>
    <li><strong>JDK 11</strong></li> 
    <li><strong>Maven 3</strong></li> 
    <li><strong>MySQL 8</strong></li>
    <li><strong>AWS Account</strong></li>
    <li><strong>IAM Roles</strong>:
        <ul>
            <li><strong>EC2 Role</strong> with permissions for S3, Auto Scaling, and CloudWatch.</li>
        </ul>
    </li>
    <li><strong>SSL Certificate</strong>: SSL certificate from <strong>AWS Certificate Manager (ACM)</strong> for HTTPS traffic on ELB.</li>
    <li><strong>AWS CLI</strong>: Installed and configured on your local machine.</li>
    <li><strong>Infrastructure as Code (Optional)</strong>:
        <ul>
            <li><strong>CloudFormation or Terraform</strong> templates if you plan to automate the deployment.</li>
        </ul>
    </li>
</ol>

