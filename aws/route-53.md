# AWS : Route 53

## Hosted Zones

```bash
aws route53 list-hosted-zones --output table
aws route53 get-hosted-zone --id HOSTED_ZONE_ID
aws route53 list-resource-record-sets --hosted-zone-id HOSTED_ZONE_ID
```

## Change Records

```bash
aws route53 change-resource-record-sets   --hosted-zone-id HOSTED_ZONE_ID   --change-batch file://record-change.json

aws route53 get-change --id CHANGE_ID
```

```json
{
  "Changes": [
    {
      "Action": "UPSERT",
      "ResourceRecordSet": {
        "Name": "app.example.com",
        "Type": "A",
        "TTL": 300,
        "ResourceRecords": [{ "Value": "192.0.2.10" }]
      }
    }
  ]
}
```
