# ck-index
Index of CloudKeep's GitHub Repos.

We list here the GitHub repositories under CloudKeep organization under 
appropriate categories. We also provide a short description and 
what automation (if any) is currently in effect for each repository.

Note these are mostly private.

## Documentation
### [ck-index](https://github.com/cloudkeep-io/ck-index)
This document.
### [ck-wiki](https://github.com/cloudkeep-io/ck-wiki)
Wiki pages - primary internal documentation.
### [ck-api-blueprint](https://github.com/cloudkeep-io/ck-api-blueprint)
Probably obsolete. Early attempt to document API.

## Website
### [ck-www](https://github.com/cloudkeep-io/ck-www)
Hugo source for our website.
| branch | tag | pipeline action |
| --- | --- | --- |
| `master` | - | deploys to [cloudkeep.io](https://cloudkeep.io) |
| `stage1` | - | deploys to [stage1](http://ck-www-stage1-us-east-1.s3-website-us-east-1.amazonaws.com/) |
| `stage2` | - | deploys to [stage2](http://ck-www-stage2-us-east-1.s3-website-us-east-1.amazonaws.com/) |

## Console (our UI)
### [ck-console](https://github.com/cloudkeep-io/ck-console)
Angular source for our UI.
| branch | tag | pipeline action |
| --- | --- | --- |
| `master` | - | deploys to [console](https://console.cloudkeep.io) |
| `eddie/*` | - | deploys to [console2](https://console2.cloudkeep.io) |
| `sanket/*` | - | deploys to [console2](https://console2.cloudkeep.io) |
| all other | - | deploys to [console1](https://console1.cloudkeep.io) |

## Services
CloudKeep Backend APIs are provided by these services. They are all deployed as
Docker Containers into EKS.
### [ck-user](https://github.com/cloudkeep-io/ck-user)
CloudKeep API for user and organization management.
| branch | tag | pipeline action |
| --- | --- | --- |
| * | - | builds/tests/pushes image to CloudKeep ECR with ver==`git describe --tags --always` |
| - | * | builds/tests/pushes image to CloudKeep ECR with ver==tag, then submits a PR to cki4-prod-use1/master to use the new version in PROD|

### [ck-aws](https://github.com/cloudkeep-io/ck-aws)
CloudKeep API for AWS related resource management
| branch | tag | pipeline action |
| --- | --- | --- |
| * | - | builds/tests image |
| - | `x.y.z[-(apha/beta/rc).N]` | builds/tests/pushes image to CloudKeep ECR with ver==tag |

## Dockerfiles
These repos are just building "custom" Docker container images from external 
sources.
### [ck-docker](https://github.com/cloudkeep-io/ck-docker)
This image is used as base to CloudKeep Services' Container images.
| branch | tag | pipeline action |
| --- | --- | --- |
| * | - | builds/tests image |
| - | `x.y.z[-(apha/beta/rc).N]` | builds/tests/pushes image to CloudKeep ECR with ver==tag |
### [ck-express-gateway](https://github.com/cloudkeep-io/ck-express-gateway)
### [ck-postgresql](https://github.com/cloudkeep-io/ck-postgresql)

## Helm Charts
### [ck-user-chart](https://github.com/cloudkeep-io/ck-user-chart)
| branch | tag | pipeline action |
| --- | --- | --- |
| * | - | builds/pushes helm chart package to CloudKeep S3 chart repo with ver==`git describe --tags --always` |
| - | * | builds/pushes helm chart package to CloudKeep S3 chart repo with ver==tag, then submits a PR to cki4-prod-use1/master to use the new version in PROD |
### [ck-aws-chart](https://github.com/cloudkeep-io/ck-aws-chart)
| branch | tag | pipeline action |
| --- | --- | --- |
| * | - | builds/pushes helm chart package to CloudKeep S3 chart repo with ver==`git describe --tags --always` |
| - | * | builds/pushes helm chart package to CloudKeep S3 chart repo with ver==tag, then submits a PR to cki4-prod-use1/master to use the new version in PROD |
### [ck-express-gateway-chart](https://github.com/cloudkeep-io/ck-express-gateway-chart)
| branch | tag | pipeline action |
| --- | --- | --- |
| * | - | builds/pushes helm chart package to CloudKeep S3 chart repo with ver==`git describe --tags --always` |
| - | * | builds/pushes helm chart package to CloudKeep S3 chart repo with ver==tag, then submits a PR to cki4-prod-use1/master to use the new version in PROD |

## Lambda Functions
### [ck-lambda-registration](https://github.com/cloudkeep-io/ck-lambda-registration)
| branch | tag | pipeline action |
| --- | --- | --- |
| * | - | builds/pushes lambda function package to CloudKeep S3 repo with ver==`git describe --tags --always` |
| - | * | builds/pushes lambda function package to CloudKeep S3 repo with ver==tag, then submits a PR to cki2-prod-use1/master to use the new version in PROD |

## Terraform
### [ck-infra0](https://github.com/cloudkeep-io/ck-infra0)
Should rename to `cki0` - multi-stage (PROD, STAGE, DEV, etc), multi-region
| branch | tag | pipeline action |
| --- | --- | --- |
| `master` | - | runs terraform against the checked in code |

### [ck-infra1-prod](https://github.com/cloudkeep-io/ck-infra1-prod)
Should rename to `cki1-prod` - PROD, multi-region
| branch | tag | pipeline action |
| --- | --- | --- |
| `master` | - | runs terraform against the checked in code |

### [ck-infra2-devlocal](https://github.com/cloudkeep-io/ck-infra2-devlocal)
### [ck-infra2-prod-use1](https://github.com/cloudkeep-io/ck-infra2-prod-use1)
Should rename to `cki2-prod-use1` - PROD, us-east-1
| branch | tag | pipeline action |
| --- | --- | --- |
| `master` | - | runs terraform against the checked in code |
### [cki3-dev01-use1](https://github.com/cloudkeep-io/cki3-dev01-use1)
### [ck-infra3-prod-use1](https://github.com/cloudkeep-io/ck-infra3-prod-use1)
Should rename to `cki3-prod-use1` - PROD, us-east-1
| branch | tag | pipeline action |
| --- | --- | --- |
| `master` | - | runs terraform against the checked in code |
### [ck-infra4-devlocal](https://github.com/cloudkeep-io/ck-infra4-devlocal)
### [ck-infra4-prod-use1](https://github.com/cloudkeep-io/ck-infra4-prod-use1)
Should rename to `cki4-prod-use1` - PROD, us-east-1
| branch | tag | pipeline action |
| --- | --- | --- |
| `master` | - | runs terraform against the checked in code |

## Terraform Modules
Terraform modules to keep the terraform code in ckiN repos DRY.
### [ck-tfmod-cloudfront](https://github.com/cloudkeep-io/ck-tfmod-cloudfront)
### [ck-tfmod-s3-pair](https://github.com/cloudkeep-io/ck-tfmod-s3-pair)
### [ck-tfmod-s3-pair-website](https://github.com/cloudkeep-io/ck-tfmod-s3-pair-website)
### [ck-tfmod-tfbackend-s3](https://github.com/cloudkeep-io/ck-tfmod-tfbackend-s3)

## Studies, Proof of Concepts
### [ck-aws-poc](https://github.com/cloudkeep-io/ck-aws-poc)
### [ck-aws-poc-cf](https://github.com/cloudkeep-io/ck-aws-poc-cf)
### [ck-signup](https://github.com/cloudkeep-io/ck-signup)
### [snapshot-study](https://github.com/cloudkeep-io/snapshot-study)

## Obsolete, on-hold
### [ck-ui](https://github.com/cloudkeep-io/ck-ui)
### [ck-discourse](https://github.com/cloudkeep-io/ck-discourse)
### [ck-discourse-chart](https://github.com/cloudkeep-io/ck-discourse-chart)
### [ck-helm-charts](https://github.com/cloudkeep-io/ck-helm-charts)
### [ck-stack-dev01](https://github.com/cloudkeep-io/ck-stack-dev01)
### [hugo-fresh](https://github.com/cloudkeep-io/hugo-fresh)
