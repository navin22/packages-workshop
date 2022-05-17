# Managing software packages with GitHub Packages




## Pre-requisites
- Install python3 if not present
- Install docker


## Steps
1. Fork this repo
2. Install requirements `pip3 install -r requirements.txt`
2. Run the project `python3 src/server.py`
2. `docker build --tag "pre-release" .`
2. `docker run -p 9001:9001 workshop-constellation`
2. docker push
3. docker pull
3. docker run




# References
