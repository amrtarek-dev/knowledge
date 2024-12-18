Cloud computing is the on-demand delivery of compute power, database storage, applications, and other IT resources.

## Deployment Models
- **Private Cloud**
	- Not exposed to the public
- **Public Cloud**
	- Cloud resources owned and operated by a third party cloud service provider.
- **Hybrid Cloud**
	- Keep some servers on premises and extend some capabilities to the cloud.

## Six advantages
- Trade capital expense (CAPEX) for operational expense (OPEX)
- Benefit from massive economies of scale
- Stop guessing capacity
- Increase speed and agility
- Stop spending money running and maintaining data centers.
- Go global in minutes

## Problems solved by Cloud
- **Flexibility**: change resource types when needed
- **Cost-effectiveness**: pay as you go, for what you use.
- **Scalability**: accommodate larger loads by making hardware stronger or adding additional nodes.
- **Elasticity**: ability to scale out and scale in when needed
- **High-availability** and fault-tolerance: build across data centers
- **Agility**: rapidly develop, test and launch software applications.

## Types of cloud computing
- Infrastructure as a Service (IaaS)
	- Providing building blocks for cloud IT
	- Providing networking, computers, data storage space.
	- Highest level of flexibility
	- Easy parallel with traditional on premises IT
		- Examples: Amazon EC2, GCP, Azure, Rackspace, Digital Ocean, Linode
- Platform as a Service (PaaS)
	- Removes the need for your organization to manage the underlying infrastructure
	- Focus on the deployment and management of your applications
		- Examples: AWS Elastic Beanstalk, Heroku, Google App Engine (GCP), Windows Azure
- Software as a Service (SaaS)
	- Completed product that is run and managed by the service provider.
		- Examples: AWS services, Google Apps, Dropbox, Zoom

# AWS Services

### Security and Identity
- **AWS IAM (Identity and Access Management):** Manages access to AWS services and resources securely.
- **Amazon GuardDuty:** Threat detection service that monitors AWS workloads.
- **AWS WAF (Web Application Firewall):** Protects applications from common web exploits.
- **AWS Shield:** A managed DDoS protection service.
### Compute
- **Amazon EC2 (Elastic Compute Cloud):** Provides virtual servers for running applications. Offers flexibility to choose instance types, operating systems, and configurations.
- **AWS Lambda:** A serverless computing service to run code without provisioning or managing servers. Ideal for event-driven applications.
- **Amazon ECS/EKS (Elastic Container Service/Kubernetes Service):** For running and managing containerized applications, supporting Docker and Kubernetes.

### Storage
- **Amazon S3 (Simple Storage Service):** Object storage for data backup, archival, and web content storage. Highly durable and scalable.
- **Amazon EBS (Elastic Block Store):** Block storage for EC2 instances. Useful for databases and applications requiring high-performance storage.
- **Amazon Glacier:** Low-cost, long-term archival storage for infrequently accessed data.
- **Amazon FSx:** File systems for Windows and Lustre, optimized for specialized workloads.

### Databases
- **Amazon RDS (Relational Database Service):** Managed relational database service supporting MySQL, PostgreSQL, SQL Server, MariaDB, and Oracle.
- **Amazon DynamoDB:** A fully managed NoSQL database designed for high-performance and scalable applications.
- **Amazon Aurora:** A high-performance managed database compatible with MySQL and PostgreSQL.
- **Amazon Redshift:** A data warehousing service for big data analytics.

### Networking
- **Amazon VPC (Virtual Private Cloud):** Enables the creation of isolated cloud environments.
- **AWS Route 53:** A scalable DNS web service for routing traffic to applications.
- **AWS CloudFront:** A content delivery network (CDN) to deliver data, videos, and APIs securely and with low latency.
- **AWS Direct Connect:** Establishes a dedicated network connection between on-premises and AWS.
- **AWS Outposts:** Extends AWS infrastructure to on-premises for hybrid cloud solutions.

### Machine Learning
- **Amazon SageMaker:** Provides tools to build, train, and deploy machine learning models at scale.
- **AWS Rekognition:** Service for image and video analysis using deep learning.
- **AWS Comprehend:** A natural language processing (NLP) service for sentiment analysis and entity recognition.
- **AWS Forecast:** Time-series forecasting service for predicting business outcomes.

### Analytics
- **Amazon Kinesis:** Real-time data processing service for streaming data like logs or IoT events.
- **Amazon EMR (Elastic MapReduce):** Big data processing framework using Hadoop, Spark, etc.
- **Amazon QuickSight:** A business intelligence (BI) service for visualizing data and creating dashboards.
- **AWS Glue:** A managed ETL (Extract, Transform, Load) service for data integration.

### Developer Tools
- **AWS CodeCommit:** A fully managed source control service for hosting Git repositories.
- **AWS CodeBuild:** A build service for compiling source code, running tests, and producing deployable software packages.
- **AWS CodeDeploy:** Automates software deployment to various compute services.
- **AWS CodePipeline:** A CI/CD service for automating the release pipelines.

### Management and Monitoring
- **AWS CloudWatch:** Monitoring service for AWS resources and custom applications.
- **AWS CloudTrail:** Logs and tracks API activity for governance and compliance.
- **AWS Config:** Tracks resource configurations to ensure compliance and troubleshooting.
- **AWS Trusted Advisor:** Provides recommendations for optimizing costs, performance, and security.

### Internet of Things (IoT)
- **AWS IoT Core:** Allows devices to securely connect and interact with AWS services.
- **AWS IoT Greengrass:** Extends AWS services to edge devices.
- **AWS IoT Analytics:** Analyzes IoT device data for actionable insights.

### Migration and Transfer
- **AWS Migration Hub:** Centralized tracking of application migrations to AWS.
- **AWS Snowball:** Physical data transfer device for large-scale migrations.
- **AWS DMS (Database Migration Service):** Migrates on-premises databases to AWS with minimal downtime.

### Business Applications
- **Amazon WorkSpaces:** Virtual desktops as a service.
- **Amazon Chime:** Online meeting and video conferencing service.
- **Amazon Connect:** Cloud-based customer contact center.

### Game Development
- **Amazon GameLift:** A managed service for deploying and scaling multiplayer game servers.
- **AWS Lumberyard:** A free game engine integrated with AWS and Twitch.