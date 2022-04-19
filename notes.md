https://devopscube.com/run-docker-in-docker/

```
sudo chgrp docker /var/run/docker.sock
nuc11:~ # mkdir /var/media/DATA/github-actions
nuc11:~ # chown 1000:1000 /var/media/DATA/github-actions
nuc11:~ # cp -dpR LibreELEC.tv/sources /var/media/DATA/github-actions/

# build the github runner (use github-runner/Dockerfile)
docker build --pull -t github-runner github-runner

```

need to fix the Dockerfile so that the _work directory is specified as:
```
# Authentication


√ Connected to GitHub

# Runner Registration

Enter the name of the runner group to add this runner to: [press Enter for Default]

Enter the name of runner: [press Enter for 1a46680e167f]

This runner will have the following labels: 'self-hosted', 'Linux', 'X64'
Enter any additional labels (ex. label-1,label-2): [press Enter to skip]

√ Runner successfully added
√ Runner connection is good

# Runner settings

Enter name of work folder: [press Enter for _work] /var/media/DATA/github-actions/_work

√ Settings Saved.
```
The you can `docker@1a46680e167f:~/actions-runner$ ./run.sh`
