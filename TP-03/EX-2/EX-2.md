## EX-02

### 2. Créer le bucket S3

```
users:~/environment $ aws --profile formation-infra-cloud s3api create-bucket --bucket epeyrataud --region eu-north-1 --create-bucket-configuration LocationConstraint=eu-north-1
{
    "Location": "http://epeyrataud.s3.amazonaws.com/"
}
```

### 3. Ajouter un tag au bucket

```
users:~/environment $ aws --profile formation-infra-cloud s3api put-bucket-tagging --bucket epeyrataud --tagging 'TagSet=[{Key=Owner,Value=epeyrataud}]'
users:~/environment $ aws --profile formation-infra-cloud s3api get-bucket-tagging --bucket epeyrataud
{
    "TagSet": [
        {
            "Key": "Owner",
            "Value": "epeyrataud"
        }
    ]
}
```

### 4. Supprimer le bucket

```
users:~/environment $ aws --profile formation-infra-cloud s3api delete-bucket --bucket epeyrataud --region eu-north-1
users:~/environment $ aws --profile formation-infra-cloud s3api list-buckets
{
    "Buckets": [
        {
            "Name": "iotamendi",
            "CreationDate": "2025-02-06T10:34:08+00:00"
        },
        {
            "Name": "kschaffner",
            "CreationDate": "2025-02-06T10:30:35+00:00"
        }
    ],
    "Owner": {
        "ID": "dce67c98d78035264db5532e5c4c05988a00c173a730653f5f4e10dc375e8252"
    },
    "Prefix": null
}
```
