# 🪣 AWS S3 Bucket Creation
This project demonstrates how to programmatically create an **Amazon S3 bucket** using the **AWS SDK for Python (Boto3)**. It's designed for quick setup and deployment of a bucket to your specified AWS region.

---
# Install dependencies
```bash
pip install boto3
```
# Configure AWS credentials 
```bash
aws configure
```

--------
# Write the code in sdk.py
```bash
  import boto3
from botocore.exceptions import ClientError

# Define your region and bucket name
region = 'us-east-1'
bucket_name = 'sakshii-bucket-2003'

# Create the S3 client
s3 = boto3.client('s3', region_name=region)

try:
    # Create the bucket
    if region == 'us-east-1':
        response = s3.create_bucket(Bucket=bucket_name)
    else:
        response = s3.create_bucket(
            Bucket=bucket_name,
            CreateBucketConfiguration={'LocationConstraint': region}
        )

    print(f"✅ Bucket '{bucket_name}' created successfully in {region}!")

except ClientError as e:
    print(f"❌ Error creating bucket: {e}")
```

# To run 
```bash
python sdk.py
```


