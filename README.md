# Cloud-Engineering-Labs
My hands-on cloud engineering journey, learning AWS services using Floci, Docker and AWS CLI.

## Lab 1 - AWS S3 Cloud Storage Using floci

### Aim
My aim of this lab was to learn how cloud storage works by using AWS CLI and Floci to create an s3 bucket, upload files, list stored files and download them.

### Tools Used
- Windows 11
- Powershell
- Docker Desktop
- Floci (local AWS simulator)
- AWS Command line Interface (CLI)
- Amazon s3 (simulated cloud storage)

### Step 1 - Creating an S3 Bucket
I used PowerShell and AWS CLI to create my first s3 bucket using Floci.
 ``` powershell
aws--endpoint-url http://localhost:4566 s3 mb s3://my-first-cloud-lab
...

The bucket was created successfully.
I then used the following command to check it:
  ``` powershell
   aws--endpoint-url http://localhost:4566 s3 ls
```
### Step 2 - Uploading a file to s3
I created a text file using powershell and saved it in my Documents folders.
``powershell
"Hello from my first cloud lab!" | Out-file -Encoding utf8 cloud-test.txt

I then uploaded the file to my s3 bucket using the AWS CLI.
```powershell

aws --endpoint-url http://localhost:4566 s3 cp cloud-test.txt s3://my-first-cloud- lab/
```
The upload was successful!

The checked the contents using:
```powershell
aws --endpoint-url http://localhost:4566 s3 ls  s3:// my-frist-cloud-lab/
```
### step 3 - Downloading File from S3
I used AWS CLI to download my file from s3 bucket back onto my laptop.
```powershell
aws --endpoint-url http://localhost:4566 s3 cp s3://my-first-cloud-lab/cloud-test.txt downloaded-test.txt

I then checked the downloaded file using powershell.
```powershell
get-content downloaded-test.txt
```
The file contained the original message:
Hello from my first cloud lab!




