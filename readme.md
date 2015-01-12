# Meteoric Projects: A tutorial on how to make a hybrid mobile app with [Meteor](https://www.meteor.com/) + [Ionic](http://ionicframework.com/)

Lets go step by step making a simple-ish Meteor mobile app using Meteoric and some of the most popular Meteor packages.

### What we will build

You landed your first enterprise client, nice! They need a secure system to manage their projects, contacts and notes. Eventually they will need a desktop web interface but for now they asked for native mobile apps. The app will need to serve iOS, Android and Window clients. Since they require three platforms, real-time data and you are a web developer... you obviously chose to use the amazing Meteor platform and Ionic UI.

Your client had a designer loosely wireframe the app, see below. As it sometimes goes not all the views have been provided so we will need to use our best judgement on the forms, pop-ups, modals and other interactions.

Got [Sketch.app](http://bohemiancoding.com/sketch/)? Download this app's [wireframe](https://www.dropbox.com/s/ry0iwzwro1f7blg/Meteoric-Projects-Mockup.sketch?dl=0).

![meteoric projects wireframe](https://www.dropbox.com/s/llxcilp1np7v1re/meteoric-wire.png?raw=1)

### Development Workflow

I find it useful when learning something new to always know "where" I am in an overall sense while working in the weeds. Data (Collections) drives this app and it will drive our workflow too. Below is the steps we will take when building **each** collection.

#### Workflow Process

1.  Create Story Issues
-  Create Collection
-  Create Schema(s)
-  Create Seed Data
-  List (Index)
  -  Create List Publications
  -  Create List Controller
  -  Create List Route
  -  Create List Templates
-  Record Details
  -  Create Record Detail Publications
  -  Create Record Detail Controller
  -  Create Record Detail Route
  -  Create Record Detail Templates
-  Record Edit
  -  Create Record Edit Publications
  -  Create Record Edit Controller
  -  Create Record Edit Route
  -  Create Record Edit Templates
-  Record Add
  -  Create Record Add Publications
  -  Create Record Add Controller
  -  Create Record Add Route
  -  Create Record Add Templates
-  Resolve "Blocking" Issues

#### Chapters (Development Order)

[Chapter 01: Initial Setup](/ch01-setup.md)
[Chapter 02: Users Collection](/ch02-users.md)
[Chapter 03: Contacts Collection](/ch03-contacts.md)
[Chapter 04: Activities Collection](/ch04-activities.md)
[Chapter 05: Projects Collection](/ch05-projects.md)
[Chapter 06: ProjectContacts Collection](/ch06-projectcontacts.md)
[Chapter 07: Notes Collection](/ch07-notes.md)
[Chapter 08: User Profile Features](/ch08-userprofilefeatures.md)
[Chapter 09: Administration Features](/ch09-administration.md)

