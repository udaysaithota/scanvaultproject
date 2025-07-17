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

