# Pushing changes to AWS

After committing code to master:
1. Update S3 bucket
`aws s3 sync . s3://greg-bee`

2. Invalidate CloudFront distribution cache
`aws cloudfront create-invalidation --distribution-id E3I4O017FOVHVQ --paths "/*"`
