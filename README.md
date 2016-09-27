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

## 02 - Running the server and adding react dependencies

In order to run the local light weight server to serve our files use the following command

```
npm run dev
```

This should open your default browser and serve the index.html page created in the previous lession.

###Installing react in our application using bower
Bower like NPM is a dependency management tool. Bower js is used for managing front end components like html, css, js etc.

First let us install bower globally so that it can be used from the command line.

```
npm install -g bower
bower init
```
`bower init` creates a `bower.json` similar to `package.json` but used to manage front end dependencies.

Once bower is installed you can install front end dependencies like `jquery`, `react`, `angular` etc.

Let us install react and its dependencies first.

```
bower install --save react babel
```

Now we reference the files in our HTML page.

```
    ...
        <script src="bower_components/react/react.js"></script>
        <script src="bower_components/react/react-dom.js"></script>
        <script src="bower_components/babel/browser.js"></script>
    </head>
    <body>
        <div id="example"></div>
        ...
    </body>
```

##03 - JSX and HelloWorld component

JSX is a preprocessor step that adds XML syntax to JavaScript. You can definitely use React without JSX but JSX makes React a lot more elegant. Just like XML, JSX tags have a tag name, attributes, and children. If an attribute value is enclosed in quotes, the value is a string.

Our first component

```
    ....
       <div id="example"></div>
       <!-- Runtime JSX compiler script -->
       <script type="text/babel">

            var HelloWorld = React.createClass({
                render: function() {
                    return (
                    <p>
                        Hello, <input type="text" placeholder="Your name here" />!
                        It is {this.props.date.toTimeString()}
                    </p>
                    );
                }
            });

            setInterval(function() {
                ReactDOM.render(
                    <HelloWorld date={new Date()} />,
                    document.getElementById('example')
                );
            }, 500);

        </script> 
    ....
```