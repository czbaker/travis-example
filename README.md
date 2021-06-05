# Full-Stack Example for Travis #

This is just a small app I'm throwing together to show how the client/server work together to build
a full-stack Node application.   The individual "parts" will be described below.

Instead of using "vanilla" JS to develop this project, I will be using TypeScript, which is a superset of JS that
adds a couple really nice features, the most important of which is strong typing which JS itself lacks entirely.

I highly recommend using it for pretty much everything, since it's basically superior in every way.

It also has a built-in bundler, so you don't need to use stuff like Parcel unless you need to bundle other assets
(like we do for our client, due to CSS/HTML files).

### server/

This will show how you're to build a small Express-based server/API that lets you server various endpoints
to a user.   Included in this example are endpoints necessary to register new users and login/logout users who 
already exist.

We'll include endpoints that both **require** and **do not require** you to be logged in via Passport.

Our users will be stored via Mongoose in a local instance of MongoDB, accessed through Mongoose (we'll define a user
model).

We will also be using TypeScript to develop our back-end, so we will not need to use something like **Webpack** for 
bundling our code (deployment purposes).

* TypeScript
* Express
* Mongoose (MongoDB ORM)
* PassportJS (Authentication)
  * Local (`passport-local`)
  * Facebook (`passport-facebook`)
  * Twitter (`passport-twitter`)
    
### ./client* (-react, -angular)

These will be examples of how you'd build a small app using React (front-end library) or Angular (more of a front-end
framework).

We'll have a front page, a second page (about us!), then a login and registration interface to show how you handle
requests to a server and deal with the results.

We'll also have a "hidden" page that will *only* display on our menu when you're logged in, and if you attempt to
access that page without authentication, it will display an error and redirect you to the login/registration
page so that you can log in to the application and try again.

I will do my best to build identical setups with both frameworks to show the differences of how they're written to
achieve the same result.

##### ./client-react:

* TypeScript
* React
* Axios (for sending HTTP requests and handling results/errors)
* Material UI (UI library incorporating Material Design by Google)
* MobX & `mobx-react` (Global stage management, so we can keep track of things between components in an easier fashion)
* Parcel (for bundling our code to deploy)

##### ./client-angular:

* TypeScript
* Angular
* Axios (for sending HTTP requests and handling results/errors)
* `angular-material` (UI library incorporating Material Design by Google, just as above)
* `mobx-angular` (Global stage management, so we can keep track of things between components in an easier fashion)
* Parcel (for bundling our code to deploy)

I will try to keep this part of the README updated with the libraries that are in use.

### Running the code/project

I'll describe here how you're supposed to start up the project and run it later, so it can be tested.