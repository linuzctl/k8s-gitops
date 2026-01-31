# Policy

These policies are used to configure MinIO access for the Outline Wiki application.

- The user policy grants Outline permission to read/write objects in the `data` bucket while explicitly denying any admin or KMS access.
- The bucket policy allows public read access to objects under `data/public/`, which is required for publicly accessible assets such as images and shared files.

Together, these policies provide the minimum permissions required for Outline to function correctly with MinIO.


#### User Policy

```json
{
 "Version": "2012-10-17",
 "Statement": [
  {
   "Effect": "Deny",
   "Action": [
    "admin:*"
   ]
  },
  {
   "Effect": "Deny",
   "Action": [
    "kms:*"
   ]
  },
  {
   "Effect": "Allow",
   "Action": [
    "s3:*"
   ],
   "Resource": [
    "arn:aws:s3:::data/*"
   ]
  }
 ]
}
```

#### Bucket Policy

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Allow",
      "Principal": {
        "AWS": [
          "*"
        ]
      },
      "Action": [
        "s3:GetObject"
      ],
      "Resource": [
        "arn:aws:s3:::data/public/*"
      ]
    }
  ]
}
```
