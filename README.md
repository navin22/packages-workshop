# Managing software packages with GitHub Packages
:wave: Welcome to the packages workshop !!

In this workshop we will be learning on how to use GitHub Packages in your software development lifecycle.
- Creating a package
- Authenticating with the package registry
- Publishing a package
- Automating using GitHub actions
- Sharing packages

## Pre-requisites
1. Set up Git and authenticate GitHub: [Instructions](https://docs.github.com/en/get-started/quickstart/set-up-git)
2. Any IDE like VS Code.
3. Install python3 from [here](https://www.python.org/downloads/), if not installed.
4. Install docker from [here](https://docs.docker.com/engine/install/), if not installed.


## Steps

Local Development
1. Fork this repository & clone to your local machine
2. Install requirements `pip3 install -r requirements.txt`
2. Run the project `python3 src/server.py`
2. Build the image locally `docker build --tag "workshop-constellation:pre-release" .`
2. Run the image locally `docker run -p 9001:9001 workshop-constellation`
2. Login to GHCR.io using PAT
   1. [Create PAT](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/creating-a-personal-access-token) with `write:packages` scope
   2. Store PAT in the env variable `CRPAT`
   3. `echo $CRPAT | docker login ghcr.io --username <username> --password-stdin`
3. `docker tag workshop-constellation:pre-release ghcr.io/<orgname>/workshop-constellation:pre-release`
2. `docker push ghcr.io/<orgname>/workshop-constellation:pre-release`
3. `docker pull ghcr.io/<orgname>/workshop-constellation:pre-release`
3. `docker run ghcr.io/<orgname>/workshop-constellation:pre-release`

Automating using Actions
1. Create a workflow using the standard templates.
2. Authentication using GITHUB_TOKEN
3. Build & Publish using actions

# References
1. [Introduction to GitHub Packages](https://docs.github.com/en/packages/learn-github-packages/introduction-to-github-packages)
2. [Working with GitHub Container Registry](https://docs.github.com/en/packages/working-with-a-github-packages-registry/working-with-the-container-registry)
3. [Working with GitHub Actions & Packages](https://docs.github.com/en/packages/managing-github-packages-using-github-actions-workflows/publishing-and-installing-a-package-with-github-actions)
4. [GitHub Packages Billing](https://docs.github.com/en/billing/managing-billing-for-github-packages/about-billing-for-github-packages)
