.. image:: https://codebuild.us-east-1.amazonaws.com/badges?uuid=eyJlbmNyeXB0ZWREYXRhIjoiRzZWVEo0UWlTRGtRTDBDa0VVekptcXhoOXdndjlCeHNPSnhRem9rcVc3dTF4dk5hWlBUamYzd3lIY2RPNHU1Q2htV3MrSVBUdkpwOHNWQzBKVWF1WUJ3PSIsIml2UGFyYW1ldGVyU3BlYyI6InBBZ2FNUXN0RXliRjNRL2EiLCJtYXRlcmlhbFNldFNlcmlhbCI6MX0%3D&branch=master

How to Use AWS Code Pipeline with a Public GitHub Repo
==============================================================================

You might be familiar with lots of free CI/CD platform for Public Project, such as CircleCI, TravisCI. It runs your build script in a custom container every time you check in code to your Git Repo (Mostly GitHub repo), perform, install, build, test, deploy.

AWS Code Pipeline is a equivalent service.

Advantage of AWS Code Pipeline:

1. seamless integration if you want to deploy your app to AWS EC2, ECS, etc ...

Disadvantage:



Use Public Github Repo to trigger Code Build
------------------------------------------------------------------------------

- Project configuration - project name: ``learn-code-pipeline-public``
- Project configuration - Enable badges: ``Yes``
- Source - source provider: ``GitHub``
- Source - repository: Repository in my ``GitHub Account`` (``Public Repository`` is for building source from other's party repo, for example, you want to test if the latest version of an open source project are compatible with your project)
- Source - GitHub repository: https://github.com/MacHu-GWU/learn-code-pipeline-public.git
- Primary source webhook events - Webhook: ``Rebuild every time a code change is pushed to this repository``, important this is the webhook allow you to trigger the build.
- Environment - Operation System: ``Amazon Linux 2``
- Environment - Runtimes: ``Standard``
- Environment - Runtimes: default
- Environment - Runtimes: default
- Buildspec - Build specifications: ``Use a buildspec file``


Advance Customization
------------------------------------------------------------------------------

- Filter GitHub Webhook Event, trigger build only on ... : https://docs.aws.amazon.com/codebuild/latest/userguide/sample-github-pull-request.html
