# Projects - Meteoric Example How-to

Lets go step by step making a simplish Meteor mobile app using Meteoric and some of the most popular Meteor packages.

### What we will build

Got [Sketch.app](http://bohemiancoding.com/sketch/)? Download this app's [wireframe](https://www.dropbox.com/s/ry0iwzwro1f7blg/Meteoric-Projects-Mockup.sketch?dl=0).

![meteoric projects wireframe](https://www.dropbox.com/s/sjhimffvxzub2c4/meteoric-projects-sketch-thumbnail.jpg?raw=1)

## 01. Initial Setup

1.	Create a new Meteor app from the terminal `$ meteor create meteoric-projects`
2.	Setup Git and push to GitHub, if you need help check [GitHub Bootcamp](https://help.github.com/categories/bootcamp/)
3.	Add standard folder structure, adapted from [Differential Boilerplate](http://github.differential.com/meteor-boilerplate/#file-structure)

	```
	.meteor/
  client/
    ├── compatibility/
    └── stylesheets/
      ├── _app-mixins.scss
      ├── _app-variables.scss
      └── app.scss
    └── views/
      └── activities/
        ├── activities.html
        ├── activities.scss
        ├── activities.js
      └── contacts/
        ├── contacts.html
        ├── contacts.scss
        ├── contacts.js
      └── notes/
        ├── notes.html
        ├── notes.scss
        ├── notes.js
      └── projects/
        ├── projects.html
        ├── projects.scss
        ├── projects.js
      └── layouts/
        ├── mainLayout.html
        └── mainLayout.js
      └── shared/
      └── index.html
  collections/
    ├── activities.js
    ├── contacts.js
    ├── notes.js
    ├── projects.js
    └── users.js
  routes/
    └── router.js
  packages/
  public/
    ├── fonts/
    └── images/
  server/
    ├── accounts.js
    ├── email.js
    ├── permissions.js
    ├── seeds.js
    └── publications/
        ├── activities.js
        ├── contacts.js
        ├── notes.js
        ├── projects.js
        └── users.js
	```
4.	Add standard packages

	Add all the following packages in one *swoop* by running this in your terminal from the project folder:
	
	```
	$ meteor add accounts-password underscore mrt:underscore-string-latest stevezhu:lodash fastclick jquery reactive-var reactive-dict iron:router zimme:iron-router-active fuatsengul:iron-router-auth dburles:collection-helpers matb33:collection-hooks reywood:publish-composite alanning:roles ongoworks:security momentjs:moment aldeed:autoform aldeed:collection2 aldeed:simple-schema tmeasday:publish-counts u2622:persistent-session zimme:collection-softremovable zimme:collection-timestampable meteorhacks:kadira meteorhacks:aggregate meteorhacks:zones matteodem:easy-search dburles:factory anti:fake fourseven:scss meteoric:ionic-sass meteoric:ionicons-sass meteoric:ionic meteoric:autoform-ionic
	```

	| Package Name | Github | Atmosphere | Website |
	|:---|:---:|:---:|:---:|
	| accounts-password | [github](https://github.com/meteor/meteor/tree/devel/packages/accounts-password) | [atmosphere](https://atmospherejs.com/meteor/accounts-password) | [website](http://docs.meteor.com/#/full/accounts_api)|
	| underscore | [github](https://github.com/jashkenas/underscore) | [atmosphere](https://atmospherejs.com/meteor/underscore) | [website](http://underscorejs.org/) |
	| mrt:underscore-string-latest | [github](https://github.com/TimHeckel/meteor-underscore-string/) | [atmosphere](https://atmospherejs.com/mrt/underscore-string-latest) | [website](http://epeli.github.io/underscore.string/) |
	| stevezhu:lodash | [github](https://github.com/lodash/lodash) | [atmosphere](https://atmospherejs.com/stevezhu/lodash) | [website](https://lodash.com/) |
	| fastclick | [github](https://github.com/ftlabs/fastclick) | [atmosphere](https://atmospherejs.com/meteor/fastclick) |
	| jquery | [github](https://github.com/jquery/jquery) | [atmosphere](https://atmospherejs.com/meteor/jquery) | [website](http://api.jquery.com/) |
	| reactive-var | | [atmosphere](https://atmospherejs.com/meteor/reactive-var) | [website](http://docs.meteor.com/#/full/reactivevar) |
	| reactive-dict | | [atmosphere](https://atmospherejs.com/meteor/reactive-dict) |
	| iron:router | [github](https://github.com/eventedmind/iron-router/) | [atmosphere](https://atmospherejs.com/iron/router) | [guide](https://github.com/EventedMind/iron-router/blob/devel/Guide.md) / [site](http://eventedmind.github.io/iron-router/) |
	| zimme:iron-router-active | [github](https://github.com/zimme/meteor-iron-router-active) | [atmosphere](https://atmospherejs.com/zimme/iron-router-active) |
	| zimme:iron-router-auth | [github](https://github.com/zimme/meteor-iron-router-auth/) | [atmosphere](https://atmospherejs.com/zimme/iron-router-auth) |
	| dburles:collection-helpers | [github](https://github.com/dburles/meteor-collection-helpers/) | [atmosphere](https://atmospherejs.com/dburles/collection-helpers) |
	| matb33:collection-hooks | [github](https://github.com/matb33/meteor-collection-hooks) | [atmosphere](https://atmospherejs.com/matb33/collection-hooks) |
	| reywood:publish-composite | [github](https://github.com/englue/meteor-publish-composite/) | [atmosphere](https://atmospherejs.com/reywood/publish-composite) | [website](http://braindump.io/meteor/2014/09/12/publishing-reactive-joins-in-meteor.html) |
	| alanning:roles | [github](https://github.com/alanning/meteor-roles/) | [atmosphere](https://atmospherejs.com/alanning/roles) | [website](http://alanning.github.io/meteor-roles/classes/Roles.html) |
	| ongoworks:security | [github](https://github.com/ongoworks/meteor-security/) | [atmosphere](https://atmospherejs.com/ongoworks/security) |
	| momentjs:moment | [github](https://github.com/moment/moment/) | [atmosphere](https://atmospherejs.com/momentjs/moment) | [website](http://momentjs.com/) |
	| aldeed:autoform | [github](https://github.com/aldeed/meteor-autoform/) | [atmosphere](https://atmospherejs.com/aldeed/autoform) |
	| aldeed:collection2 | [github](https://github.com/aldeed/meteor-collection2/) | [atmosphere](https://atmospherejs.com/aldeed/collection2) |
	| aldeed:simple-schema | [github](https://github.com/aldeed/meteor-simple-schema/) | [atmosphere](https://atmospherejs.com/aldeed/simple-schema) |
	| tmeasday:publish-counts | [github](https://github.com/percolatestudio/publish-counts/) | [atmosphere](https://atmospherejs.com/tmeasday/publish-counts) |
	| u2622:persistent-session | [github](https://github.com/okgrow/meteor-persistent-session/) | [atmosphere](https://atmospherejs.com/u2622/persistent-session) |
	| zimme:collection-softremovable | [github](https://github.com/zimme/meteor-collection-softremovable) | [atmosphere](https://atmospherejs.com/zimme/collection-softremovable) |
	| zimme:collection-timestampable | [github](https://github.com/zimme/meteor-collection-timestampable/) | [atmosphere](https://atmospherejs.com/zimme/collection-timestampable) |
	| meteorhacks:kadira | [github](https://github.com/meteorhacks/kadira/) | [atmosphere](https://atmospherejs.com/meteorhacks/kadira) | [website](https://kadira.io/) |
	| meteorhacks:aggregate | [github](https://github.com/meteorhacks/meteor-aggregate/) | [atmosphere](https://atmospherejs.com/meteorhacks/aggregate) |
	| meteorhacks:zones | [github](https://github.com/meteorhacks/zones/) | [atmosphere](https://atmospherejs.com/meteorhacks/zones) |
	| matteodem:easy-search | [github](https://github.com/matteodem/meteor-easy-search/) | [atmosphere](https://atmospherejs.com/matteodem/easy-search) | [website](https://github.com/matteodem/meteor-easy-search/wiki) |
	| dburles:factory | [github](https://github.com/percolatestudio/meteor-factory/) | [atmosphere](https://atmospherejs.com/dburles/factory) |  |
  | anti:fake | [github](https://github.com/anticoders/meteor-fake/) | [atmosphere](https://atmospherejs.com/anti/fake) |  |
	| fourseven:scss | [github](https://github.com/fourseven/meteor-scss/) | [atmosphere](https://atmospherejs.com/fourseven/scss) | [website](http://sass-lang.com/guide) |
	| meteoric:ionic-sass | [github](https://github.com/meteoric/ionic-sass/) | [atmosphere](https://atmospherejs.com/meteoric/ionic-sass) | [website](http://ionicframework.com/docs/components/) |
	| meteoric:ionicons-sass | [github](https://github.com/meteoric/ionicons-sass/) | [atmosphere](https://atmospherejs.com/meteoric/ionicons-sass) | [website](http://ionicons.com/) |
	| meteoric:ionic | [github](https://github.com/meteoric/meteor-ionic/) | [atmosphere](https://atmospherejs.com/meteoric/ionic) | [website](http://meteoric.github.io/) |
	| meteoric:autoform-ionic | [github](https://github.com/meteoric/autoform-ionic/) | [atmosphere](https://atmospherejs.com/meteoric/autoform-ionic) |  |
	
5.	Add standard `<head>` elements in **index.html**

    ```
    
        <head>
          <title>Meteoric Projects</title>
          <meta name="viewport" content="initial-scale=1, maximum-scale=1, user-scalable=no, minimal-ui">
          <meta name="apple-mobile-web-app-capable" content="yes">
          <meta name="apple-mobile-web-app-title" content="Meteoric Projects">
          <meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
        </head>

        <body>
        </body>
    ```

	