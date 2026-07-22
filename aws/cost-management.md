# AWS : Cost Management

## Costs and Budgets

```bash
aws ce get-cost-and-usage   --time-period Start=YYYY-MM-DD,End=YYYY-MM-DD   --granularity MONTHLY   --metrics UnblendedCost

aws budgets describe-budgets --account-id ACCOUNT_ID
aws ce get-dimension-values   --time-period Start=YYYY-MM-DD,End=YYYY-MM-DD   --dimension SERVICE
```

## Optimization

```bash
aws compute-optimizer get-ec2-instance-recommendations
aws compute-optimizer get-auto-scaling-group-recommendations
aws ec2 describe-volumes --filters Name=status,Values=available
aws elasticache describe-reserved-cache-nodes-offerings
```

Tag resources consistently by owner, application, environment and cost center. Review idle capacity, storage classes, retention, data transfer, commitments and right-sizing against measured usage.
