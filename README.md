<img width="1535" height="959" alt="Screenshot 2026-09-04 214337" src="https://github.com/user-attachments/assets/d3025051-61ec-418b-8044-fc914444acd7" /># Experiment No. 2 — Cloud Storage Creation (S3) and Launching an EC2 Instance in AWS

## Aim
To create an Amazon S3 bucket for cloud storage and launch a virtual machine using Amazon EC2 in the AWS Management Console.

## Objectives
After completing this experiment, students will be able to:
- Understand AWS Cloud Storage (Amazon S3)
- Create and manage S3 buckets
- Upload and organize files in cloud storage
- Launch an EC2 virtual server
- Connect to an EC2 instance
- Understand cloud computing infrastructure services

## Software Requirements
- Laptop/Desktop
- Internet connection
- AWS Academy Learner Account / AWS Free Tier Account
- Modern web browser (Chrome/Edge)

## Theory

### Amazon S3 (Simple Storage Service)
Amazon S3 is an object storage service provided by AWS that stores unlimited amounts of data with high durability and availability.

**Features:**
- Unlimited storage
- 99.999999999% (11 nines) durability
- High availability
- Secure storage
- Versioning
- Lifecycle management
- Encryption

---

## Part A — Creating an Amazon S3 Bucket

1. Open the AWS console: [https://aws.amazon.com/console/](https://aws.amazon.com/console/)  

<img width="1535" height="959" alt="Screenshot 2026-09-04 214337" src="https://github.com/user-attachments/assets/b60b027f-a2fc-4c78-9c61-8586057ff47a" />

2. Log in:
   - Click **Sign in using root user email**
   - Enter the registered email address
   - Enter the AWS password
   - Complete the verification process

<img width="1535" height="959" alt="Screenshot 2026-09-04 214406" src="https://github.com/user-attachments/assets/f2438a51-b14e-4005-bdf1-7072c3ea3049" />

3. Type **S3** in the search box.

<img width="1535" height="959" alt="Screenshot 2026-09-04 214439" src="https://github.com/user-attachments/assets/d6e1b907-0d81-496e-8253-04c2b5c7b2dc" />

5. Click **Amazon S3**.
6. Click **Create bucket**.
7. Enter the following details:

   | Parameter    | Value                      |
   |--------------|-----------------------------|
   | Bucket type  | General purpose            |
   | Bucket name  | `student-cloud-storage-001` |
   | AWS Region   | Asia Pacific (Mumbai)      |

<img width="1535" height="959" alt="Screenshot 2026-09-04 214730" src="https://github.com/user-attachments/assets/59b8ad05-d317-40a3-8d3d-5f511eafd365" />

9. Leave the remaining settings unchanged.
11. Click **Create bucket**.

<img width="1535" height="959" alt="Screenshot 2026-09-04 214749" src="https://github.com/user-attachments/assets/0e3b9b44-42ad-4fec-b7ae-5d18222ad36c" />

12. Click **Upload**.
13. Upload the following files:
    - PDF file
    - Word document
    - Image file

<img width="1535" height="959" alt="Screenshot 2026-09-04 215034" src="https://github.com/user-attachments/assets/0757141c-a25f-419d-804c-e4002999f9f7" />
    
**Example bucket structure:**
```
student-cloud-storage-001
│
├── Cloud.pdf
├── Assignment.docx
├── Image.jpg
└── Notes.pdf
```
<img width="1535" height="959" alt="Screenshot 2026-09-04 215105" src="https://github.com/user-attachments/assets/c40f6245-a6b1-4b1f-98cc-4cad46d174e4" />

---

## Part B — Launching an Amazon EC2 Instance

1. Type **EC2** in the AWS search bar.

<img width="1535" height="954" alt="Screenshot 2026-09-04 215126" src="https://github.com/user-attachments/assets/4e82df17-c560-4df4-93a2-786fae5ed14d" />

2. Open the **EC2 Dashboard**.

<img width="1535" height="958" alt="Screenshot 2026-09-04 215226" src="https://github.com/user-attachments/assets/a6130274-0618-4769-b3a3-6e107a29be90" />

3. Click **Launch instance**.
4. Enter the instance name: `CloudLabVM`
5. Select the operating system:
   - Amazon Linux 2023
   - Ubuntu Server
6. Select the instance type: `t3.micro`
7. Create a key pair:

   | Parameter      | Value        |
   |----------------|--------------|
   | Key pair name  | `CloudLabKey`|
   | Key pair type  | RSA          |
   | File format    | `.pem`       |

8. Download the `CloudLabKey.pem` file.
9. Configure network settings:
   - ✅ Allow SSH traffic (Port 22)
   - ✅ Allow HTTP traffic (Port 80)
   - ✅ Allow HTTPS traffic (Port 443)
10. Set the storage size: `8 GiB`
11. Click **Launch instance**.

<img width="1535" height="959" alt="Screenshot 2026-09-04 215324" src="https://github.com/user-attachments/assets/94bdf4c9-cb59-4c1f-b694-93f5a6a9f7ae" />

12. Wait until the status changes:

<img width="1535" height="959" alt="Screenshot 2026-09-04 215425" src="https://github.com/user-attachments/assets/20b1b1c9-6355-4f98-88b9-a81f56c18c48" />


    ```
    Pending → Running
    ```

### Connecting to the EC2 Instance
1. Open **EC2**.
2. Select the instance.

<img width="1535" height="959" alt="Screenshot 2026-09-04 215454" src="https://github.com/user-attachments/assets/fa22ad54-3d9f-4793-96bc-d23041885104" />

3. Click **Connect**.

<img width="1535" height="959" alt="Screenshot 2026-09-04 215638" src="https://github.com/user-attachments/assets/e919cf6c-c75a-4735-848d-ccac0a5f669d" />

4. Select **EC2 Instance Connect**.
5. Click **Connect**.

6. Execute the following command:

   ```bash
   echo "Hello AWS"
   ```

   **Output:**
   ```
   Hello AWS
   ```

<img width="1535" height="959" alt="Screenshot 2026-09-04 215722" src="https://github.com/user-attachments/assets/e29ec1f8-265d-4b26-ab0a-1ad75927dc84" />

<img width="1535" height="959" alt="Screenshot 2026-09-04 215801" src="https://github.com/user-attachments/assets/3e4a40c0-7243-4dc5-b123-176bf231d34f" />


### Stopping the EC2 Instance
1. Open **EC2**.
2. Select **Instances**.
3. Select the running instance.
4. Click **Instance state**.

<img width="1535" height="951" alt="Screenshot 2026-09-04 215931" src="https://github.com/user-attachments/assets/32058426-f00b-4947-a57d-7fd72f3d8151" />

5. Click **Stop instance**.

   **Status flow:**
   ```
   Running → Stopping → Stopped
   ```
<img width="1535" height="959" alt="Screenshot 2026-09-04 220001" src="https://github.com/user-attachments/assets/fdd08d4a-982e-40b8-aef9-6e834b4943f0" />


### Logging Out of AWS
1. Click the profile icon in the upper-right corner.
2. Select **Sign out**.

---

## Result
The Amazon S3 bucket was created successfully, files were uploaded, an EC2 instance was launched, and the virtual machine was connected successfully.
