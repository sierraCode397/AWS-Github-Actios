# AWS Practical Task

## Step 1: Set Up a Dedicated User for S3 Access

### 1.1 Create a New IAM User
**Objective:**  
Generate a new IAM user dedicated to managing access to your S3 bucket.

**Instructions:**
- Log in to your AWS Management Console.
- Navigate to the IAM service.
- Create a new user with a unique name.
- Ensure that the access type is set to provide programmatic access.

---

### 1.2 Attach the Required Policy
**Objective:**  
Grant the user permission to manage and interact fully with your S3 bucket.

**Instructions:**
- During the user creation process, select to attach policies directly.
- From the policy list, choose the policy that grants full access to S3 (commonly named similar to `AmazonS3FullAccess`).
- Confirm and complete the creation process.

---

### 1.3 Secure Your Credentials
**Objective:**  
Retrieve and safely store the access credentials for later use.

**Instructions:**
- After the user is created, download the access credentials (Access Key ID and Secret Access Key).

---

## Step 2: Integrate Credentials with Your GitHub Repository

### 2.1 Add Your Credentials as Repository Secrets
**Objective:**  
Securely incorporate your AWS credentials into your GitHub project so that your deployment workflow can access them.

**Instructions:**
- Open your GitHub repository and go to the **Settings** tab.
- Navigate to **Secrets** and select **Actions**.
- Click on **New repository secret** and add a new secret for your Access Key ID (`AWS_ACCESS_KEY_ID`).
- Repeat the process to add a secret for your Secret Access Key (`AWS_SECRET_ACCESS_KEY`).

---

### 2.2 Security Best Practices
**Objective:**  
Ensure that sensitive credentials are never exposed.

**Recommendations:**
- Always use GitHub Secrets to manage sensitive data.
- Make sure your CI/CD pipeline references these secrets, so your keys remain hidden and secure throughout the deployment process.
- Regularly review and rotate credentials to maintain security.

---

## Step 3: Create a Workflow

Next, we create a workflow for the deployment.

**Instructions:**

- Navigate to your repository containing the app you wish to deploy and select the **Actions** tab.
- Click on **Set up workflow yourself**.
- Insert the following script into your workspace:

---

## Step 4: Run your Pipeline

**Instructions:**
- Navigate to the **Actions** tab in your repository to see your pipeline in action.

**Troubleshooting:**
- **User Permissions:** Ensure your IAM user's policy is correctly set.
- **Bucket Specification:** Confirm that you have the correct bucket name.
- **Secrets Reference:** Verify that your workflow references the exact names of your secrets.
