# react-session

#Using this repository

```
git clone https://github.com/nisheed2440/react-session.git
```

```
git checkout lesson-<lesson number>
```

example:
```
git checkout lesson-01
```

## 01 - Package.json
#Package.json

A package.json file contains meta data about your app or module. Most importantly, it includes the list of dependencies to install from npm when running npm install.

Creating a `package.json` file is easy. All you have to do is run

```
npm init
```
in your root of your app or module.

###Installing [`lite-server`](https://github.com/johnpapa/lite-server) module as a dependency

Lightweight development only node server that serves a web app, opens it in the browser, refreshes when html or javascript change, injects CSS changes using sockets, and has a fallback page when a route is not found.
```
npm install --save-dev lite-server
```

####Configuring package.json to use lite-server

```
//Inside package.json...
....
  "scripts": {    
    "dev": "lite-server"
  },
....
```

