# AWS CI/CD Pipeline

End-to-end CI/CD pipeline built on AWS, from a remote cloud dev environment through automated build, secure package management, and deployment. Built incrementally over 6 days, with real debugging notes along the way rather than a clean happy-path walkthrough.

## Tech Stack

**Compute & Environment:** Amazon EC2, VS Code Remote-SSH
**Source & Build:** GitHub, AWS CodeConnections, AWS CodeBuild, Apache Maven
**Packages:** AWS CodeArtifact
**Storage & Deploy:** Amazon S3, AWS CodeDeploy, AWS CodePipeline
**Security:** AWS IAM (least-privilege roles, temporary credentials over hardcoded keys)
**Monitoring:** Amazon CloudWatch

## Progress

| Day | Topic | Status | Doc |
|-----|-------|--------|-----|
| 1 | Set Up a Web App Using AWS and VS Code | Done | [docs/day1-set-up-a-web-app-using-aws-and-vs-code.md](docs/day1-set-up-a-web-app-using-aws-and-vs-code.md) |
| 2 | Connect Remote Dev Environment with GitHub | Done | [docs/day2-connect-a-github-repo-with-aws.md](docs/day2-connect-a-github-repo-with-aws.md) |
| 3 | Secure Packages with CodeArtifact | Done | [docs/day3-secure-packages-with-codeartifact.md](docs/day3-secure-packages-with-codeartifact.md) |
| 4 | Continuous Integration with CodeBuild | Done | [docs/day4-continuous-integration-with-codebuild.md](docs/day4-continuous-integration-with-codebuild.md) |
| 5 | Deploy a Web App with CodeDeploy | Done | [docs/day5-deploy-a-web-app-with-codedeploy.md](docs/day5-deploy-a-web-app-with-codedeploy.md) |
| 6 | Set Up Your Pipeline with AWS CodePipeline | Done | [docs/day6-set-up-your-pipeline-with-aws-codepipeline.md](docs/day6-set-up-your-pipeline-with-aws-codepipeline.md) |

## Highlights

- Diagnosed and fixed IAM permission gaps blocking CodeArtifact token retrieval and CodeBuild's dependency resolution, both root-caused to missing least-privilege roles rather than credential issues
- Went beyond the guided steps to publish a custom package to a private CodeArtifact repository with a generated checksum for integrity verification
- Added an automated security-scan gate to the build pipeline, checking for hardcoded secrets before every build

## Structure

```
docs/           write-up for each day, architecture, walkthrough, issues and fixes
docs/images/    supporting screenshots and diagrams, one folder per day
```

---

Built as part of NextWork's AWS DevOps Challenge, extended with additional debugging notes, a security scanning step, and custom package publishing beyond the guided curriculum.
