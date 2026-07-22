# GitLab CI : Environments

## Static Environment

```yaml
deploy-production:
  stage: deploy
  script:
    - ./deploy.sh production
  environment:
    name: production
    url: https://example.com
  rules:
    - if: $CI_COMMIT_BRANCH == $CI_DEFAULT_BRANCH
      when: manual
```

## Dynamic Review Environment

```yaml
deploy-review:
  stage: deploy
  script:
    - ./deploy-review.sh "$CI_COMMIT_REF_SLUG"
  environment:
    name: review/$CI_COMMIT_REF_SLUG
    url: https://$CI_COMMIT_REF_SLUG.review.example.com
    on_stop: stop-review
  rules:
    - if: $CI_PIPELINE_SOURCE == "merge_request_event"
```

## Stop Environment

```yaml
stop-review:
  stage: deploy
  script:
    - ./destroy-review.sh "$CI_COMMIT_REF_SLUG"
  environment:
    name: review/$CI_COMMIT_REF_SLUG
    action: stop
  when: manual
```

## Serialized Deployment

```yaml
deploy-production:
  resource_group: production
  environment: production
  script: ./deploy.sh
```
