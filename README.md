# A Mahjong client/server project.

![screenshot 311](https://cloud.githubusercontent.com/assets/177243/15599542/c5f1087e-2398-11e6-89e8-11ca62b2a17f.png)

This repository contains a client/server implementation for playing networked [Mahjong](https://en.wikipedia.org/wiki/Mahjong), using web sockets to connect each player to the server, specifically relying on [socket.io](http://socket.io).

And for those who think mahjong is a single-player tile matching game: it's not. It's a four player competitive game around forming high-scoring tile combinations with limited [common knowledge](https://en.wikipedia.org/wiki/Common_knowledge_%28logic%29) as well as [imperfect information](https://en.wikipedia.org/wiki/Perfect_information) local for each player.

## Running things

You'll need a modern version of [Node.js](https://nodejs.org) to run this project (as this project uses ES6 in lots of places), which at this point I kind of expect everyone has installed anyway. If not, install that first. You'll also need [`git`](https://git-scm.com), of course, but you're looking at a project on github so that part shouldn't have needed mention.

With Node.js installed, the simplest way to run things is to `git clone` this repo, run `npm install` in the `./mahjong` dir that makes (to get all the dependencies installed), and to then run `npm start` in the same dir to start up both the server (which runs from `./src/server/server.js`) and run a live-compile for the web client (compiled using the webpack config in `./src/client/web`).

- The server will run as game host on [http://localhost:8081/](http://localhost:8081)
- The client is served on [http://localhost:8081/client](http://localhost:8081/client)

Connecting to [http://localhost:8081/](http://localhost:8081) will give you a link to open the client.

## Release status

**status: close to alpha release**

This is a work in progress, so there's plenty that doesn't work right now, hopefully I can take this line out of the README.md in the near future.

## License?

While this code is being developed, everything in this repository is "all rights reserved". You have permission to clone this repo to run the code, but you can't modify and then redistribute the code, and you most certainly aren't permitted to run the code and make that accessible to the world at large. 

These restrictions will be greatly relaxed once the code gets closer to "releasable" state.

## Contributing

If you want to help improve this codebase, or add things you feel are missing: hurray! There's a few obvious places to start looking.

### reporting bugs

Did you find a bug and want to report it? That's great! There will always be bugs that haven't been found by thosse writing the code, and hearing from you when you run into one is super valuable in terms of improving things for everyone. Take a screenshot, describe what was happening when you saw the bug manifest, and let's get that bug squished!

### tile sets

You can never have too many nice looking tiles, so if you have an MJ set that you particularly like and want to have your tiles added to the game, have a look at the `./apps/client/web/images/tiles` directory.

### new play rules

Everyone has their own play rules, and even as "officially recognized" rule sets, there are lots and lots, so if you want to help write a new ruleset, or implement one that you know of from other games (digital or real life), have a look at the `./apps/server/lib/game/rulesets` directory. If you want to just see how things work, have a look at the `minimal` ruleset for inspiration, and if you want to do any testing: remember to *rig the wall*: the `./apps/server/lib/game/wall.js` file comes with a commented off function that can be used to set up the wall exactly the way you want it to, so that you can start a game set up to do whatever you need in a single click. It saves a lot of testing time!

### UI improvements

It's extremely hard to come up with the perfect UI, so I like to take the "does it work at least a little? great, let's use that and then improve it as time goes on" approach. As such, the UI is certainly not stellar right now, but does allow all the functions you might need out of playing the game. However, you might be *much* better at UI design than I am, so if you have some good ideas and want to show mockups of what would be a better interface for players to both play the game and engage with each other (through a lobby, or ingame chat, etc), then your input is just as important as developer work on the code.

### Documentation

Do you want to help build out the documentation around both playing mahjong using this client/server implementation or just the game in general? That's great! When you write good docs *everybody wins*, so do get in touch and you can get your write on!

## Where to contribute

We're doing all the work right here, on github. Hit up the [issue tracker](https://github.com/pomax/mahjong/issues), which is emphatically **not** a "bug tracker", but a tracker of whatever issues are relevant to a project, covering all the above-mentioned points, and just start a new issue if you want to jump into this project.

### Is there a CLA?

No, there is not, but there is also no personal credit for specific parts of the code or its assets: by contributing to this project, your contributions become part of the project, and every contributor is valued equally. The contributor list is also based on your github name, not your real world name, unless you specifically also want that in the contributor list. Any legal complications (for instance, contributing code you did not have the rights to) are resolve based on the commit history: offending contributions will be reverted, and like normal human beings we'll find a way to make what you wanted to contribute can be done without breaking the law.
