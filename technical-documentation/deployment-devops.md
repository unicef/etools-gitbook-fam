# Deployment / DevOps

From a development standpoint we follow the standard git flow doing Pull Requests \(PR's\) for changes, code review and then merging to develop \(the integration branch for testing / staging environments\) and master \(stable\) branches.

Once code has been merged to develop/master it is automatically deployed to staging/production using the following tooling/flow:

![](../.gitbook/assets/deploy_new.png)

CI is done in CircleCI where images are built and tests are run. CircleCI then pushes the various images to Docker Hub, which is then automatically picked up by the appropriate "stack" in Docker Cloud.

