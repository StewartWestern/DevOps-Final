# Linux Infrastructure
These commands will show if the instance is running correctly
```
uname -a
df -h
```

## S3 Storage
If we want others to see the contents of our bucket we need to *allow public access* in the settings

The following *also* needs to be added to permissions
```
{
	"Version": "2012-10-17",
	"Statement": [
		{
			"Effect": "Allow",
			"Principal": "*",
			"Action": [
				"s3:GetObject"
			],
			"Resource": "arn:aws:s3:::YOUR_BUCKET_NAME/*"
		}
	]
}
```