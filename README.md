# Managing software packages with GitHub Packages
:wave: Welcome to the packages workshop !!

In this workshop we will be learning on how to use GitHub Packages in your software development lifecycle.
- Creating a package
- Authenticating with the package Registry
- Publishing a packages
- Automating using actions
- Sharing packages

## Pre-requisites
- Install python3 from [here](https://www.python.org/downloads/), if not installed.
- Install docker from [here](https://docs.docker.com/engine/install/), if not installed.


## Steps

Local Development
1. Fork this repository
2. Install requirements `pip3 install -r requirements.txt`
2. Run the project `python3 src/server.py`
2. Build the image locally `docker build --tag "workshop-constellation:pre-release" .`
2. Run the image locally `docker run -p 9001:9001 workshop-constellation`
2. Login to GHCR.io using PAT
   1. Create PAT with `write:packages` scope
   2. Store PAT in the env variable `CRPAT`
   3. `echo $CRPAT | docker login ghcr.io --username <username> --password-stdin`
3. `docker tag workshop-constellation:pre-release ghcr.io/<orgname>/workshop-constellation:pre-release`
2. `docker push ghcr.io/<orgname>/workshop-constellation:pre-release`
3. `docker pull ghcr.io/<orgname>/workshop-constellation:pre-release`
3. `docker run ghcr.io/<orgname>/workshop-constellation:pre-release`

Automating using Actions
1. Create a workflow for pull_request event
2. Authentication using GITHUB_TOKEN
3. Build & Publish using actions

# References
1. [Introduction to GitHub Packages](https://docs.github.com/en/packages/learn-github-packages/introduction-to-github-packages)
2. [Working with GitHub Container Registry](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-container-registry)
3. [Working with GitHub Actions & Packages](https://docs.github.com/en/packages/managing-github-packages-using-github-actions-workflows/publishing-and-installing-a-package-with-github-actions)
4. [GitHub Packages Billing](https://docs.github.com/en/billing/managing-billing-for-github-packages/about-billing-for-github-packages)
