🚀 Terraform Setup Guide

Follow these steps to install and configure Terraform on your system.


1. 📦 Install Terraform
Linux / MacOS

```
# Add HashiCorp GPG key
curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg

# Add the official HashiCorp repo
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] \
https://apt.releases.hashicorp.com $(lsb_release -cs) main" \
| sudo tee /etc/apt/sources.list.d/hashicorp.list

# Update and install
sudo apt update && sudo apt install terraform -y
```

For MacOS (Homebrew):

```
brew tap hashicorp/tap
brew install hashicorp/tap/terraform
```

For Windows:

1.	Download the latest Terraform ZIP from: Terraform Releases
2.	Extract the ZIP and move terraform.exe to a folder (e.g., C:\terraform).
3.	Add that folder to your System PATH:
	•	Start → “Edit system environment variables”
	•	Edit Path → Add C:\terraform

✅ Verify Installation

Run:
```
terraform -version
```
You should see output like:
```
Terraform v1.x.x
on linux_amd64
```

⚙️ Configure AWS Credentials

Terraform needs AWS credentials to manage resources.

Option A: Use AWS CLI

```
aws configure
```

Enter your:
	•	AWS Access Key ID
	•	AWS Secret Access Key
	•	Default region (e.g., ap-southeast-1)

Option B: Use Environment Variables

```
export AWS_ACCESS_KEY_ID="your_access_key"
export AWS_SECRET_ACCESS_KEY="your_secret_key"
export AWS_DEFAULT_REGION="ap-southeast-1"
```

▶️ Run Terraform

Inside your Terraform project folder:

```
# Initialize Terraform providers & modules
terraform init

# See what changes will be applied
terraform plan

# Apply changes (create resources)
terraform apply -auto-approve

# Destroy resources when finished
terraform destroy -auto-approve

```

📖 Useful Commands

```
terraform init
terraform validate
terraform plan
terraform apply
terraform destroy
```


