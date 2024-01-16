# SST Notes App
This project is a full stack notes application built with SST. It includes a DynamoDB table, an S3 bucket, an API gateway, NodeJS lambda functions, and a static React front end.

## Stacks
The `sst.config.ts` configuration file contains information about which resources should be created, modified, or removed by commands such as `sst dev`. This configuration file imports modules from the `/stacks` folder, then appends each module to the app with `.stack()`. A stack is a concept from AWS CloudFormation that represents a collection of AWS resources that are managed as a unit. Each module in the `/stacks` folder uses SST constructs to configure and export a stack.

## Custom Domain
This project deploys the app to a cloudfront url. To deploy to a custom domain, follow these instructions:
https://sst.dev/chapters/purchase-a-domain-with-route-53.html
1. Purchase a domain
2. Add the customDomain field to the config in `stacks/ApiStack.ts`
3. Add the customDomain field to the config in `stacks/FrontendStack.ts`
4. Add the SiteUrl field to `stack.AddOutputs()` in `stacks/FrontendStack.ts`
5. Redeploy the app