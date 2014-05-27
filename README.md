# Overview

  Unreliable software places huge costs both on the military and the civilian economy. The current state of practice contains about one to five bugs per thousand lines of code. Formal program verification is the only way to be certain that a given piece of software is free of errors that could disrupt military operations in the field. Formal verification is currently done manually by specially-trained engineers. Consequently, formal verification has been too costly to apply beyond small, critical software components.

  The Crowd Sourced Formal Verification (CSFV) program seeks to make formal program verification more cost-effective by reducing the skill set required for verification. The approach is to transform verification into a more accessible task by creating a game that reflects the code model, is intuitively understandable, and is fun to play. Completion of the game effectively helps the program verification tool complete the corresponding formal program verification proof.

  The primary research challenge faced by CSFV is construction of automated game-level builders capable of transforming program verification models into compelling games. A particular game instance is a function of the program verification tool, the property to be verified and the program being verified. Each game instance is provided to the "crowd", either via the Web or through internal domain distribution. Game solutions are used to populate a database, then are mapped back into program annotations sufficient to allow the program verification tool to make progress toward verifying a specific program property.

  This project, the CSFV Community Gaming website project will provide the web site infrastructure and integration of the games. This will be a web site that is available on the Internet, and also will be delivered in a form where the server and the games can be installed and used behind a firewall.

  You can check the website http://www.verigames.com

  The application is written in pure JavaScript.  It runs on [node.js](http://nodejs.org/) using several supporting open-source modules.  MongoDB is used as the primary data store, using an Mongoose Object Modeling module to abstract the database access.  A memcached-based caching used to cache data query results.

  The application is intended to be easily deployed locally on CentOS, Mac, Ubuntu, and Windows Operating Systems.

### Depenedencies
 Notable dependencies of utilities module are (Including Developer/Testing dependencies starting from 5.) :
 1. Datejs - an open-source JavaScript Date Library [datejs](http://www.datejs.com/)
 2. Memcached client build on top of Node.js - [memcache](https://github.com/3rd-Eden/node-memcached)
 3. JavaScript parser/compressor/beautifier [uglify-js](https://github.com/mishoo/UglifyJS)
 4. UglifyCSS - a port of YUI Compressor to NodeJS - [uglifycss](https://github.com/fmarcia/UglifyCSS)
 5. Mocha - a feature-rich JavaScript test framework - [mocha](http://visionmedia.github.io/mocha/)
 6. Javascript Code Quality Tool - [jshint](http://www.jshint.com/)
 7. Chai - a BDD / TDD assertion library for node - [chai](http://chaijs.com/)
 8. JavaScript build tool - [jake](https://github.com/mde/jake)

# Configuration
 All Configuration is bundled in a single file, namely config/development.js. This list will explain the various options. Most things will __not__ need to be modified during development.

* **security** it holds the configuration used to encrypt passwords, the module uses [crypto.pbkdf2](http://nodejs.org/api/crypto.html#crypto_crypto_pbkdf2_password_salt_iterations_keylen_callback) with salt, iterations and keylen.
* **isLocalStorage** flag indicates whether or not the storage of files will be locally or in s3. If true, then local storage is used, otherwise, Amazon S3 service will be used for storage.
* *s3* the Amazon S3 configurations used to access Amazon S3 Puckets, used by connect-stream-s3 module, refer to [their documentation](https://github.com/appsattic/connect-stream-s3#middleware-options) for more information.

# Dependency External Tools and Softwares Setup

 Refer to [Setup Guide](https://github.com/topcoderinc/csfv_frontend_module/wiki/Setup-Guide) wiki page.

### Installing Coverage Tools

1. Download node-js coverage archive from https://github.com/visionmedia/node-jscoverage/zipball/master
2. Extract archive and run:
```
./configure && make && make install
```

# Local Deployment

1. Checkout csfv_utilities_module code
```
  git clone git@github.com:topcoderinc/csfv_utilities_module.git
```
2. Install dependencies
```
  npm install
```

3. Run tests
```
chmod +x jake.sh
./jake.sh
```


