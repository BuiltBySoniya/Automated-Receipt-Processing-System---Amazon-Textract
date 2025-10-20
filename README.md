# 🚀 Automated Receipt Processing System – Amazon Textract

Serverless Receipt & Invoice Data Extraction Pipeline

## Short Description

Developed a serverless pipeline that automates receipt and invoice processing using Amazon Textract, AWS Lambda, and Amazon S3. Upon file upload, the system extracts key fields (vendor, amount, date), loads structured data into a datastore, and triggers downstream workflows for archival and analytics.

## 🛠️ AWS Services Used:

Amazon Textract,
AWS Lambda,
Amazon S3,
Amazon DynamoDB (or alternative datastore),
AWS IAM,

## 🧰 Technical Tools:

Python (or Node.js) Lambda functions,
Boto3 (or AWS SDK) for AWS integrations,
AWS CLI / AWS SAM for deployment,
CSV/JSON data handling libraries,

## 🧠 Skills Demonstrated:

Serverless document-processing workflow,
Machine-learning based text extraction,
Automated ETL of unstructured data into structured formats,
Cloud-native storage, indexing and archival mechanisms,

## 📋 Steps Performed

### Create S3 Buckets & Configure Upload Trigger:

Created an input S3 bucket for receipt/image uploads and an output bucket for processed results.
Configured an S3 event notification to trigger a Lambda function upon new file upload.

### IAM Role & Permissions Setup:

Defined an IAM role for Lambda with permissions to read from S3, invoke Textract, write to DynamoDB, and log to CloudWatch.
Ensured least-privilege access for document processing.

### Develop Lambda Function for Extraction & Processing:

Built a Lambda handler that receives S3 upload events, invokes Textract’s expense/receipt APIs, extracts summary fields (vendor, date, total) and line-items, and writes cleaned data to the datastore (e.g., DynamoDB).
Also moved processed files to archival/pending folders as part of post-processing.

### Load & Store Processed Data:

Saved extracted metadata into a DynamoDB table with a defined schema.
Stored raw Textract output (JSON) and original receipt files under versioned folders in S3 for auditability.

### Monitor, Archive & Validate Workflow:

Set up CloudWatch logs and metrics to monitor Lambda executions, Textract latency and error rates.
Configured S3 lifecycle policies to transition archival data to lower-cost tiers after defined retention periods.
Tested with sample receipt images, verified correct extraction of values, and validated end-to-end workflow.

## ✅ Final Result:

Automated Receipt / Invoice Processing Pipeline

## 💼 Business Implication:

This solution streamlines and automates receipt/invoice data entry and management, reducing manual labour, eliminating data-entry errors and accelerating finance operations. By leveraging serverless components and Amazon Textract’s ML-based extraction, organizations convert unstructured documents into structured business-ready data with zero infrastructure burden and high scalability.
