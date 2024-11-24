- [Understanding Monitoring and Alerting Services](#understanding-monitoring-and-alerting-services)
  - [AWS Monitoring Overview](#aws-monitoring-overview)
  - [What Can Be Monitored on AWS?](#what-can-be-monitored-on-aws)
  - [AWS Metrics Overview](#aws-metrics-overview)
  - [What is AWS CloudWatch?](#what-is-aws-cloudwatch)
  - [Introduction to AWS CloudWatch](#introduction-to-aws-cloudwatch)
  - [Monitoring Metrics via AWS CloudWatch](#monitoring-metrics-via-aws-cloudwatch)
  - [Introduction to AWS SNS](#introduction-to-aws-sns)
- [AWS CloudWatch Deep Dive](#aws-cloudwatch-deep-dive)
  - [AWS CloudWatch Dashboards](#aws-cloudwatch-dashboards)
  - [AWS CloudWatch Alarms](#aws-cloudwatch-alarms)
  - [AWS CloudWatch Features\*\*](#aws-cloudwatch-features)
- [Introduction to Monitoring and Alerting for AWS EC2](#introduction-to-monitoring-and-alerting-for-aws-ec2)
  - [Monitoring AWS EC2 Instances](#monitoring-aws-ec2-instances)
  - [AWS EC2 and CloudWatch Alarms](#aws-ec2-and-cloudwatch-alarms)
  - [AWS EC2 System Checks and Metrics](#aws-ec2-system-checks-and-metrics)
  - [Adding Custom Metrics for AWS EC2\*\*](#adding-custom-metrics-for-aws-ec2)
  - [Pushing Custom Metrics from AWS EC2 to CloudWatch\*\*](#pushing-custom-metrics-from-aws-ec2-to-cloudwatch)
- [Introduction to AWS Elastic Block Store (EBS)](#introduction-to-aws-elastic-block-store-ebs)
  - [AWS EBS Volume Type](#aws-ebs-volume-type)
  - [Monitoring AWS EBS Volumes\*\*](#monitoring-aws-ebs-volumes)
- [Introduction to Monitoring and Alerting for AWS RDS](#introduction-to-monitoring-and-alerting-for-aws-rds)
  - [Monitoring AWS RDS Metrics\*\*](#monitoring-aws-rds-metrics)
  - [AWS RDS Events\*\*](#aws-rds-events)
- [Introduction to Monitoring and Alerting for AWS Elastic Load Balancer (ELB)](#introduction-to-monitoring-and-alerting-for-aws-elastic-load-balancer-elb)
  - [Deploying an AWS Elastic Load Balancer (ELB)](#deploying-an-aws-elastic-load-balancer-elb)
  - [Key Metrics for Monitoring AWS Elastic Load Balancers (ELB)](#key-metrics-for-monitoring-aws-elastic-load-balancers-elb)
  - [Steps for Monitoring AWS Elastic Load Balancer (ELB) Metrics](#steps-for-monitoring-aws-elastic-load-balancer-elb-metrics)
- [AWS Billing and Cost Monitoring](#aws-billing-and-cost-monitoring)
  - [Step-by-Step Guide for Monitoring AWS Billing](#step-by-step-guide-for-monitoring-aws-billing)
  - [Setting Up AWS Billing Reports in S3](#setting-up-aws-billing-reports-in-s3)
- [Introduction to Cloud Computing and AWS](#introduction-to-cloud-computing-and-aws)
  - [Benefits of AWS Cloud](#benefits-of-aws-cloud)
  - [Who is Using AWS and Why?](#who-is-using-aws-and-why)
  - [AWS Services Overview](#aws-services-overview)


# Understanding Monitoring and Alerting Services

1. **Overview of Monitoring and Alerting**:  
   - **Monitoring** tracks system resources and performance, providing insights into infrastructure health, service availability, and application stability.
   - **Alerting** notifies teams about issues in real-time, enabling proactive actions. Alerts can also trigger automated tasks (e.g., launching a new EC2 instance if one fails).

2. **Key AWS Services**:
   - **CloudWatch**: AWS's primary monitoring tool, tracking metrics like CPU usage, memory, disk speeds, and custom application metrics. It can also monitor logs and set alarms to automate responses to changes.
   - **SNS (Simple Notification Service)** and **SES (Simple Email Service)**: These services handle alert notifications to operational teams when metrics exceed thresholds, ensuring timely responses.

## AWS Monitoring Overview

1. **AWS Console Overview**:  
   - AWS offers various monitoring and alerting services, accessible via the AWS Management Console, where services are categorized for easy navigation.
   - **CloudWatch**: This is the main service for monitoring AWS cloud resources. The CloudWatch console provides several features like dashboards, alarms, events, logs, and metrics, which will be covered in future lessons.

2. **Search Functionality**:  
   - If you're having trouble finding a specific service, you can use the search box at the top of the console to quickly locate services like **SNS (Simple Notification Service)**, which is used for push messaging and alerts.

## What Can Be Monitored on AWS?

**Infrastructure and Resource Health**:  
  **Key Metrics**: Monitoring infrastructure health, like EC2 CPU utilization, is crucial. High CPU usage indicates potential issues, such as slow performance or downtime. Proactive monitoring allows you to take action (e.g., load balancing, throttling requests) before problems escalate.

**Cost and Usage Monitoring**:  
  Cloud's "pay-as-you-go" model can lead to unexpected charges if resources are over-provisioned or not properly terminated. Monitoring your AWS billing is essential to avoid surprises. You can set alerts for when your spending reaches predefined thresholds to stay within budget.

**Custom Metrics and Application Logs**:  
  In addition to AWS's built-in metrics, you can monitor custom application workloads, such as processing time for tasks. CloudWatch can also track errors in your application logs, alerting you when certain thresholds are exceeded (e.g., a high number of 404 errors).

By using **CloudWatch** for both built-in and custom metrics, you can ensure the health of your infrastructure, control costs, and maintain application performance.

## AWS Metrics Overview

1. **Service-Specific Metrics**:  
   Each AWS service you use provides its own set of metrics for monitoring. These include:
   - **EC2** metrics (e.g., CPU utilization, disk I/O)
   - **RDS** metrics (e.g., CPU credit usage, read/write operations)
   - **S3** metrics (e.g., bucket size, request count)
   - **CloudFront** metrics (e.g., requests, data transfer)

2. **Viewing Metrics**:  
   Within CloudWatch, you can view detailed metrics by selecting the service (e.g., EC2, RDS, S3). Once selected, you can see a graph of the data collected for those metrics. For example, viewing RDS CPU credit usage or S3 bucket data for a specific time frame (e.g., last week).

3. **Alerting with SNS**:  
   CloudWatch metrics can be connected to **Simple Notification Service (SNS)** for setting up alerts. You can create an SNS topic, which acts as a communication channel for sending alerts. Subscriptions can be created to deliver alerts via various communication protocols (e.g., email, SMS).

By utilizing **CloudWatch** and **SNS**, you can continuously monitor the health of your resources and be notified in real time if metrics exceed specified thresholds.

## What is AWS CloudWatch?

**AWS CloudWatch** is a comprehensive monitoring service for AWS resources that provides:

1. **Metrics Collection**:  
   CloudWatch collects and tracks metrics from various AWS services, as well as custom applications running in your AWS infrastructure.

2. **Logs Monitoring**:  
   CloudWatch can monitor logs from both AWS services and custom applications, centralizing all diagnostic information in one place.

3. **Alarms and Notifications**:  
   CloudWatch allows you to create alarms based on tracked metrics. These alarms can send notifications via **SMS** or **email**, and can also trigger **automated actions**, such as running a script, calling an API, or executing custom code.

4. **Automated Actions for Proactive Resolution**:  
   Automated actions triggered by alarms can resolve issues proactively, providing operations teams with time to analyze and make informed decisions.

## Introduction to AWS CloudWatch

1. **S3 Metrics Example**:  
   - CloudWatch can monitor metrics from AWS services like **S3**. For example, tracking the total number of objects in a bucket.
   - In the example, CloudWatch tracks the number of objects in an S3 bucket called "templates," and the goal is to ensure the number of objects does not exceed 66.

2. **Setting Alarms**:  
   - You can configure **alarms** in CloudWatch to take actions when thresholds are breached (e.g., if the number of objects exceeds 66).
   - Actions upon alarm triggering include sending **notifications**, or taking automated actions like:
     - **AWS Lambda** functions to remove newly added objects.
     - **Autoscaling actions** for EC2 instances.

3. **Automation and Efficiency**:  
   - CloudWatch, along with other AWS services, enables **automated management** of resources, even outside of working hours, making the process highly efficient with minimal human intervention.

## Monitoring Metrics via AWS CloudWatch

1. **Visualizing Multiple Metrics**:  
   - CloudWatch allows you to plot multiple metrics on a **single graph** for easy comparison.  
   - Example: Monitoring the number of objects in two different **S3 buckets** can help visualize how they relate and track resource usage.

2. **Real-Time Updates**:  
   - The graphs are **real-time** and update continuously, providing an immediate overview of the system's performance.

3. **Event Streaming for Resource Changes**:  
   - CloudWatch can also monitor **changes** in AWS resources (e.g., new EC2 instances).  
   - When a change is detected, an **alarm** can trigger actions such as invoking an **AWS Lambda function** or running a custom **CLI script**.  

4. **Custom Metrics**:  
   - CloudWatch allows the submission of **custom metrics**, such as application-specific data (e.g., failed login attempts, order counts).  
   - These custom metrics can also have **alerts** set, offering flexibility to monitor both **AWS resources** and **application-level metrics**.

## Introduction to AWS SNS

**AWS SNS (Simple Notification Service)** is a fast, flexible, fully managed push notification service that allows sending messages to **multiple recipients** across different platforms. It's integrated with various AWS services like CloudWatch, providing a simple and cost-effective way to manage notifications and alerts.

Here are the key features and steps covered in the session:

1. **Core Functionality**:  
   - SNS allows sending notifications via **SMS**, **email**, or HTTP(S) to **other services** like **Lambda** and **SQS**.  
   - It follows a **publish-subscribe (pub/sub)** model: a message is published to a **topic**, and all subscribed endpoints receive it.

2. **Integration with AWS CloudWatch**:  
   - CloudWatch alarms can be configured to send notifications directly to **SNS topics** when triggered.  
   - No need for complex messaging systems; CloudWatch and SNS work seamlessly together.

3. **Creating Topics and Subscriptions**:  
   - A **topic** is created, and **subscriptions** can be added (e.g., **email**, **SMS**, **Lambda**).  
   - Subscribers must **confirm** their subscription, ensuring notifications aren't sent to unintended recipients.

4. **Using SNS for Monitoring and Alerting**:  
   - Example: An **S3 bucket alarm** triggers when the number of objects exceeds a certain threshold.  
   - SNS sends a notification to the subscribed endpoint (like an email) informing the team of the triggered alarm.

5. **Flexibility of SNS**:  
   - It supports various protocols for message delivery, making it versatile for diverse IT infrastructures.  
   - **SMS** is commonly used for direct mobile notifications, and **SQS** can be used for queuing messages for processing by other systems or applications.

# AWS CloudWatch Deep Dive

AWS **CloudWatch** is the central monitoring service provided by AWS for observing and managing infrastructure and application performance.

**Key Features and Concepts**

1. **Core Functionality**:
   - **Metrics Collection**: CloudWatch collects native AWS service metrics (e.g., EC2, S3) and **custom metrics** from applications.
   - **Alarms**: Monitors metrics against thresholds over specified periods and triggers actions when thresholds are breached.

2. **Alarm States**:
   - **OK**: Metric is within the defined threshold.
   - **ALARM**: Metric exceeds the threshold, triggering notifications or actions.
   - **INSUFFICIENT DATA**: Not enough data to evaluate the alarm state.

3. **Key Use Cases**:
   - **AWS Infrastructure Monitoring**: Tracks EC2 instances, RDS databases, load balancers, etc., with no additional configuration needed.
   - **Application Monitoring**: Observes microservices and custom applications to ensure optimal performance and uptime.
   - **Log Management**: Aggregates and monitors logs from various sources, simplifying troubleshooting.
   - **Real-Time Alerts**: Sends notifications (via **SNS**) or takes automated corrective actions (e.g., auto-scaling EC2 instances during high CPU usage).

4. **Rich Integration**:
   - **SNS**: Sends notifications via email, SMS, or HTTP(S).
   - **SQS**: Queues messages for further processing.
   - **Lambda**: Executes custom code based on alarm states.
   - **Auto Scaling**: Dynamically adjusts EC2 instance count based on metrics like CPU utilization.

**Advanced Features**

1. **Dashboards**:
   - Provides consolidated views of multiple metrics for easier monitoring.
   - Customizable with text, images, and cross-region data, offering global visibility.

2. **Flexibility**:
   - Can integrate with API endpoints and trigger workflows based on metrics and alarms.
   - Scales seamlessly with infrastructure and supports real-time analysis of critical components.

## AWS CloudWatch Dashboards

This session covers the creation and customization of AWS CloudWatch Dashboards, a feature that enables users to visualize and monitor multiple metrics in one consolidated view. Dashboards provide flexibility in configuring, comparing, and analyzing metrics from various AWS resources.

**Steps to Create a CloudWatch Dashboard**

1. **Navigate to Dashboards**:
   - Access the CloudWatch admin panel and click on the **Dashboards** link.
   - If no dashboards exist, click **Create Dashboard**.

2. **Name the Dashboard**:
   - Enter a name (e.g., "AWS Demo") and confirm to proceed.

3. **Select Visualization Type**:
   - Choose from four visualization options:
     - **Line**: Compare metrics over time.
     - **Stacked Area**: Display total value trends over time.
     - **Number**: Show the latest metric value.
     - **Text**: Add descriptive text with Markdown formatting.

4. **Configure Metrics**:
   - Select the desired metric (e.g., **CPU Utilization**) for visualization.
   - Filter metrics by typing keywords (e.g., "CPU") in the search bar.
   - Choose specific instances or services to track.

5. **Set Time Dimensions**:
   - Adjust timeframes (e.g., 1 hour, 12 hours, 1 day, 1 week) for visualizing data.
   - Ensure the selected time period matches the data availability.

6. **Customize Visualization**:
   - Combine metrics from multiple AWS services (e.g., EC2, S3, RDS) for correlation.
   - Add or modify metrics directly on the graph.
   - Switch between different statistics (e.g., average, maximum) or change visualization types (e.g., line to stacked area).

7. **Fine-Tune Settings**:
   - Adjust **Y-axis limits**, **graph options**, or **refresh intervals** (e.g., 1 minute, 5 minutes, 15 minutes).
   - Pin dashboards for easy access and add widgets for additional metrics.

8. **Save and View Dashboard**:
   - Click **Create Widget** to save the visualization.
   - Use the **Dashboards tab** to view and manage created dashboards.

**Key Features of CloudWatch Dashboards**

1. **Customizability**:
   - Combine metrics from multiple AWS services on a single dashboard.
   - Use different visualization types to fit specific use cases.

2. **Cross-Region Support**:
   - Pull data from multiple AWS regions for a global view.

3. **Real-Time Monitoring**:
   - Set refresh intervals to automatically update visualizations with the latest data.

4. **Interactive Controls**:
   - Modify metrics, timeframes, and graph styles on the fly for deeper insights.

**Benefits of Using Dashboards**
- Centralized monitoring of resources for better operational efficiency.
- Easy correlation between metrics from different services.
- Improved visibility for troubleshooting and performance optimization.

By leveraging CloudWatch Dashboards, teams can gain actionable insights into their AWS infrastructure and applications, ensuring a well-monitored, efficient cloud environment.

## AWS CloudWatch Alarms

AWS CloudWatch Alarms are a powerful tool for monitoring metrics and triggering notifications or actions when defined thresholds are breached. These alarms are essential for proactive system monitoring and automation in AWS environments.

**Key Features of CloudWatch Alarms**

1. **Alarm States**:
   - **Alarm**: Triggered when the metric exceeds the defined threshold.
   - **Insufficient Data**: Indicates that there isn’t enough data to evaluate the metric.
   - **OK**: Metric remains within the specified threshold.

2. **Actions on Alarms**:
   - Send notifications via Amazon SNS (email, SMS, etc.).
   - Trigger auto-scaling activities.
   - Perform custom actions like stopping or rebooting an EC2 instance.

**Steps to Create a CloudWatch Alarm**

1. **Navigate to Alarms**:
   - Open the **CloudWatch Dashboard** and click on the **Alarms** link.

2. **Select a Metric**:
   - Click **Create Alarm** to view available metrics.
   - Choose a metric, such as **CPU Utilization** for an EC2 instance.
   - Specify the statistic (e.g., maximum, average) and period (e.g., 1 minute).

3. **Define the Alarm Threshold**:
   - Name the alarm (e.g., "EC2 CPU Utilization Alarm").
   - Set a description (optional).
   - Define the condition (e.g., CPU Utilization ≥ 60% for 15 minutes).
   - Optionally, specify consecutive periods for more complex conditions.

4. **Configure Actions**:
   - Choose the alarm state that triggers the action (e.g., **Alarm** or **OK**).
   - Attach an SNS topic for notifications (ensure subscribers are set up).
   - Optionally configure auto-scaling or EC2-specific actions.

5. **Review and Create**:
   - Confirm the configuration and click **Create Alarm**.

6. **Monitor Alarm States**:
   - After creation, the alarm may start in the **Insufficient Data** state until metrics are collected.
   - Once sufficient data is available, the alarm transitions to **OK** or **Alarm**.

**Best Practices**

- **Test Alarms**: Use test thresholds (e.g., CPU ≥ 1%) to quickly observe alarm behavior.
- **Notification Topics**: Use well-defined SNS topics with appropriate subscribers for notifications.
- **Investigate Insufficient Data**: Ensure metrics are properly collected if alarms frequently enter this state.
- **Combine with Auto-Scaling**: Leverage alarms to dynamically adjust resources in response to traffic spikes.

**Use Case Example**

- **Scenario**: Monitor EC2 instance CPU utilization.
- **Threshold**: Trigger an alarm when CPU usage exceeds 80% for 10 minutes.
- **Action**: Notify the admin via email and automatically add another EC2 instance to the load balancer.

By effectively using AWS CloudWatch Alarms, you can maintain high availability, optimize performance, and proactively manage AWS infrastructure.

## AWS CloudWatch Features**

AWS CloudWatch provides comprehensive monitoring, alerting, and logging tools to manage and optimize your AWS infrastructure. Here's a breakdown of its key features discussed in this module:

**Key Features**

1. **Billing Alarms**:
   - Monitor **estimated AWS charges**.
   - Trigger notifications or automate actions (e.g., decommissioning resources) as costs exceed defined thresholds.

2. **CloudWatch Events**:
   - Respond to **state changes** in AWS resources.
   - Automate tasks like launching new EC2 instances when needed or stopping unused resources.

3. **CloudWatch Logs**:
   - Collect and analyze logs from services such as Lambda, RDS, or EC2.
   - Search and index logs for troubleshooting and monitoring application health.

4. **CloudWatch Metrics**:
   - Default metrics include CPU utilization, disk I/O, and network traffic.
   - These form the core of CloudWatch’s monitoring capabilities.

5. **Custom Metrics**:
   - Create and monitor custom metrics like **memory usage**, **disk space utilization**, and **swap space**.
   - Use AWS-provided scripts to enable additional insights into resource utilization.

6. **Auto-Scaling Integration**:
   - Dynamically adjust resources based on demand.
   - Example: Scale down EC2 instances during low traffic and scale up when CPU utilization exceeds a threshold (e.g., 75%).

7. **Automatic Recovery**:
   - Automatically reboot or recover failed EC2 instances based on status checks.

8. **Third-Party Integrations**:
   - Integrate with tools like **Copperegg**, **Stackdriver**, or **New Relic** for enhanced performance monitoring and custom dashboards.

**Advanced Metrics with Monitoring Scripts**

CloudWatch allows reporting of additional resource metrics beyond defaults:
- **Memory Metrics**:
  - **Memory Utilization**: Percentage of memory in use.
  - **Memory Available**: Free memory for applications.
- **Disk Metrics**:
  - **Disk Space Utilization**: Percentage of disk space in use.
  - **Disk Space Available**: Free disk space in GB.
- **Swap Space Metrics**:
  - **Swap Space Utilization**: Percentage of swap space used.

**Practical Use Case Examples**

1. **Billing Alerts**:
   - Create a billing alarm to notify admins if costs exceed $500/month.

2. **Dynamic Scaling**:
   - Use auto-scaling rules to maintain a balance between performance and cost, spinning up instances when demand spikes and terminating them during idle periods.

3. **Log Monitoring**:
   - Track RDS logs for database errors and set alarms to notify the admin.

4. **Event-Based Automation**:
   - Trigger a Lambda function to back up databases daily based on a CloudWatch event.

5. **Custom Dashboards**:
   - Combine metrics from multiple AWS services into a single dashboard for centralized monitoring.

CloudWatch’s flexibility and integration options make it an essential tool for DevOps and system monitoring, enabling smarter decision-making and automation in AWS environments.

# Introduction to Monitoring and Alerting for AWS EC2

**Learning Objectives**

1. **Understanding EC2 Monitoring Facilities**:
   - Overview of metrics and alarm functionality specific to EC2.
   - Insights into default and custom metrics.

2. **CloudWatch Integration**:
   - Using **CloudWatch metrics and alarms** to monitor EC2 instances.
   - Automating actions like stopping, restarting, or terminating instances based on alarm triggers.

3. **System-Level Status Checks**:
   - Monitoring overall instance health and performance beyond numeric metrics.

**What is AWS EC2?**
- **Elastic Cloud Compute (EC2)** is AWS's Infrastructure-as-a-Service (IaaS) offering.
- Allows deployment of raw compute power for various applications with customizable operating systems and configurations.

**Key Features of EC2 Monitoring and Alerting**

1. **Default Metrics**:
   - **CPU Utilization**, **disk I/O**, and **network traffic** are available for free.
   - By default, these metrics are reported to CloudWatch every **5 minutes**.
   - **1-minute intervals** can be enabled at an additional cost for higher precision.

2. **Custom Metrics**:
   - Users can define and track specific metrics (e.g., memory or disk space utilization).
   - CloudWatch can be configured to monitor and trigger alarms for these custom metrics.

3. **CloudWatch Alarms and Actions**:
   - Automate responses to alarms (e.g., restart or terminate a malfunctioning instance).
   - Prevent incurring unnecessary costs by stopping non-functional instances.

4. **System-Level Checks**:
   - EC2 provides **status checks** to determine the health of the instance:
     - **System Status Check**: Indicates issues with AWS infrastructure hosting the instance (e.g., networking or power failure).
     - **Instance Status Check**: Reflects problems within the EC2 instance, such as software or OS issues.

5. **Cost Optimization**:
   - Ensures instances that are malfunctioning or idle do not continue incurring charges.
   - Automates replacing problematic instances with healthy ones.

**Advantages of Monitoring EC2 Instances**

- **Proactive Management**:
  - Early detection of issues helps prevent application downtime.
- **Cost Efficiency**:
  - Automating instance termination ensures no unnecessary charges for idle or malfunctioning instances.
- **Customizable Monitoring**:
  - Ability to track metrics specific to your application’s needs, in addition to default metrics.

## Monitoring AWS EC2 Instances

**Steps to Enable EC2 Monitoring**

1. **Launching an EC2 Instance**:
   - Navigate to the **EC2 Management Panel**.
   - Select **Launch Instance**.
   - Choose **Amazon Linux AMI** and a **T2 Micro instance** (free tier eligible).
   - Use default settings to simplify setup, then click **Review and Launch**.

2. **Accessing Monitoring for the Instance**:
   - Once the instance is running, select it and open the **Monitoring Tab**.
   - View available metrics for the EC2 instance.

**Key Monitoring Features**

1. **Basic Monitoring**:
   - Enabled by default.
   - Metrics like **CPU utilization** and **disk usage** are collected every **5 minutes**.

2. **Detailed Monitoring**:
   - Provides data at **1-minute intervals**.
   - Requires manual activation from the **Monitoring Tab**.
   - **Costs extra** due to increased data collection frequency.
   - Useful for **production environments** where fine-grained metrics are critical.

3. **Customizing Metric Views**:
   - Users can adjust the timeframe for metric charts.
   - Clicking on any graph opens a detailed view for deeper analysis.

**When to Use Detailed Monitoring**

- **Mission-Critical Applications**:
  - Essential for monitoring systems where downtime has significant impact.
  - Helps detect performance issues faster than 5-minute intervals.

- **Real-Time Insights**:
  - Enables quick responses to system changes or potential failures.

## AWS EC2 and CloudWatch Alarms

This session focuses on setting up **AWS CloudWatch alarms** to monitor EC2 instance metrics and automate actions like stopping, rebooting, or scaling EC2 instances. 

**Steps to Configure a CloudWatch Alarm for EC2**

1. **Access CloudWatch**:
   - Open the AWS Management Console and navigate to the **CloudWatch Dashboard**.

2. **Choose Metrics**:
   - Go to the **Metrics** section in CloudWatch.
   - Select **EC2 Metrics**, then **Per Instance Metrics**.
   - Locate the desired EC2 instance by searching for its **Instance ID**.

3. **Select a Metric**:
   - From the filtered list, choose a metric, e.g., **CPU Utilization**, to base your alarm on.
   - This metric measures the percentage of allocated EC2 compute units currently in use.

4. **Create Alarm**:
   - Go to the **Alarms** menu and click **Create Alarm**.
   - Define:
     - **Metric**: Select the metric identified earlier (e.g., CPU utilization).
     - **Threshold**: Set the condition for the alarm (e.g., CPU utilization > 0%).
     - **Evaluation Period**: Define how often CloudWatch evaluates the metric.
   - Name the alarm and provide a description.

5. **Configure Actions**:
   - Define what happens when the alarm is triggered:
     - **Notification**: Send alerts via SNS (email, SMS, etc.).
     - **Auto Scaling**: Adjust the number of instances in an auto-scaling group.
     - **EC2 Actions**: Stop, reboot, or terminate the instance.

6. **IAM Role**:
   - Allow CloudWatch to interact with EC2 by creating or assigning an **IAM Role**.

7. **Create Alarm**:
   - Finalize the setup by clicking **Create Alarm**.

**Example Use Case**

- **Scenario**: Monitoring CPU utilization.
- **Threshold**: Set at 0% (for demonstration purposes).
- **Action**: Automatically stop the instance if CPU utilization is greater than 0%.

After creating the alarm, CloudWatch monitors the metric. If the threshold condition is met, the defined action is triggered (e.g., stopping the instance). 

**Key Features of CloudWatch Alarms**

1. **Metric-Based Automation**:
   - React to metric values crossing thresholds.
   - Automate responses like stopping, starting, or scaling instances.

2. **Flexibility in Evaluation**:
   - Configure evaluation periods (e.g., 1 minute, 5 minutes).
   - Customize the number of consecutive periods for alarm triggering.

3. **Integration with AWS Services**:
   - Notifications via **SNS**.
   - Auto-scaling with **EC2 Auto Scaling**.
   - Direct **EC2 instance actions**.

4. **IAM Integration**:
   - Ensures secure access for CloudWatch to manage EC2 actions.

**Practical Tips**

- Use **detailed monitoring** for critical workloads for more frequent evaluations (1-minute intervals).
- Ensure **IAM roles** are set up to allow CloudWatch to execute actions on EC2.
- Test alarms with easily triggered thresholds during setup.
- Set realistic thresholds for production environments to avoid unnecessary actions.

## AWS EC2 System Checks and Metrics

**Two Types of Status Checks**

1. **System Status Checks**:
   - **Purpose**: Monitors the physical hardware and infrastructure hosting your EC2 instance.
   - **Examples of Failures**:
     - Loss of network connectivity.
     - Power failure.
     - Physical hardware issues.
   - **Resolution**:
     - Restart or terminate the instance to migrate it to a healthy host.
     - Wait for AWS to resolve hardware issues.

2. **Instance Status Checks**:
   - **Purpose**: Monitors the software and network configuration on the instance itself.
   - **Examples of Failures**:
     - Incorrect networking or startup configuration.
     - Exhausted memory.
     - Corrupted file system.
     - Incompatible kernel.
   - **Resolution**:
     - Address issues directly (e.g., reboot the instance, adjust configuration).

**Key EC2 Metrics Monitored via CloudWatch**

1. **CPU Utilization**:
   - Measures the percentage of allocated compute units currently in use.
   - Helps gauge instance load and performance.

2. **Disk Read/Write Operations**:
   - Tracks the completed read/write operations from all instance storage volumes.
   - Identifies disk I/O activity and performance.

3. **Network Traffic (In/Out)**:
   - Monitors the number of bytes received and sent via the instance’s network interfaces.
   - Useful for understanding application traffic patterns.

4. **Status Check Failed**:
   - Tracks whether system or instance checks have failed.
   - **Value 0**: Both checks passed.
   - **Value 1**: One or both checks failed.

**How to Access and Monitor Metrics**

1. **EC2 Console**:
   - Navigate to the **EC2 Dashboard**.
   - Select the instance and switch to the **Status Checks** tab.
   - View the status of system and instance checks.

2. **Monitoring Tab**:
   - Provides access to real-time metrics like CPU utilization, network traffic, and disk operations.
   - Graphical representation of metrics over time.

3. **CloudWatch**:
   - Navigate to the **Metrics** section.
   - Access preconfigured metrics or create **custom metrics** for specific monitoring needs.

**Custom Metrics**

- **Purpose**: Extend beyond default metrics to monitor specific application behaviors.
- **Publishing Methods**:
  - Use **AWS CLI** or **AWS SDK/API** to push metrics to CloudWatch.
- **Integration with Alarms**:
  - Set up alarms using custom metrics to trigger notifications or automated actions.

**Practical Recommendations**

- Regularly review **status checks** to catch and resolve issues early.
- Use **alarms** in CloudWatch for critical metrics to automate responses.
- Leverage **custom metrics** for application-specific monitoring needs.
- Address failing **system checks** promptly by restarting or migrating the instance.

## Adding Custom Metrics for AWS EC2**

This session focuses on configuring **custom metrics** for EC2 instances and tracking them using **AWS CloudWatch**. Custom metrics address specific monitoring needs not covered by CloudWatch's default EC2 metrics.

**Why Custom Metrics?**
- CloudWatch offers basic EC2 metrics like CPU usage and network traffic.
- Applications may require tracking metrics specific to their environment, e.g., memory usage, disk space, or application-specific performance.
- Custom metrics provide flexibility to monitor unique requirements.

**Steps to Add Custom Metrics**

**1. Set Up an IAM Role for EC2**
- **Purpose**: Enable EC2 instances to communicate with CloudWatch securely.
- **Steps**:
  1. **Create a Role**:
     - Go to the IAM Management Console.
     - Select **Roles** > **Create New Role**.
  2. **Select Role Type**: Choose **AWS Service** and select **Amazon EC2**.
  3. **Attach Policy**:
     - Use a custom policy or predefined policies with the following permissions:
       - `CloudWatchPutMetricData`
       - `CloudWatchGetMetricStatistics`
       - `CloudWatchListMetrics`
       - `EC2DescribeTags`
  4. **Assign Role Name**: E.g., "custom-metrics-role."
  5. **Complete Setup**: Click **Create Role**.

**2. Launch an EC2 Instance with the IAM Role**
- Use **Amazon Linux 2** or another supported AMI.
- Attach the IAM role (e.g., "custom-metrics-role") during instance configuration.
- Configure security groups, storage, key pair and tags as needed.

**3. Install Required Packages on EC2**
- Use **SSH** to connect to the instance.
- Install **Perl** packages:
  ```bash
  sudo yum install perl-Switch perl-DateTime perl-Sys-Syslog perl-LWP-Protocol-https -y
  ```
**4. Download AWS Monitoring Scripts**
- Download AWS-provided Perl scripts for custom metrics:
  ```bash
  curl https://aws-cloudwatch.s3.amazonaws.com/downloads/CloudWatchMonitoringScripts-1.2.2.zip -O
  unzip CloudWatchMonitoringScripts-1.2.2.zip
  cd aws-scripts-mon
  ```

- Key files:
  - `mon-put-instance-data.pl`: Publishes metrics to CloudWatch.
  - `mon-get-instance-stats.pl`: Gathers instance statistics.
  - `creds.template`: Placeholder for AWS credentials (not needed if IAM role is used).

**5. Configure and Push Custom Metrics**
- Example: Publish memory usage metrics.
  ```bash
  ./mon-put-instance-data.pl --mem-util --mem-used --mem-avail --swap-util --swap-used --disk-path=/ --disk-space-util --disk-space-used --disk-space-avail --from-cron
  ```
  - Options:
    - `--mem-util`: Memory utilization percentage.
    - `--disk-space-util`: Disk usage percentage for a specific path.

- Automate with a **cron job**:
  ```bash
  crontab -e
  ```
  Add:
  ```bash
  */5 * * * * /path/to/aws-scripts-mon/mon-put-instance-data.pl --mem-util --mem-used --disk-space-util --disk-space-used --from-cron
  ```

**Benefits of Custom Metrics**
1. **Application-Specific Insights**: Monitor metrics unique to your workloads.
2. **Custom Alarms**: Use CloudWatch alarms to respond to custom thresholds.
3. **Visualization**: Plot custom metrics alongside default metrics in the CloudWatch console.

## Pushing Custom Metrics from AWS EC2 to CloudWatch**

**Key Files and Their Purpose**

1. **`mon-put-instance-data.pl`**:
   - Collects system metrics like **memory utilization**, **swap usage**, and **disk space**.
   - Sends the metrics to **Amazon CloudWatch**.

2. **`mon-get-instance-stats.pl`**:
   - Queries CloudWatch for the latest metrics and displays them for the instance.

3. **`creds.template`**:
   - Template for storing **AWS access keys** (only needed if IAM roles aren't assigned to the EC2 instance).

**Steps to Push Metrics**

**1. Run the Script**
- Use the `mon-put-instance-data.pl` script to collect and push metrics. Example command:
  ```bash
  ./mon-put-instance-data.pl --mem-util --mem-used --mem-avail --swap-util --swap-used --disk-space-util --disk-space-used --disk-space-avail --from-cron
  ```
- Parameters:
  - `--mem-util`: Memory utilization as a percentage.
  - `--swap-used`: Amount of swap memory used.
  - `--disk-space-util`: Disk utilization for a specified path.

**2. Verify Metrics in CloudWatch**
- Navigate to **AWS CloudWatch Console** > **Metrics** > **All**.
- Look for a new **Linux System** namespace containing:
  - Memory utilization
  - Memory available
  - Memory used
- Confirm that the instance ID matches the EC2 instance where the script was executed.

**Automating with a Cron Job**
To ensure metrics are pushed periodically:

1. Open the **crontab editor**:
   ```bash
   crontab -e
   ```

2. Add a new cron job:
   ```bash
   */5 * * * * /path/to/aws-scripts-mon/mon-put-instance-data.pl --mem-util --mem-used --disk-space-util --disk-space-used --from-cron
   ```
   - This schedules the script to run every 5 minutes.

3. Save and exit the editor.

**Key Insights**
1. **Manual Execution vs Automation**:
   - Running the script manually uploads metrics only once.
   - Scheduling with cron ensures regular metric uploads.

2. **Namespace and Metrics**:
   - Custom metrics are categorized under the **Linux System** namespace in CloudWatch.

3. **Flexibility**:
   - AWS provides boilerplate scripts, but you can extend them to track additional metrics.

**Summary of Module**
- **Learned**: Standard and custom EC2 metrics available in CloudWatch.
- **Implemented**:
  - Setting up IAM roles for EC2 instances.
  - Configuring custom metrics with AWS scripts.
  - Automating metric uploads with cron jobs.

# Introduction to AWS Elastic Block Store (EBS)

**What is AWS EBS?**
- **Elastic Block Storage (EBS)** is a **block-level storage** service that provides persistent storage volumes for **EC2 instances**.
- **Instance Store** is another storage option, but it’s temporary and physically attached to the host machine.
- **EBS** offers greater flexibility since volumes can be **attached**, **detached**, and **reattached** to different EC2 instances within the **same availability zone**, with data preserved even after detaching.

**EBS Volume Types**
EBS volumes come in various types to cater to different workloads:

1. **General Purpose SSD (GP2)**:
   - Balanced performance and cost.
   - Baseline of **3 IOPS per GB**, with performance scaling as the volume size increases (e.g., a **100 GB volume** gets **300 IOPS**).
   - Maximum throughput: **160 MB/sec**.

2. **Provisioned IOPS SSD (IO1)**:
   - High performance for mission-critical applications.
   - Allows you to provision specific **IOPS** for workloads requiring consistent and high throughput.

3. **Throughput Optimized HDD (ST1)** and **Cold HDD (SC1)**:
   - These are optimized for **large, sequential data operations** and are more cost-effective than SSD volumes.

**Key Performance Factors for EBS Volumes**

1. **IOPS (Input Operations Per Second)**:
   - The key measure of performance for EBS volumes.
   - SSD volumes measure IOPS in chunks of **256 KB** (random operations), while HDD volumes measure in **1024 KB** (sequential operations).

2. **Throughput**:
   - A measure of data transfer per second (e.g., **GP2 volumes** can burst up to **160 MB/sec**).

3. **IO Credits**:
   - **GP2 volumes** have a unique feature of accumulating **IO credits**.
   - These credits allow the volume to **burst beyond its baseline performance** when needed, providing flexibility in handling high-demand workloads.
   - If the volume is idle, unused credits are accumulated and can be used during bursts of high activity.

4. **Volume Size and IOPS**:
   - The size of the volume directly affects the **baseline IOPS**. Larger volumes offer more IOPS.


## AWS EBS Volume Type 

**SSD-Based EBS Volumes**  

1. **GP2 (General Purpose SSD)**:  
   - Baseline performance: **3 IOPS per GB**, up to **10,000 IOPS**.  
   - Uses an **IOPS credit system** for bursts beyond baseline performance.  
   - Best suited for general-purpose workloads.  
   - Max throughput: **160 MB/sec**.  

2. **IO1 (Provisioned IOPS SSD)**:  
   - Baseline performance: **30 IOPS per GB**, up to **20,000 IOPS** (10x GP2).  
   - **No credit system**, offering consistent performance.  
   - Ideal for high-throughput applications like databases.  
   - Max throughput: **320 MB/sec**.  


**HDD-Based EBS Volumes**  

1. **ST1 (Throughput Optimized HDD)**:  
   - Optimized for **frequently accessed**, throughput-intensive workloads.  

2. **SC1 (Cold HDD)**:  
   - Designed for **infrequently accessed workloads**.  
   - Most cost-effective EBS option.  

**Key Considerations**  

- **SSD Volumes** are better for applications requiring high **IOPS** and random read/write operations.  
- **HDD Volumes** are optimized for sequential data access and cost-effective for lower performance needs.  
- **IOPS** and **throughput** are critical factors when choosing a volume type for modern applications.  

## Monitoring AWS EBS Volumes**
 

**Monitoring EBS Metrics**  

1. **Metric Tiers**:  
   - **Basic Metrics**: Collected every **5 minutes**.  
   - **Detailed Metrics**: Collected every **1 minute** (default for **IO1** volumes).  

2. **Key Metrics**:  
   - **Read/Write Bandwidth**: Measures available bandwidth for reading/writing data.  
   - **Read/Write Throughput**: Tracks data transfer rates.  
   - **Burst Balance** (for GP2): Tracks accumulated IOPS credits for handling burst activities.  

**Status Checks**  
- **EBS Status Checks**: Automated tests running every **5 minutes**, indicating if the volume is functional:  
  - **OK**: Volume is working properly.  
  - **Impaired**: Volume shows potential data inconsistencies.  

- **Handling Inconsistencies**:  
  - By default, AWS disables I/O for inconsistent volumes.  
  - Users can override this behavior by enabling the **Auto-Enabled Volume Attribute** in specific scenarios (e.g., testing).  

**Key Takeaways**  
- **GP2 Metrics**: Includes IOPS credits for bursts, making it cost-effective for general workloads.  
- **IO1 Metrics**: Provides consistent performance without credit systems, ideal for mission-critical applications.  
- Use **CloudWatch graphs** to track historical trends in metrics like bandwidth, throughput, and burst balance.  

# Introduction to Monitoring and Alerting for AWS RDS

This module focuses on **AWS Relational Database Service (RDS)**, its critical role in applications, and the tools available for monitoring and alerting to maintain optimal performance and reliability.

**Key Topics Covered**  

1. **Overview of AWS RDS**:  
   - A fully managed **PaaS** offering scalable relational databases (e.g., MySQL, PostgreSQL, Oracle, SQL Server, Aurora).  
   - Supports high availability through features like automatic failover between replicas during hardware or software failures.  

2. **Importance of Monitoring RDS**:  
   - Databases are vital for application performance, availability, and user experience.  
   - Monitoring ensures reliability and helps diagnose failures across multiple points in the system.  

3. **Monitoring Options in AWS**:  
   - **CloudWatch Metrics**:  
     - Metrics include **CPU Utilization**, **Database Connections**, **Free Memory**, and many more.  
     - Large variety of metrics available for detailed insights.  
   - **Events**:  
     - Tracks changes to DB instances, snapshots, security groups, and parameter groups.  
     - Can trigger notifications (via email, SMS, etc.) for real-time alerts using **Event Subscriptions**.  
   - **Database Logs**:  
     - Access engine-specific logs (e.g., MySQL error logs, slow query logs).  
     - Logs refresh every 5 seconds for near real-time monitoring.  
     - Logs can be downloaded for deeper analysis.  

4. **Alerting and Automation**:  
   - Set alarms for specific metric thresholds using CloudWatch.  
   - Use **CloudWatch Events** to take corrective actions based on state changes or anomalies.  

## Monitoring AWS RDS Metrics**

**Key RDS Metrics for Monitoring**
1. **CPU Utilization**:  
   - Percentage of CPU used by the database server.  
   - High utilization may indicate resource contention or high workloads.

2. **Database Connections**:  
   - Number of active connections to the RDS instance.  
   - Monitoring ensures optimal usage and avoids connection limits.

3. **Freeable Memory**:  
   - Available RAM on the instance.  
   - Low memory could lead to performance degradation or crashes.

4. **Free Storage Space**:  
   - Available disk space for the database.  
   - Essential for avoiding unexpected downtime due to storage exhaustion.

5. **Read IOPS and Write IOPS**:  
   - Input/Output Operations Per Second for reads and writes.  
   - High values may indicate storage bottlenecks or overload.

6. **Read Latency and Write Latency**:  
   - Average time per read/write operation.  
   - High latency indicates performance issues, often due to storage.


**Using AWS CloudWatch for Monitoring**
1. **Metrics Dashboard**:  
   - View a graphical representation of metrics like CPU, memory, and storage.  
   - Check historical data by changing the time range.  

2. **Events Dashboard**:  
   - Logs actions like backups or configuration changes.  
   - Notifications can be set up for real-time updates via CloudWatch Event Subscriptions.  

3. **Detailed Metric Monitoring**:  
   - Select individual metrics like CPU utilization to view specific trends.  

**Setting Up Alarms for RDS Metrics**
1. **Creating an Alarm**:  
   - Navigate to the monitoring section, click "Create Alarm," and configure:  
     - Metric (e.g., CPU Utilization).  
     - Threshold (e.g., CPU >= 80%).  
     - Notification settings (e.g., email or SNS distribution list).  

2. **Recommended Metrics for Alarms**:  
   - **Free Storage Space**: Avoid running out of disk space.  
   - **DB Connections**: Prevent hitting connection limits.  
   - **Latency Metrics**: Address slow performance promptly.


**Key Takeaways**
- Proactively monitoring key metrics like CPU, memory, storage, and latency ensures high availability and optimal database performance.  
- CloudWatch’s detailed views, alarms, and notifications provide a robust mechanism for managing database health and avoiding downtime.  

## AWS RDS Events**

**Key Concepts**
1. **Importance of Monitoring Events**:  
   - **Why**: Metrics track performance, but **events capture specific configuration changes and operational actions**.  
   - **Goal**: Provide timely notifications to respond quickly to incidents and ensure high availability.

2. **Recommended Domains for Monitoring**:  
   - **Resource Utilization**: CPU, memory, disk space.  
   - **System Errors**: Diagnose issues impacting database availability.  
   - **Accidental Terminations**: Guard against unintended deletions or reboots.  
   - **Cluster Health Maintenance**: Track status in multi-node environments.  
   - **Query Logs**: Audit and optimize query performance.  
   - **Resource Modifications**: Identify unauthorized or unexpected changes.

**Using CloudWatch Events for RDS**
1. **Accessing Events**:
   - Events can be viewed for the past **24 hours in the AWS Management Console** or **14 days via CLI/API**.

2. **Event Types**:
   - Availability, backup, configuration changes, failovers, creation, deletions, and failures.

3. **Event Subscriptions**:
   - Automate notifications for specific categories of events.
   - Steps:
     1. Navigate to **Event Subscriptions** in the console.
     2. Click **Create Event Subscription**.
     3. Provide:
        - **Name**: e.g., "event-subscription".
        - **Target Topic ARN**: Choose an SNS topic (e.g., "alerting admins").
        - **Source Type**: Select resources (instances, clusters, etc.).
        - **Event Categories**: Availability, backup, failover, etc.
        - **Instances**: Choose specific or all instances.
     4. Save the configuration.

**Example: Setting Up and Testing Event Subscriptions**
1. **Subscription Configuration**:
   - Monitor **all event categories** for **all instances**.
   - Link notifications to an email address.

2. **Testing**:
   - Perform a manual action like **rebooting an instance**.
   - Observe events in the console (e.g., shutdown and restart).
   - Confirm **email notifications** for corresponding events.

**Best Practices for RDS Event Monitoring**
- **Critical Events**: Focus on backup completion, failovers, and resource modifications.
- **Operational Policies**: Develop action plans for handling alerts, minimizing response time.
- **Automation**: Use Lambda functions or other automated workflows to respond to specific events.

# Introduction to Monitoring and Alerting for AWS Elastic Load Balancer (ELB)

ELB ensures fault tolerance, scalability, and efficient traffic distribution, making it a vital service for modern applications.

**Key Concepts**

1. **What is AWS ELB?**
   - A **load balancing service** that distributes incoming traffic across multiple EC2 instances or other compute resources.
   - Ensures **fault tolerance**, **scalability**, and **high availability** for applications.

2. **Importance of Monitoring ELB**:
   - **Availability**: As the entry point for applications, an ELB's downtime affects the entire service.
   - **Performance**: Correct functioning ensures that user traffic is routed efficiently.
   - **Key Goals**:
     - Detect potential performance bottlenecks.
     - Minimize downtime.
     - Optimize user experience.

3. **Core Learning Objectives for Monitoring ELB**:
   - **Familiarization with the Service**: Understanding what ELB does and its role in AWS architecture.
   - **Key Metrics**: Identifying the most critical metrics to monitor.
   - **Monitoring Procedures**: Setting up alerts and thresholds to maintain performance.

4. **ELB as a Scaling Enabler**:
   - Automatically adjusts to handle traffic increases by adding compute capacity.
   - Provides seamless load balancing without manual intervention.


## Deploying an AWS Elastic Load Balancer (ELB)

This lesson focuses on deploying an Elastic Load Balancer (ELB) in the AWS environment, covering the setup process, configuration of health checks, and assigning EC2 instances for traffic distribution.

 **Steps to Deploy an AWS ELB**

1. **Accessing the ELB Dashboard**:
   - Navigate to the AWS EC2 Management Console.
   - Select the **Load Balancers** menu.
   - Click **Create Load Balancer**.

2. **Selecting Load Balancer Type**:
   - Choose between:
     - **Classic Load Balancer** (simple routing at the network/application level).
     - **Application Load Balancer** (advanced routing based on content).  
   - For this demo, the **Classic Load Balancer** was selected.

3. **Naming the Load Balancer**:
   - Assign a name (e.g., `Alert ELB`).

4. **Configuring Security Groups**:
   - Security groups act as virtual firewalls.
   - Configure to allow traffic on required ports (e.g., HTTP on port 80 or HTTPS on port 443 for web applications).
   - For the demo, the default VPC security group was used.

5. **Configuring Security Settings**:
   - SSL settings can be added for secure connections (recommended for production).
   - This step was skipped for the demo.

6. **Health Check Configuration**:
   - **Purpose**: Ensures traffic is routed only to healthy EC2 instances.
   - **Key Settings**:
     - **Ping Protocol**: HTTP.
     - **Ping Port**: 80 (default for web servers).
     - **Ping Path**: `index.html` (or any custom path based on the application).
     - **Response Timeout**: Time allowed for an instance to respond (e.g., 5 seconds).
     - **Interval**: Time between health checks (e.g., 30 seconds).
     - **Thresholds**:
       - **Unhealthy Threshold**: Number of consecutive failed checks before marking an instance unhealthy (e.g., 2).
       - **Healthy Threshold**: Number of consecutive successful checks to mark an instance healthy (e.g., 10).

7. **Adding EC2 Instances**:
   - Attach EC2 instances to the ELB for traffic routing.
   - Select two or more instances (even if not running real web servers for the demo).

8. **Adding Tags** (Optional):
   - Tags can help identify resources but were skipped in this demo.

9. **Reviewing and Creating ELB**:
   - Review configuration.
   - Click **Create** to deploy the ELB.

**Health Check Mechanism**
- ELB continuously monitors the health of attached EC2 instances.
- **Healthy Instances**: Instances that pass all health checks.
- **Unhealthy Instances**: Instances that fail health checks are excluded from routing.
- ELB automatically adds instances back to the healthy pool once they recover.

## Key Metrics for Monitoring AWS Elastic Load Balancers (ELB)

 **1. Backend Connection Errors**
- **Definition**: Tracks the number of unsuccessful connections between the ELB and registered EC2 instances.
- **Significance**: High values may indicate connectivity issues, which can result in increased latency or dropped requests.
- **Action**: Investigate EC2 instances or ELB configurations if this value increases.

**2. Latency**
- **Definition**: Measures the time taken to receive a response from backend EC2 instances.
- **Significance**:
  - Key for monitoring application performance.
  - Anomalies (e.g., spikes in maximum latency) may point to bottlenecks, slow database queries, or misconfigurations.
- **Action**:
  - Compare historical average latency against maximum values.
  - Investigate and optimize slow-performing components like specific web pages or database queries.

 **3. Surge Queue Length**
- **Definition**: Represents the number of requests waiting to be routed due to the inability to connect to healthy EC2 instances.
- **Maximum Queue Size**: 1024 requests; additional requests are dropped.
- **Significance**:
  - Indicates overloading or insufficient healthy instances.
  - Persistent queuing can degrade user experience.
- **Action**: Scale up the backend or troubleshoot connectivity issues.

**4. Spillover Count**
- **Definition**: Counts requests dropped when the queue is full.
- **Significance**: Indicates severe capacity issues in handling incoming traffic.
- **Action**: Increase the number of EC2 instances or optimize traffic routing.

**5. Request Metrics**
- **Request Count**: Total number of incoming requests to the ELB.
- **HTTP Status Codes**:
  - Tracks specific status codes (e.g., 2xx, 4xx, 5xx).
  - Helps identify user errors (4xx) or server-side issues (5xx).
- **Significance**:
  - Helps diagnose system-level and application-level issues.
  - Informs troubleshooting for high error rates.
- **Action**: Investigate status codes that deviate from expected patterns.

**6. Healthy Host Count**
- **Definition**: Number of EC2 instances deemed healthy based on health checks.
- **Significance**: Healthy instances are critical for routing traffic and maintaining availability.
- **Action**: Monitor to ensure sufficient capacity to handle traffic.

**7. Unhealthy Host Count**
- **Definition**: Number of EC2 instances deemed unhealthy due to failed health checks.
- **Significance**: Indicates issues with specific instances or their configurations.
- **Action**: Troubleshoot and restore unhealthy instances to operational status.

**Usage Insights**
- **Historical vs. Real-Time Analysis**:
  - Plot historical data to identify trends.
  - Monitor real-time metrics to react to performance or availability issues.
- **Performance Tuning**:
  - Use metrics like latency and request counts to fine-tune your application and backend services.
- **Scalability**:
  - Use surge queue length and healthy host count to determine when to scale EC2 instances or load balancer capacity.

## Steps for Monitoring AWS Elastic Load Balancer (ELB) Metrics

**1. Navigating the ELB Metrics in AWS Console**
- **Instance Tab**: Displays details about the EC2 instances behind the ELB.
- **Health Check Tab**: Shows the health check configurations, including intervals and thresholds.
- **Listeners Tab**: Indicates the ports where the ELB listens for incoming requests.
- **Monitoring Tab**: Lists all key metrics for the ELB, such as:
  - Healthy and unhealthy instance counts.
  - Average latency.
  - HTTP response metrics (e.g., 2xx, 4xx, and 5xx status codes).

**2. Verifying ELB DNS and Instance Health**
- The **ELB DNS URL** is used by clients to connect to the load balancer. If backend instances are unavailable or unhealthy:
  - Requests to the DNS URL will timeout.
  - ELB will not route requests to backend EC2 instances.
- **Instance State**:
  - Instances are marked "Out of Service" if they fail the health checks.
  - Reasons include:
    - The instance is stopped.
    - The instance is running but not serving the expected application or responding on the specified ports.

**3. HTTP Response Metrics**
- **2xx Responses**: Indicate successful requests. The majority should fall into this category for a healthy application.
- **4xx Responses**: Represent client errors (e.g., bad request or unauthorized access).
- **5xx Responses**: Indicate server errors or backend exceptions.

**4. Health Check Configuration**
- Health checks are essential to ensure requests are routed only to healthy backend instances.
- Example Configuration:
  - **Interval**: 30 seconds.
  - **Unhealthy Threshold**: 2 consecutive failures.
- When instances fail health checks:
  - Hover over the error icon in the AWS console for detailed failure messages.
  - Possible reasons include incorrect configurations, unreachable instances, or missing resources (e.g., a web server not serving `index.html`).

**5. Monitoring and Alerting**
- Use **CloudWatch Dashboards**:
  - Visualize ELB metrics (e.g., latency, request count).
  - Identify trends or anomalies (e.g., spikes in 4xx/5xx errors or latency).
- Set **CloudWatch Alarms**:
  - Trigger alerts based on thresholds (e.g., unhealthy instances exceeding 0, latency above 1 second).
  - Automate scaling actions or notify administrators when thresholds are breached.

**6. Practical Observations**
- Start and test EC2 instances with valid configurations to pass health checks.
- Ensure backend instances are:
  - Listening on the specified ports (e.g., port 80 for HTTP).
  - Hosting the required application or files.
- Monitor how ELB reacts to instance states:
  - Healthy instances are added to the routing pool.
  - Unhealthy instances are excluded.

# AWS Billing and Cost Monitoring

**1. Why Monitor AWS Billing?**
- **Cost Control**: AWS operates on a "pay-as-you-go" model, charging for resources used. Mismanagement can lead to unnecessary expenses.
- **Avoid Human Errors**:
  - Forgetting to stop/terminate resources like EC2 instances or EBS volumes.
  - Over-provisioning resources beyond actual needs.
- **Insightful Usage Analysis**:
  - Helps optimize resource usage and reduce costs.
  - Provides visibility into spending across services, regions, or availability zones.

**2. Key Billing Features in AWS**
**AWS Cost and Usage Dashboard**
- Found in the **Billing and Cost Management Console**.
- Provides a breakdown of:
  - Resource usage.
  - Costs by service, region, and time period.

**Cost Explorer**
- Visualize and analyze spending patterns.
- Identify trends and optimize resource allocation.

**CloudWatch Billing Metrics**
- AWS automatically publishes billing metrics to CloudWatch once billing alerts are enabled:
  - **Estimated Charges**: Displays your estimated charges in real-time.
  - Charges can be filtered by:
    - Service type (e.g., EC2, S3).
    - Linked accounts (for consolidated billing).

**3. Setting Up Billing Alerts**
**Prerequisites**:
- Billing alerts can only be set up by the **root account** (not IAM users).
- Enable billing alerts in the **Billing Preferences** section.

**Steps to Create Billing Alerts**:
1. **Enable Billing Data in CloudWatch**:
   - Go to **Billing Preferences**.
   - Enable "Receive Billing Alerts."
2. **Create an Alarm in CloudWatch**:
   - Navigate to the CloudWatch console.
   - Select the billing metric you want to monitor (e.g., estimated charges).
   - Set a threshold (e.g., `$100`).
   - Define notification actions (e.g., send an email using Amazon SNS).

 **4. Billing Notifications**
AWS offers multiple methods to stay updated on costs:
1. **Email Alerts**:
   - Receive notifications when a billing alarm is triggered.
2. **Daily Reports in S3**:
   - Configure AWS to save daily billing reports in an S3 bucket.
3. **CloudWatch Alarms**:
   - Automate notifications or actions when billing thresholds are exceeded.

**5. Best Practices for Billing Monitoring**
1. **Tagging Resources**:
   - Use AWS tags to categorize resources by project, environment, or owner.
   - Helps allocate costs accurately.
2. **Review Unused Resources**:
   - Identify and delete unused resources like idle EC2 instances or unattached EBS volumes.
3. **Set Budget Thresholds**:
   - Use the AWS Budgets service to track actual vs. planned spending.
   - Automate alerts when spending approaches predefined limits.
4. **Understand Service-Specific Costs**:
   - Know the cost implications of services like EC2, S3, and RDS.
   - Example: Stopping EC2 instances doesn’t stop EBS charges unless volumes are deleted.

**6. Monitoring for Large Accounts**
- **Consolidated Billing**:
  - Manage multiple linked accounts under one master account.
  - Centralize billing and monitor all accounts simultaneously.
- **Resource-Specific Analysis**:
  - Breakdown costs per service or per region.
  - Optimize usage across availability zones.


## Step-by-Step Guide for Monitoring AWS Billing

**1. Accessing the Billing Dashboard**
- **Navigate to Billing Dashboard**:
  - In the **AWS Management Console**, click on your profile and select **My Billing Dashboard**.
- **Configure Billing Preferences**:
  - Go to the **Preferences** section to enable:
    1. **PDF Invoice by Email**: Receive a detailed invoice each month via email.
    2. **Billing Alerts via CloudWatch**: Set up CloudWatch metrics and alarms for monitoring your billing.
    3. **Daily Billing Reports in S3**: Automatically save daily billing reports in an S3 bucket for internal analysis.

**2. Enabling CloudWatch Billing Metrics**
- **CloudWatch Setup**:
  - In the AWS Management Console, search for **CloudWatch**.
  - Under **Metrics**, select **Billing**. Note that CloudWatch billing data is only available in the **US East (N. Virginia)** region.
- **Switch to US East (N. Virginia)**:
  - Follow the on-screen instructions to change your region to **US East (N. Virginia)** to view billing metrics.
- **Billing Metrics**:
  - Select the **Browse Metrics** button to view available metrics like:
    - **Estimated Charges** (overall billing for your account).
    - **Service-specific metrics** (e.g., EC2, S3, etc.).

**3. Creating Billing Alarms in CloudWatch**
- **Alarm Setup**:
  - In the **CloudWatch console**, navigate to **Alarms** and click **Create Alarm**.
  - **Select Metric**: Choose metrics such as **Total Estimated Charges** or specific service costs (e.g., EC2, S3).
  - **Set Alarm Threshold**: Configure the alarm to trigger when costs exceed a certain threshold (e.g., $100).
  - **Notification Setup**: Choose an **SNS Topic** to send notifications (email or other actions).

**4. Key Metrics to Track**
- **Total Estimated Charges**:
  - The most important metric for tracking your total billing. Set alarms based on your expected budget (e.g., 90% of the expected cost).
- **Service-Level Metrics**:
  - Track costs per service, such as EC2, EBS, or S3. This helps identify expensive resources and allows you to optimize cloud usage (e.g., switching to cheaper storage options or using spot instances).

**5. Example of Alarm Configuration**
- **Create a Budget Alert**:
  - Set up an alarm for **Total Estimated Charges** with a threshold (e.g., $100).
  - Select **SNS Topic** for email notifications when the threshold is crossed.
  - You can also trigger other actions based on the alarm, such as automatically reducing resources or scaling down services.

**6. Final Notes**
- **Real-Time Monitoring**: CloudWatch provides near-real-time data, enabling you to keep track of spending and avoid surprises at the end of the month.
- **Clean Up Unnecessary Resources**: Use the billing data to identify underutilized resources and optimize them to lower costs.

## Setting Up AWS Billing Reports in S3

**1. Create an S3 Bucket**
- Go to the **S3 Management Console** and click on **Create Bucket**.
- Select **US Standard** as the target region.
- Choose a **unique bucket name** (e.g., `monitoring-bill-demo`) and click **Create**.

**2. Set Up Permissions for the Bucket**
- After the bucket is created, go to the **Properties** tab of the bucket.
- In the **Permissions** section, click on **Add Bucket Policy**.
- Copy the **sample policy** provided in the billing dashboard and paste it into the **Bucket Policy editor**.
- Click **Save** to apply the policy.
  
This policy ensures AWS billing services can store the reports in your S3 bucket.

**3. Verify Bucket in Billing Preferences**
- Return to the **Billing Dashboard** in AWS.
- In the **Billing Preferences** section, choose to **receive billing reports** and enter the name of the S3 bucket you created.
- Click **Verify** to confirm the bucket's validity.

**4. Select Report Types**
- You can select different types of reports to be saved to your S3 bucket:
  - **Monthly Reports**: A summary of your charges.
  - **Detailed Billing Report**: A detailed breakdown of charges.
  - **Cost Allocation Report**: A report that allocates costs across different AWS accounts.
  - **Detailed Billing with Resources and Tags**: Includes detailed charges and cost allocation for resources and tags.
- Choose the report types you need and click **Save Preferences**.

**5. Automated Billing Report Storage**
- Once configured, AWS will automatically save your billing reports in the selected S3 bucket. These reports will be saved in a specific **file format** that you can monitor and use for analysis.

**Key Takeaways**
- **Billing Reports**: You can store different types of reports in an S3 bucket for more frequent, detailed, and customizable monitoring of your AWS costs.
- **Permissions**: Ensure proper permissions between AWS services (like billing and S3) by configuring a bucket policy.
- **Automation**: Once set up, these reports are automatically generated and stored for analysis.


# Introduction to Cloud Computing and AWS

In this module, you are introduced to **cloud computing** and **Amazon Web Services (AWS)**, providing an overview of their significance and benefits. Here's a breakdown of the key points:

**What is Cloud Computing?**
Cloud computing refers to delivering hosted services over the internet. It allows companies to access computing resources like virtual machines, storage, and applications as utilities, just like electricity. Instead of maintaining physical infrastructure, businesses can lease these resources on demand.

Key aspects of cloud computing include:
- **Virtualization**: The core technology enabling cloud computing to provide access to shared computing resources on-demand.
- **Cost Efficiency**: Cloud computing reduces the need for upfront investment in IT infrastructure, as resources are rented based on usage.
- **Scalability**: Cloud services offer the flexibility to scale resources up or down depending on demand, ensuring optimal resource use.

**Why Are Companies Switching to Cloud Computing (AWS)?**
Traditional IT infrastructures required deploying monolithic data centers with physical servers. This approach had several drawbacks:
- **High Capital Expenditure**: Significant upfront investment in hardware and infrastructure.
- **Low Utilization**: Inefficient use of resources, with idle servers.
- **Scalability Issues**: Difficult to scale operations quickly to meet demand.

With AWS and other cloud platforms, businesses can avoid these issues by accessing on-demand resources that are:
- **Faster to Deploy**: Cloud computing enables quicker deployment of applications and services.
- **Easily Scalable**: Companies can scale resources dynamically to handle increased demand or reduce them when not needed.
- **Environmentally Friendly**: Many cloud providers, like AWS, focus on using renewable energy sources to power their data centers and improve energy efficiency.

**Benefits of Cloud Computing**
Some key benefits that have driven the growth of cloud computing include:
- **Cost Efficiency**: Cloud services are typically cheaper due to better resource utilization and the ability to pay only for what is used.
- **High Performance**: Cloud platforms offer high-performance computing power, which helps businesses run complex applications efficiently.
- **Flexibility and Accessibility**: Cloud computing allows businesses to access their infrastructure from anywhere with an internet connection.

**Cloud Deployment Models**
There are several configurations for deploying cloud services:
- **Public Cloud**: Cloud resources are provided by public cloud providers (e.g., AWS, Microsoft Azure, Google Cloud). These resources are shared among customers, but each customer’s data is isolated.
- **Private Cloud**: A company owns and manages its own cloud infrastructure, providing more control over resources.
- **Hybrid Cloud**: A combination of public and private clouds, connected via a secure network. This setup allows companies to maintain some control while benefiting from the scalability of public cloud resources.


## Benefits of AWS Cloud

**1. Agile and Fast Deployment**
- **Quick Setup**: AWS enables rapid deployment of computing resources, eliminating the long waiting times associated with traditional IT infrastructure setups.
- **On-Demand Resources**: Resources can be provisioned within minutes, enabling businesses to respond quickly to changing demands.

**2. Scalability and Elasticity**
- **Scalable Resources**: AWS provides resources that can scale up or down depending on your business needs, allowing you to manage both growth and fluctuating demand effectively.
- **Elasticity**: Businesses can easily ramp up or scale down resources without having to make long-term investments in hardware or deal with over-provisioning.

**3. Cost-Effectiveness**
- **OpEx vs. CapEx**: With AWS, you move from a capital expenditure (CapEx) model, where you invest in hardware upfront, to an operational expenditure (OpEx) model, where you pay only for what you use.
- **Optimized Usage**: Instead of purchasing expensive equipment and underutilizing it, AWS enables businesses to consume exactly what they need when they need it, leading to cost savings.
- **Lower Total Cost of Ownership (TCO)**: With AWS, the total cost of running IT operations is lower because you pay only for the resources you use and benefit from ongoing cost optimizations made by AWS.

**4. Security and Compliance**
- **Comprehensive Security**: AWS provides a secure environment that meets stringent information security standards. It is trusted by global corporations and governments for handling sensitive data.
- **Security Certifications**: AWS is compliant with many security and governance standards and offers extensive auditing and control mechanisms.

**5. Flexibility and Hybrid Cloud**
- **Hybrid Cloud**: AWS allows businesses to extend their on-premises infrastructure into the cloud, providing more flexibility in how resources are deployed and managed.
- **Robust and Flexible Architecture**: AWS offers a variety of tools for building and managing IT architectures that can grow and adapt as needed.

**6. Encourages Innovation**
- **Fostering Creativity**: AWS offers an environment where developers can experiment, test new ideas, and innovate without the risk or cost of failure, allowing companies to push the boundaries of what’s possible with technology.
- **Pay-As-You-Go**: The flexible pay-per-use model encourages experimentation without the fear of significant upfront costs.

**7. High Availability and Global Reach**
- **Global Infrastructure**: AWS has a vast global network of data centers that ensures high availability and the ability to serve users from virtually anywhere in the world.

**8. Competitive Edge for Companies**
- **Large-Scale Needs**: AWS can handle the demands of large enterprises, providing the infrastructure to support massive computing needs.
- **Cost Optimization**: AWS's ability to adjust resources based on need helps businesses save costs, avoid over-provisioning, and optimize usage.

## Who is Using AWS and Why? 

AWS is a widely adopted cloud platform used by both large enterprises and popular startups for a variety of purposes, including infrastructure management, application services, mobile services, data analytics, and more. Here are some examples of how different companies are leveraging AWS:


**Popular Startups Using AWS**

- **Instagram**, **LinkedIn**, **Dropbox**, **Tumblr**, and **Airbnb**: These startups use AWS for scalable infrastructure, storage, and to run their operations efficiently without worrying about managing physical hardware.

**Large Enterprises Using AWS**

1. **Unilever**, **Lamborghini**, and **Tata Motors**: These companies use AWS for digital transformation, website management, and enhancing their business operations with cloud-based solutions.
   
2. **Lionsgate**, **Tokyo Stock Exchange**, and **Galera Chemicals**: These companies use AWS for development and testing, benefiting from AWS's application services like databases, queuing, and workflow management, which enable faster development and quicker time to market.

3. **Expedia**, **General Electric**, and **PBS**: These organizations deploy innovative solutions on AWS to meet their evolving business needs.

4. **Netflix**: Netflix runs its entire video streaming business on AWS infrastructure, showcasing AWS's ability to support large-scale operations for major global businesses.

5. **Samsung**, **Vodafone**: These companies use AWS for mobile services, enhancing their mobile offerings and supporting mobile websites and apps.

**Data Analytics and Business Intelligence**
- **Pfizer**, **Aon**, and other major global companies use AWS for building and deploying data analytics solutions, helping them make data-driven decisions to improve their operations and services.

**Mobile Application Services**
- **HTC** and **Vodafone**: AWS is widely used for developing, testing, and deploying mobile applications, as well as for managing mobile-focused websites and app stores.

**Hybrid Cloud Solutions**
Some businesses are adopting hybrid cloud environments, where AWS complements their on-premises infrastructure:

- **Nasdaq**, **SunPower**, and **Nokia**: These companies use AWS to build hybrid cloud setups, allowing them to handle workloads like data analytics, integration, and operational applications.
- **Samsung**: Integrates AWS with their on-premises systems to handle critical business functions such as financial transactions and to scale elastically.

**Cloud Migration and Optimization**
- **Unilever** and **Bristol-Myers**: These companies migrate existing applications to AWS, enabling faster product development and reduced costs.
- **NewsCorp**: Migrated its entire data center operations to AWS, reducing the number of physical data centers from 40 to just 6, optimizing costs and resource management.

**Business Operations on AWS**
- **Netflix** and **Suncorp**: These companies run their entire businesses on AWS, eliminating the need for traditional data centers and enabling them to focus on core operations.

 **Why Are Companies Adopting AWS?**
AWS provides a robust, scalable, and feature-rich cloud platform that allows companies to:
- **Scale on-demand** without the need for large upfront investments in physical infrastructure.
- **Foster innovation** by providing a flexible environment for development teams to work faster and more efficiently.
- **Reduce costs** through efficient resource usage and optimization tools.
- **Support hybrid and traditional infrastructures** where necessary, especially for businesses transitioning to the cloud or working with legacy systems.

## AWS Services Overview

AWS offers a wide range of services across various categories, enabling businesses to build, scale, and manage their infrastructure efficiently. Here's a breakdown of some key AWS service categories:

**Enterprise Applications**
These services cater to the needs of businesses for sharing and collaboration, data storage, and information analysis. Some examples include:
- **Virtual Desktops**: Enabling access to desktop environments from anywhere.
- **Sharing and Collaboration Services**: Allowing teams and businesses to store, analyze, and share information securely.

These applications can be built on top of various AWS platform services, which include:
- **Analytics**: AWS offers Hadoop, real-time streaming data, data warehouses, and data pipelines to help businesses analyze large data sets.
- **App Services**: This includes services like queuing, notifications, workflows, and other tools to support application development and management.

**Administration and Security Services**
AWS provides several services to manage security and administration, including:
- **Identity Management**: Ensuring that only authorized users can access resources.
- **Access Control**: Defining who can access specific services and resources.
- **Usage and Resource Tracking**: Monitoring usage and optimizing resources.


**Core AWS Services**
At the heart of AWS are the core services that power the infrastructure:
- **Compute**: Virtual servers and compute resources (e.g., EC2 instances).
- **Storage**: Scalable storage options (e.g., S3, EBS).
- **Content Delivery Networks**: Distributing content globally with services like CloudFront.
- **Databases**: Managed databases (e.g., RDS, DynamoDB).
- **Networking**: Services for managing and configuring networking (e.g., VPC, Route 53).

These core services are the building blocks for almost every AWS application or service.


**AWS Global Infrastructure**
AWS operates a global network of data centers to support its services. As of now, AWS Cloud has:
- **42 Availability Zones** in **16 regions** around the world.
- **63 Edge Locations** for content delivery.

AWS continues to expand rapidly, adding new regions and availability zones to meet the growing demand for cloud services worldwide.


**Certifications and Compliance**
AWS is built and managed according to stringent certifications and compliance programs:
- **Security and Data Protection**: AWS has robust security mechanisms in place to ensure data protection.
- **Governance and Compliance**: AWS supports shared responsibility for security, where AWS handles the infrastructure's security, while customers manage their own data and applications.
- **Audit-Ready Services**: AWS provides features that make it easy for customers to meet security and compliance standards.

These certifications and compliance programs help ensure that customers can trust AWS for maintaining a secure and compliant environment for their cloud operations.
