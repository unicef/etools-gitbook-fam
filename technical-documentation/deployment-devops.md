# Deployment / DevOps

From a development standpoint we follow the standard git flow doing Pull Requests \(PR's\) for changes, code review and then merging to develop \(the integration branch for testing / staging environments\) and master \(stable\) branches.

Once code has been merged to develop/master it is automatically deployed to staging/production using the following tooling/flow:

![Code deployment flow](../.gitbook/assets/assets-2f-kzwqgc7o0kw5edlhvvk-2f-l35bucwwvekwqjs7lmz-2f-l35fio3js65czzc7oua-2fprp-documentation-depl.png)

 CI is done in CodeFresh where images are built and tests are run. CodeFresh then pushes the various images to Docker Hub, which is then automatically picked up by the appropriate "stack" in Docker Cloud.

