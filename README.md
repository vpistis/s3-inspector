# S3 Inspector
Tool to check AWS S3 bucket permissions.
**Compatible** with Linux/MacOS, python2 and python3
## What it does
 - Checks all your buckets for public access
 - For every bucket gives you the report with:
   - Indicator if your bucket is public or not
   - Permissions for your bucket if it is public
   - List of URLs to access your bucket (non-public buckets will return Access Denied) if it is public

## Prerequisites
### Create a new IAM User
 - **Create IAM user with AmazonS3ReadOnly policy attached**
   - Go to IAM (https://console.aws.amazon.com/iam/home)
   - Click "Users" on the left hand side menu
   - Click "Add user"
   - Fill in user name and check **Programmatic access**
   - Click "Next: Permissions"
   - Click "Attach existing policies directly"
   - Check **AmazonS3ReadOnly** policy
   - Click "Next: Review"
   - Click "Create user"
   - **Copy the credentials**
     - **Access key ID**
     - **Secret access key**
 - **Create ~/.aws/credentials file or paste the credentials in when you run the script**
   - Put the credentials you copied in the previous step here in this format:
```
[default]
aws_access_key_id = <your access key ID goes here>
aws_secret_access_key = <your secret_access_key goes here>
```
### Use existing configured IAM User
 - **use your existing credentials or profile** if you have a file `~/.aws/credentials` like this:
```
[default]
aws_access_key_id = <your access key ID goes here>
aws_secret_access_key = <your secret_access_key goes here>
[myPorfile_name]
aws_access_key_id = <your access key ID goes here>
aws_secret_access_key = <your secret_access_key goes here>
```
 - and pass the profile name or leave blank for `default` when requested:
```
python s3inspector.py
Enter your AWS profile name [default]:
```

## Usage
`python s3inspector.py`

## Report example
![Sample report screenshot](https://github.com/kromtech/s3-inspector/blob/screenshot/samplerun.png "Sample report screenshot")
