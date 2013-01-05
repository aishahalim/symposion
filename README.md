# Symposion

A conference management solution from Eldarion.

Built with the generous support of the Python Software Foundation.

See http://eldarion.com/symposion/ for commercial support, customization and hosting

## Usage
### Prerequisites
- python 
- pip
 - `curl https://raw.github.com/pypa/pip/master/contrib/get-pip.py | python`
- build-essential (debian) or `yum groupinstall "Development Tools"; yum install gcc;` (centos)
- install git, git clone this repository, and cd into it.

### Quickstart
- `pip install -r requirements.txt`
- `python manage.py syncdb`
- `python manage.py loaddata fixtures/*`
 
## Development
### Getting the code
- Get an account with GitHub
- Click "Fork" on this page to create a fork (copy) of this repository
- Go to the resulting repo and copy the git url
- `git clone $url`
- `cd symposian`
- Now you can work on this code, commit and push to your own github repository

### Pushing the feature to FlourishConference
- Make sure your repo is in sync with FlourishConf's
 - `git remote add flourish git://github.com/FlourishConference/symposion.git`
 - `git fetch flourish`
 - `git rebase flourish master`
 - `git push origin master`
- Go to your github fork and click *pull request*.
 - The base repo should FlourishConference/symposion and branch master. The head repo should be your fork and whatever branch you'd like to request pull from.
 - Leave a useful comment about the commit or a title and click *send pull request*
- Your feature will be merged it whenever the repo owners see fit.

## Deployment
### Development
- `python manage.py runserver localhost`
- Point your browser to localhost and it should load the project.

### Production
As of this version, the flourish beta is hosted on heroku, so deployments happen as follows

- Request the flourish heroku admin to add you as a collaborator
- cd into -your clone- and checkout a branch (called deploy here) that tracks flourish master
 - `git checkout -t flourish/master -b deploy`
 - `git remote add heroku git@heroku.com:flourishconf.git`
- Push to heroku whenever you want any branch deployed
 - `git push heroku deploy:master`
 - Check if everything's alright in the [beta heroku site] (http://beta.flourishconf.com/)
