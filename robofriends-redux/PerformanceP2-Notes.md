## V124 - Code splitting introduction

How to deliver JS files in the most efficient eay possible
Code Splitting or progrssive bootstrapping

What is Code Splitting?
Code splitting is the splitting of code into various bundles or components which can then be loaded on demand or in parallel. ... While the total amount of code is the same (and perhaps even a few bytes larger), the amount of code needed during initial load can be reduced.
Source - [https://developer.mozilla.org/en-US/docs/Glossary/Code_splitting#:~:text=Code%20splitting%20is%20the%20splitting,on%20demand%20or%20in%20parallel.&text=While%20the%20total%20amount%20of,initial%20load%20can%20be%20reduced.]

The above practice gives the browser a little less work to do at initial loading/fetching.
This can also be very beneficial as JS is a single threaded programming language, meaning it can only execute one line of code at a time.

Production build of 3rd party libraries - npm run build - buid the production version of create react app.

## v125 - Exercise 1 - Code splitting

## v126 - Code splitting part 1

Tip - In react use super() so that we can use the 'this' keyword.

## v127 - ES2020 - Dynamic import()

## v128 - Code Splitting Part 2

With the import statement you are importing dynamically. Meaning the code will only be imported when that piece of code is requested. Happens underneath the hood with webpack. By using the import syntax we automatically tell it to code split.

Importing routes dynamically/ on the fly.
Using the import statement in code and not at top of page. This is only possible because of webpack.
The above is asychronous which means it returns a promise.

this.state.component.

In this case on the initial load page 2 and page 3 are not loaded with the bundle.js and when they are loaded they are only loaded once.

Dynamic import makes this possible.

## v129 - Code Splitting Part 3

Creating an async component - AKA Higher Order Component
A Higher Order Component is a component that returns another component
Similar to higher order function which returns another function
An example of a higher order component is like <connect></connect> in redux.

    More on Higher-Order Components - React Docs

## v130 - Code Splitting part 4

Can do component level code splitting.
Route based Code Splitting
Component based code splitting

## Note131 - Exercise #2 Code Splitting

Use react.lazy in code. Lazy loading

## V132 Solution: react.lazy() code Splitting

Run npm audit fix --force if project small and no breaking changes.
For blockchain this might be different as the tech keeps changing. Look into how to do manual package update.

React.lazy allows you to do code splitting.
Can use react.lazy when we import the components

## v133 React Performance Optimizations

Performance tool
in params add:
localhost:3000<?react.perf>

\*Note <> not added.

Open dev tools and go to performance
Hit record
Interact with app
Yellow bars refers to JS in performance tab
Highlight - Look in user timing
Since JS is single threaded whenever a component is mounting or rednering, updating it is hogging the main thread (main worker) this prevents other code from running.
In redux when using <connect><connect/> we can connect to state
React dev tools - Got this
The faster components are being rerendered the color will more closely resemble red.
slower === blue
Helpful for detecting unneccesary render cycle

## v134 Resources React Performance

## v135 React Performance Optimizations

## v136 Resources: React Performance 2

24/02/2021 - Above done

## v137 Optimizing Code review

- How do we optimize our code?
- Only load what is needed
-       Code Splitting
-           Route Based Chunking
-           Component Based Chunking
-               Above done by using webpack and dynamic import.
-               OR using tool like loadable library that does it for you
-                   and gives you a nice wrapper
-       Tree Shaking
-           Done behind the scenes by webpack
-           Removes any unused code when you actually build the app. For example
-               If you're importing masive library but only using one function from it
-                   it will discard the unused functions
-                       can be done with webpack
- Avoid blocking main thread
-       Minimizing the JS, compile, parse and execution time.
-       Be smart about how much JS we are including in our code
- Avoid Memory Leaks
-       Simply making sure that we do not keep adding memory to our apps
-           e.g, If we have many event listeners on a page and we change that page to
-               another route but event listeners not removed. Now the browser must remember
-                   more and more things
-           When browser memory low the app will crash
- Avoid Multiple re-rendering
-       Minimizing the amout of DOM manipulations we have to do

## v138 Resources: Tree Shaking 101

GOOD Guide on tree shaking here

## v139 Progressive Web Apps

- What is a progressive web app?
- Progressive web apps are web apps that behave like native apps
- Difference between web app and Pweb App
- web app must knows
-       HTML, CSS, JS
- native app must knows
-       learn native language
-           java for android
-           objective c and swift for IOS apps
-       with native apps all the files live on your phone
-             does not behave the same as web app where
-                 files are fetched from a server
-                     this is why phone apps are so big in terms of MB/GB
-       Addtionaly, native apps can send you push notifications.
-           they can also work offline
-           Never  get blank screen
-       Native apps are built to work offline
-       native apps also have access to:
-           phone hardware: camera, geo-location, push notifications
- With PWAs you can make web apps behave like native apps
-       can make browser not have top URL bar (native app aesthetics)
-       can send push notifications, works a lot faster like on phones that regular web apps
-             with PWA's you do not need approval of apple/google to get your PWA downloaded
-       App will run on all browser platforms
- GOAL of PWA's
-       * Better UX
-       * faster websites
-
-       With new HTML5 APIs we are starting to get more access to phone/foreign? hardware.
-           only native apps had this access
-       whatwebcando.today
-           Shows what access web platforms have. New features etc
-       Google supports PWA's and Apple does not
-         Google has big share in the web - makes sense for them to push PWAs
-
-       Facebook is getting mobile market share by using REACT Native.
-
-       Apple makes use of safari browser
- create-react-app already comes with PWA capabilities.
-       Because it is easy to implement it is a good idea to implement
- Lighthouse is a chrome plugin that you can run on any website:
-       will tell us some performance metrics and how close we are to that PWA
-       This extension will check for website for offline capabilities
-            and check for any other features a PWA should have
-               will then return a report
-       Also gives access to:
-           SEO, Best Practice, Accessibility, PWA, Performance in %
-               number interested in is PWA %
-       Extension will advise what can be done to improve app to PWA standards
-
-
-
-
- ## v140 - Resources: Progressive We Apps
- Topics in this resource folder:
-       Submitting PWA to 3 app stores
-       PWA Android vs iOS
-       ROBOFRIENDS GITHUB REPO
-       TOP PWA's from around the world
-
-
- ## v141 - Progressive web apps
- The goal is to make the user experience as close as possible to a native app
- Basically the user will have read functionality while internet connection off.
- Could possibly have CRUD if info saved on phone memory temporarily
-       Create list of favorite pokemon
-       See list of pokemon
-       Update list
-       Delete lists and list items
-       When internet connection back then update online profile
-       Link a schema on phone and create update
- Next vid - 3 Most important parts to building a PWA
-       HTTPS
-       App Manifest
-       Service Workers
-
-
-
- ## v142 - Progressive web Apps Examples
- HTTPS - Discussing checklist
- 3 Most important parts to building a PWA
-       HTTPS
-           Prevents bad actors from tampering with communications
-               Between the app and browser
-               Passwords sent to server can be encrypted
-           Why is HTTPS required for PWA?
-               PWA webapps use some features that require some HTTPS for
-                   security reasons
-               Github pages automatically provides you with HTTPS hosting
-               The website "Let's Encrypt" provides your own website with
-                   encryption.
-                   This is free, automated and open Certificate Authority
-               In addition to above the is "Cloudflare" (CDN)
-                   Server to host your files on - Free to paid tiers
-
-       App Manifest
-       Service Workers
-
-
- ## Note 143 - Resources PWA - HTTPS
- Tutorial on how to deploy a website on github pages
- Note on deploying a create react app on github pages
- Here is a PWA developer checklist
- Recommendation to use lets Encrypt to implement HTTPS
-
-
-
- ## v144 - PWA - APP Manifest
- Importance of adding viewport meta tag in HTML
- Comes out of the box with create react app
- This tag optimizes the app for multiple devices
- Helps with adjusting the screen size based on the device
- If you do lighthouse report you will get warning
- App manifest file
- This also comes with create react app
-       It is a simple JSON file that
-           gives the developers the ability to control how the app should appear
-               to the use in areas where they would expect to see apps such as the
-                   mobile device homescreen and define how app will be launched.
-                   How it will look.
- The manifest also gives you the ability to "add to homescreen"
- What is a splash screen?
- - when loading a PWA there will be BG color, Logo & name of app
- - - This will retreived from manifest.json file
- - - - Gives native app feel

---

-
- ## notes145 - Resources: PWA - APP Manifest
- To learn more, have a look at Viewport Meta Tag
- - Resource to help you generate icons for your robofriends PWA
- - - https://realfavicongenerator.net/
-
-
-
- ## v146 - PWA - Service Workers
- What is a service worker?
- - This is a script that your browser runs in the BG
- - - A programmable Proxy - this is the reason why we can make our apps work offline
- - - - What is HTTP proxy mean?
- - - - An HTTP Proxy basically serves as a gateway between the user and the internet. It is - - - - - used to cache files, and web pages which makes it easy for you to access them. The - - - - - - HTTP Proxy has two roles it plays one of which is as an HTTP Client and the - - - - - - - - - other as an HTTP Server which is for management, security and caching.
- - Andre definition:
- - - Allowing us to control what happens on a request by request basis
- - - - It is the reason why we can make our PWAs work offline
- - Main feature of Service Workers is offline experience
- - More resources further in course for other features
- - How do we use a service worker?
- - - In create react app we have a file called registerServiceWorker.js and in newer
- - - - versions of react it is called serviceWorker.js
- - - - - This file is executed in the index.js inside src folder
- - What does this registerServiceWorker file do?
- - - ## Check for browser support of service worker
- - - - saying: "do we actually have service worker in navigator/browser"
- - - - Can be done for each browser: website called "is ServiceWorker ready?"
- - - - "if there is a service worker, we want to use this SW prop of the navigator/browser"
- - - - - "and do something called register with service-worker.js file"
- - - - - register is common way to create SW on site
- - - - - Where does service-worker.js comming from?
- - - - - - Created in build folder (npm run build)
- - - ## Successful registration
- - - - Above if statement returns a promise
- - - - - This code will fire if true
- - - - - - On success will have two states
- - - - - - - 1. Will either be terminated to save memory or
- - - - - - - 2. Will run in BG to fetch messages and events that occurs in the network req
- - - ## Failed registration, service worker won't be installed.
- - - - - This code will fire if false
- - - ## What happens without service worker?
- - - - Our browser is going to send a request to the network/internet
- - - - WITH a SW the browser will first communicate with the SW
- - - - - In a PWA the SW acts as a network proxy
- - - - - - 1. It intercepts any request made to the network and checks to see if you really
- - - - - - - - need to communicate with the network because files might be @SW already
- - - - - - - - - When user opens new screen of PWA the req for that page first goes to SW
- - - - - - 2. When SW receives req the SW will try to access the Cache API (web api)
- - - - - - - - most browsers have this. It is included with service worker
- - - - - - - - - cache api is kind of like box where the browser stores files
- - - - - - - - - - JS, CSS files, Images - any static files
- - - - - - - - - - - The worker tries to access box to assert if req is inside box?
- - - - - - - - - - - If true then SW will return content regardless of network activity
- - - - - - 3. If false and no file, req must go to network
- - - - - - 4. Network then passes files to browser/client
- - - - What ever files we need to work offline we cache them in the cache api via SW
- - - - - On first visit req goes to network but on repeat req goes to SW to check for files
- - - - - - Will go through these steps next
- - - - - - @ 11:24 - How aove would be done before Create_react_app implemented SWs
- - - - - - - npm install sw-precache
- - - - - - - - in build step: run command:
- - - - - - - - - sw-precache --config=sw-precache-config.js
- - - - - - - - in index.js run register SW code
- - - - - - - - add manifest.json in public folder
- - - - - - - - further config sw-precache-config.js file
-
- ## v147 - Resources: PWA - Service Workers
- ## v148 - PWA - Final Thoughts
- ## v149 - Exercise: #3 - PWA
- ## v150 - Quick Note: Upcoming video
- ## v151 - Deploying Our React App
- - The Creation of the PWA is in this video
- - npm install gh-pages - This is package for github pages
- - Add deploy command to scripts section in package.json
- - predeploy in scripts will first run build to production then deploy hence predeploy
- - The entire create react app deployment process can be found in the react docs
- - Remember you get HTTPS out of the box with github pages
-
-
- ## v152 - Service Worker Updates
- - With the newer versions of create react app you have the option to
- - - opt in to using service workers
- - Update packages with npm audit, npm audit fix and npm update
- ## v153 - Solution Part 1 - PWA
- - font-display: swap; - This property will swap the font-face in as soon as it loads
- - - browsers draws text immediately and when the font-face is loaded it will swap it.
- - - - this way the user will see the default text without the special font until
- - - - - the font is fully loaded.
- - <meta name="Robo App" content="Robo Social media app ;>"> - Help with SEO
- - - Web Crawlers search for it.
- - Performance score on lighthouse can be better/worse depending on internet speed. \*
- ## v154 - Solution Part 2 - PWA
- - Because of create react app there are already PWA benefits.
- - - e.g - HTTPS, Service Workers etc.
- - The cache storage in dev tools under application tab will show what files SW's are
- - - caching.
- - Generating favicons
- - Add favicon sizes in manifest.json file according to lighthouse specs
- - - Reminder this manifest makes it possible to add app to homescreen
- ## v155 - Solution Files - PWA
- - https://progressivetooling.com - List of tools used to improve front end performance
- - Repo's of solution code.
- ## v156 - Section Summary
- - Code Optimizations - Only load what is needed
- - - Code splitting
- - - Tree Shaking
- - Avoid blocking main thread
- - Avoid Memory Leaks
- - Avoid Multiple re-rendering
- - ***
- - PWAs
- - - HTTPS
- - - App Manifest
- - - Service Worker - Deliver websites offline
- - - Out of the three types of optimizations Perf 1 and 2 covered
- - - - network optimizations
- - - - - Minimize Files
- - - - - Minimize Delivery
- - - - Front end optimizations.
- - - - - Critical Render Path
- - - - - Optimized Code
- - - - - Progressive Web Apps
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
-
