## 🛠️ Step-by-Step Implementation: Automating Receipt Processing Using AWS

This guide walks you through the full setup of a serverless receipt processing pipeline using AWS services.

---
## 1️⃣ Create the S3 Bucket (for uploading receipts) 

### ✅ Steps:
1. Go to the **S3 Console** → Click **Create Bucket**
2. Name your bucket (e.g., `storage-receipt-udaysai`)
3. Choose a region (e.g., `ap-south-1`)
4. Click **Create bucket**
5. Create Organizational folder inside bucket.
6. Name it **incoming** inside this you will upload files.
![image alt](https://github.com/udaysaithota/scanvaultproject/blob/2c23acecc61d927b0178b583838e8217ae81cda1/Screenshot%202025-07-17%20130816.png)


![image alt](https://github.com/udaysaithota/scanvaultproject/blob/beac5f3f30eac657a53265f8393ba64d690db170/Screenshot%202025-07-17%20110514.png)


---

## 2️⃣ Create a DynamoDB Table (to store extracted data)

### ✅ Steps:
1. Go to the **DynamoDB Console** → Click **Create Table**
2. Table name: `Receipts-table`
3. Partition key: `receipt_id` (String)
4. Sort-key: `date` (String)
5. Click **Create**


![image alt](https://github.com/udaysaithota/food-Waste-Reduction-Solution/blob/626257ca1c622ee0fa13fb60b9b905c910367a6d/Screenshot%202025-07-17%20111106.png)


![image alt](https://github.com/udaysaithota/food-Waste-Reduction-Solution/blob/626257ca1c622ee0fa13fb60b9b905c910367a6d/Screenshot%202025-07-17%20111143.png)


---

## 3️⃣ Set Up Amazon SES (to send emails)

### ✅ Steps:
1. Go to **Amazon SES Console**
2. Verify your sender email under **Verified Identities**
3. (Optional) Verify recipient email if your account is in sandbox mode
4. Note the region (e.g., `ap-south-1`) – you’ll need it in your Lambda

![image alt](https://github.com/udaysaithota/food-Waste-Reduction-Solution/blob/c761d7007c7338f48bb9f79fcd36c667e44568c1/Screenshot%202025-07-17%20112022.png)

1[image alt](https://github.com/udaysaithota/food-Waste-Reduction-Solution/blob/c761d7007c7338f48bb9f79fcd36c667e44568c1/Screenshot%202025-07-17%20112057.png)


---


## 4️⃣ Create IAM Role for Lambda Execution

### ✅ Steps:
1. Go to the **IAM Console** → Roles → Create Role
2. Choose **Lambda** as the use case
3. Attach the following policies:
  
```
   - `AmazonS3ReadOnlyAccess`
   - `AmazonTextractFullAccess`
   - `AmazonDynamoDBFullAccess`
   - `AmazonSESFullAccess`
   - `AWSLambdaBasicExecutionRole`
```
4. Name the role: `LambdaReceiptProcessingRole`

![image alt](https://github.com/udaysaithota/food-Waste-Reduction-Solution/blob/c761d7007c7338f48bb9f79fcd36c667e44568c1/Screenshot%202025-07-17%20113125.png)

![image alt](https://github.com/udaysaithota/food-Waste-Reduction-Solution/blob/c761d7007c7338f48bb9f79fcd36c667e44568c1/Screenshot%202025-07-17%20113506.png)

---
