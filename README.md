docker-git-ftp
==============

A minimal Debian Slim Linux docker image with the latest [git-ftp](https://github.com/git-ftp/git-ftp).

Automatically build upon pushes to the master branch:
https://hub.docker.com/r/evox95/git-ftp

Usage
-----

Example `.gitlab-ci.yml` configuration:

```yml
deploy_production:
  image: evox95/git-ftp
  stage: deploy
  only:
    - master
  script:
    - git config git-ftp.url "ftp://*******:21/"
    - git config git-ftp.user *****
    - git config git-ftp.password *****
    - git ftp push --auto-init
```
