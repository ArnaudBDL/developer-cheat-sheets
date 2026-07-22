# AWS : CloudWatch

## Metrics and Alarms

```bash
aws cloudwatch list-metrics --namespace AWS/EC2
aws cloudwatch get-metric-data --metric-data-queries file://queries.json   --start-time START_TIMESTAMP --end-time END_TIMESTAMP

aws cloudwatch put-metric-alarm   --alarm-name high-cpu   --namespace AWS/EC2   --metric-name CPUUtilization   --dimensions Name=InstanceId,Value=INSTANCE_ID   --statistic Average --period 300   --evaluation-periods 2 --threshold 80   --comparison-operator GreaterThanThreshold
```

## Logs

```bash
aws logs describe-log-groups --output table
aws logs tail LOG_GROUP_NAME --follow
aws logs filter-log-events --log-group-name LOG_GROUP_NAME   --filter-pattern 'ERROR'
```
