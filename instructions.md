
# ADD THESE TO BETWEEN BODY TAGS

<!-- <script crossorigin src="https://unpkg.com/react@17/umd/react.production.min.js"></script>
<script crossorigin src="https://unpkg.com/react-dom@17/umd/react-dom.production.min.js"></script> -->
<!-- <script src="/scripts/app.js"></script> // THIS IS THE JAVASCRIPT FILE -->

<script src="/bundle.js"></script> //THIS IS THE JAVASCRIPT FILE BUNDLED BY WEBPACK

# INSTALL LIVE SERVER
npm i live-server

# RUN LIVE SERVER
live-server public     //Public is the folder where is the entry page file

# Install Babel AUTOMATICALLY CONVERT TO ES5
-   npm install -g babel-cli

# INSTAL NPM IN ROOT
npm init



# SPECIFY OUTPUT AND INPUT FOLDERS FOR BABEL
babel src/app.js --out-file=public/scripts/app.js --presets=env,react

# WATCH BABEL CHANGES  // ONLY WHEN INSTALLED GLOBALLY
babel src/app.js --out-file=public/scripts/app.js --presets=env,react --watch

# UNISTALL BABEL AND LIVE SERVER AS GLOBAL DEPENDENCIES
# IT IS BETTER IDEA TO INSTALL THEM LOCALLY

npm uninstall -g babel-cli live-server

# INSTALL BABEL AND LIVE_SERVER LOCALLY 
npm i babel-cli

# INSTALL LIVE_SERVER LOCALLY 
npm install live-server

 # OR INSTALL WEBPACK SERVER //prefered
 npm install webpack-dev-server

# INSTALL WEBPACK LOCALLY AND WEBPACK-CLI AND CREATE webpack.config.js  FILE FOR WEBPACK IN THE ROOT
npm install webpack

in webpack.config.js  

ADD

devServer: {
  contentBase:  path.join(__dirname,'public'),
}

add to package.json just above "dependencies"
  "scripts: {
      "serve-live": "live-server public/",   // for live server , not needed when used webpack dev server
      "build": "webpack",
      "dev-server":"webpack-dev-server",// not needed when the SERVE bellow is used
      "serve": "./node_modules/.bin/webpack serve" // THIS STARTS THE SERVER AND BUNDLE WITH JUST ONE COMMAND
 }

 NOW YOU CAN RUN LIVE SERVER WITH - npm run serve
 NOW YOU CAN RUN BABEL WITH       - npm run build-babel
 NOW YOU CAN RUN WEBPACK WITH      -npm run build

 # INSTALL BABEL FOR WEBPACK 
 npm install babel-core
 npm install babel-loader@7

 # TO TRACE ERRORS 
 add this to the webpack.config.js file

 devtool: "cheap-module-source-map"  //it indicates where the error occured

 # SIMPLIFY ES6 CLASSES WITH BABEL PLUGIN AND CONFIGURE IN .babelrs FILE// THIS ELIMINATES BINDING 
 npm install babel-plugin-transform-class-properties


 # CSS AND SCSS
 npm i css-loader
 npm i style-loader

 npm install sass-loader
 npm i node-sass

 npm i normalize.css   // to get reset


 # ADD THE CODE TO WEBPACK CONFIG
 test: /\.s?css$/,
            use : [
                'style-loader',
                'css-loader',
                'sass-loader'
            ]

# INSTALL REACT ROUTER 
npm i react-router-dom

# ADD TO WEBPACK.CONFIG.JS FILE THE FOLLOWING AND RESTART SERVER

add to devServer another property  historyApiFallback: true

Result =

devServer: {
  port: 3000,
  open: true,
  contentBase: path.join(__dirname, 'public'),
  historyApiFallback: true  //important for front end to comunicate with server
}