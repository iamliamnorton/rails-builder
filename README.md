# Rails Builder

Simple dockerized rails builder using tailwind, postgres, and not test unit:

1. Clone this repo into your new Rails dir:
```
git clone git@github.com:iamliamnorton/rails-builder.git .
```
2. Remove .git so new app can be setup
```
rm -rf .git
```
3. Build the rails-builder image:
```
docker build -t rails-builder -f Dockerfile.rails .
```
4. Run with appropriate APP_NAME:
```
APP_NAME=app docker run -it -v $PWD:/opt/app rails-builder rails new . --name $APP_NAME --database postgresql --skip-action-mailbox --skip-action-text --skip-active-job --skip-jbuilder --skip-dev-gems  --skip-test --skip-system-test --javascript bun --css tailwind
```
