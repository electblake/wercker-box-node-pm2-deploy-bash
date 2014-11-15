# node-bash-pm2-release

**Dependencies for Node.JS, Foundation, Compass, and PM2 Deployment!**

**Expects**

`./ecosystem.json` defines all your deployment goodness

**Workflow Files:**

`./deplyoment/pm2-post-deploy.sh`

```
// run on build step after ssh is handled
./deployments/build-release.sh
```
**Example build-release.sh**

```

**#!/usr/bin/env sh**
echo "Building Release..."
echo "-- npm install"
npm update musi-data --registry https://private.registery/<sEcRet-tok3n>
npm install

echo "-- [app] bower install"
bower install

echo "-- [theme] bower install"
cd theme-profile_home && bower install && cd ../

```

This is a specialized fork of my [Node Grunt Compass Box](https://github.com/electblake/wercker-box-node-grunt-compass) which is designed:
> ...to build "mean"'ish stacks. Foundation, Compass AngularJS, ExpressJS, Mongo(oose).

#### Node Modules

The folling modules are installed globally for you.

* [Grunt](http://gruntjs.com)
* [Bower](http://bower.io)

*check wercker details page for updated versions included*

#### Build Workflow

The following ruby gems are installed for you

* [SASS](http://sass-lang.com/)
* [Compass](http://compass-style.org/)
* [Bundler](http://bundler.io/)

#### Deploy Workflow

* `./deployment/build-release.sh`
* `pm2 deploy ecosystem.json $NODE_ENV`

### Related Wercker Boxes

I looked at these when creating this one, these might work better for you:

* [electblake/node-grunt-compass@0.0.5](https://app.wercker.com/#applications/5315f86108bd1cb563003473/tab/details) ([github](https://github.com/electblake/wercker-box-node-grunt-compass))
* [olger/box-yeoman@0.5.5](https://app.wercker.com/#applications/5315f86108bd1cb563003473/tab/details) ([github](https://github.com/giffdiff/box-yeoman))

### UNTESTED

This wercker is largly untested for testing platform stuff (karma, phantom), that bit was taken from: 

[olger/box-yeoman@0.5.5](https://app.wercker.com/#applications/5315f86108bd1cb563003473/tab/details) ([github](https://github.com/giffdiff/box-yeoman))

## Help

Look at the code I guess.. sorry