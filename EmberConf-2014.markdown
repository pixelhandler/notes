# EmberConf 2014

The first EmberConf was a rousing success. Presenters ranged from experienced speakers to first-time speakers and from core team members to app developers. All of these perspectives were essential to represent the complete Ember community. Huge thanks to [Leah Silber](https://twitter.com/wifelette) and the rest of the conference organizers for working so hard to make this event a reflection of all the aspects we love about Ember.

While I took fewer notes for some talks than others, the correct interpretation is not that those presentations were less interesting, but rather than those speakers were engaging and their slides were detailed.

## Summary

The high level takeways:

* The community is very __healthy__: There were 430 attendees of the conference and there are 330 committers to the core Ember.js project on Github.
* The biggest themes of the conference were scaling developer __productivity__ and improved __performance__.
* A growing number large companies are releasing __ambitious single-page web apps__ built with Ember: Yahoo!, Netflix, Square
* 4 major Ember projects are landing in the next few months that will provide significant productivity and performance improvements:
  1. __Ember-CLI__ is a command line utility for managing Ember projects. [Link](https://github.com/stefanpenner/ember-cli)
  2. __Broccoli__ provides very fast builds. [Link](http://www.solitr.com/blog/2014/02/broccoli-first-release)
  3. __HTMLBars__ replaces Handlebars with a much faster (and smarter) templating engine. [Link](https://github.com/tildeio/htmlbars)
  4. __Ember Data 1.0__ provides a data persistence framework. [Link](http://emberjs.com/blog/2014/03/18/the-road-to-ember-data-1-0.html)

Blog writeups:

* [Session by session writeups by Allison Sheren](http://allisonsherenmcmillan.blogspot.com/search/label/emberconf%202014)
* [Ember Conf 2014 Wrap Up by Justin Ball](http://www.justinball.com/2014/03/27/ember-conf-2014-wrap-up/)
* [Illustrated Notes of EmberConf2014 by Michael Chan](http://chantastic.io/emberconf2014/)
* [We are EmberConf 2014 by Bill Heaton](http://pixelhandler.com/posts/we-are-emberconf-2014)

Extra Sessions:

* [Empty Your Cup Reflections on Learning Ember presented by Matt Jones](http://confreaks.com/videos/3460-emberconf2014-empty-your-cup-reflections-on-learning-ember)
* [Extending Ember with Analytics presented by Alex DiLiberto](http://confreaks.com/videos/3456-emberconf2014-extending-ember-with-analytics)
* [Array Computing Properties presented by David Hamilton](http://confreaks.com/videos/3457-emberconf2014-array-computing-properties)
* [Ember & SOA presented by Jeremy Green](http://confreaks.com/videos/3458-emberconf2014-ember-soa)
* [Admin Your App: or Why Internal Tools Matter presented by Michael Becker](http://confreaks.com/videos/3459-emberconf2014-admin-your-app-or-why-internal-tools-matter)

__2014-03-25__
  *  *  *  *

## Intro

* Inclusivity

## Keynote

Yehuda Katz and Tom Dale | [@wycats](https://twitter.com/wycats) and [@tomdale](https://twitter.com/tomdale) | [Slides](https://speakerdeck.com/tomdale/emberconf-2014-keynote) | [Video](http://confreaks.com/videos/3297-emberconf2014-keynote)

### Productivity

_Screens and Flows_

This is basically a description of the UX challenge for developers. Lots of logic and many paths through the application. All pages are full of links that interconnect the entire app. It's easy to add links (they're lightweight) so we do. Design is going to require lots of iteration and lots of interconnectivity. Productivity in this case means handling the complexity of common patterns and simplifying common patterns that in other cases would create spaghetti.

The philosophy of Ember is inspired by the philosophy of Rails. DHH: "I think the conclusion is that we're not as special as unique as we would like to believe. That fact is that the flexibility we think we need, that we want - we really don't." _Opt-in versus opt-out_ of the "good" behavior, the example here is organ donation.

The story of why you became an Ember developer is that Ember made you a more productive developer. To build more complex flows in long-lived applications.

## Using Ember to Make the Seemingly Impossible Easy

Andre Malan and Heyjin Kim | [@ramcio](https://twitter.com/ramcio) and [@heyjinkim](https://twitter.com/heyjinkim) | [Simple Reach](http://www.simplereach.com) | [Slides](https://speakerdeck.com/simplereach/using-ember-to-make-the-seemingly-impossible-easy) | [Video](http://confreaks.com/videos/3298-emberconf2014-using-ember-to-make-the-seemingly-impossible-easy)

_Migration_

_Visualization_

- D3 in Ember Component (encapsulated)
- [Donut chart exmaple in jsbin.](http://emberjs.jsbin.com/ember-conf-d3/3/edit)

Infinitely scrolling list of video elements. Performance challenge. Many post views handled by the controller, switching in the `<video>` element for the one post that's on the screen. DOM swapping. Ember-list-view.

Further reading:

- [Reusable D3 Charts with Ember Components](http://heyjinjs.us/post/57158250642/reusable-d3-charts-with-ember-js-components) by Heyjin Kim
- [Why we use D3 and Ember for Data Visualization](http://www.simplereach.com/blog/why-use-d3-ember-for-data-visualization)

## Contributing to Ember

Robert Jackson | [@rwjblue](https://twitter.com/rwjblue) | [Slides](https://speakerdeck.com/rwjblue/contributing-to-ember) | [Video](http://confreaks.com/videos/3299-emberconf2014-contributing-to-ember-the-inside-scoop)

### Why is Ember Awesome?

_Community_

* Fix / cleanup documentation
* Report and/or fix bugs
* Submit new features

### Docs

* `[DOC] Fixed typo in blah.`
* `[DOC beta] `
* `[DOC release] `

### Bug fixes

* Add a test showing regression. (If you can't do this, open an issue and attach a jsbin.)
* Fix issue.
* Prefix commit.
  * `[FEATURE ember-metal-zomg] Fix blah`
  * `[BUGFIX beta] Fix dummy`
  * Only severe regression will be pulled into release channel.
* Security: security @emberjs.com and work with the core team emberjs.com/security

### Features

_Feature Flags_

* `defeaturify` processes builds
* Check the `features.json` file.
* Only enable features in canary builds. (You can enable them in beta/release but you don't want to because bug fixes are not pulled in.)

    EmberENV = {
      FEATURES:  {
      }
    }

* Flag name: Package name + short feature name = ember-metal-zomg
* Add to features.json as last line
* Set value to `null`
* Rebase on every change.
* Add to FEATURES.md with description and include PR link for further reading.
* Hide changes behind flags: `if (Ember.FEATURES.isEnabled('ember-metal-zomg')) { ... } else { ... }`
* Check the "Enable Opt Features" checkbox in QUnit UI.
* Commit Prefix - Features: `[FEATURE ember-metal-zomg]`
* Project svelt is trying to keep the core slim so that file sizes don't bloat.

DOC, BUGFIX, FEATURE, SECURITY

## Ember Data

Igor Terzic | [@terzicigor](https://twitter.com/terzicigor) | [Slides](http://terzicigor.com/talks/index.html#/) | [Video](http://confreaks.com/videos/3300-emberconf2014-ember-data-and-the-way-forward)

Framework: "Way of reasoning about problems abstractions."

Data Persistence Framework

* data transformation ("easy")
* asynchronicity ("medium")
* caching ("medium")

* adapter/serializer ("easy", so it's more flexible)
* store/models (hard, so it's locked down)

* locality is the hard part and is the current focus of Ember Data 1.0

## Broccoli

Jo Liss | [@jo_liss](https://twitter.com/jo_liss) | [Slides](http://www.slideshare.net/jo_liss/broccoli-32911567) | [Video](http://confreaks.com/videos/3301-emberconf2014-no-more-grunt-watch-modern-build-workflows-with-broccoli)

* [Broccoli First Release Blog Post](http://www.solitr.com/blog/2014/02/broccoli-first-release/)

### Motivations

_Ember tooling_

* Package management: Bower
* Build tool: ???

_What about `grunt watch`?_

* Complex
* Slowness as the app grows in size. Waiting 10 seconds is unnacebptable because you're doing it hundreds of times a day.

### Part 1, build definitions: Brocfile.js

* conact()
* filterCoffeeScript()
* minify:

    if (process.env.BROCCOLI_ENV === 'production') {appJs = uglifyJavaScript(appJs) };

* compileSass()
* mergeTrees()

### Part 2, plugin API

Broccoli only knows trees. Tiny API. Big helper packages.

* .read()
* .read()
* .read()
* .cleanup()

* broccoli-transform: (srcDir, destDir)
* broccoli-filter: processString. broccoli-filter has cache.

### Integration

Broccoli is a small library. Just builds. Grunt is a good task-runner for generating, running test, deploying.

[Broccoli Announcement](http://bit.ly/broccoli-announcement)

Fingerprinting discussion. Has to be done by Broccoli or EmberCLI. There is a grunt plugin that might serve as an interim solution.

## Animations and Transitions

Edward Faulkner | [@eaf4](https://twitter.com/eaf4) | [Slides](http://ef4.github.io/ember-animation-demo/#/title-slide) | [Video](http://confreaks.com/videos/3302-emberconf2014-animations-and-transitions-in-an-ember-app)

[Follow along with the demo](http://e4.github.io/ember-animation-demo)

* Translate 0 hack to give all elements the same rendering context.
* Observe height with computed property to use with CSS. "Growing box" for example: adding and subtracting form fields.
* willTransition action handler on route.
* slide-demo-source has a lot of detail about delaying transitions for animations.
* modal-launcher using query parameters and name outlet.
* Ember attaches event handlers at the top of the DOM for events you're not using, such as scroll events, which causes "jank" because it blocks the native scroll acceleration. The solution is to wrap part of the DOM where you do care about scroll events in a component.

## Angular

John K. Paul | [@johnkpaul](http://ef4.github.io/ember-animation-demo/#/title-slide) | [Slides](http://johnkpaul.github.io/presentations/emberconf/components-transclude-directives/#/) | [Video](http://confreaks.com/videos/3303-emberconf2014-ember-components-transclude-my-directives)

Component Lists from Paul and @coderberry. The goal is to make these reusable and shared.

"Transclusion" is a real thing and pretty useful: [Wikipedia explanation](http://en.wikipedia.org/wiki/Transclusion)

## Modeling the App Store and iTunes with Ember Data

Jeremy Mack | [@mutewinter](https://twitter.com/mutewinter) | [Slides](http://emberconf.com/images/slides/2014_jmack.pdf) | [Video](http://confreaks.com/videos/3304-emberconf2014-modeling-the-app-store-and-itunes-with-ember-data)

* "I create with Ember" on his business card.
* Tapas with Ember
* Coffeescript

["Everyone knows their name" slide with code"](http://cl.ly/image/0v2O0O0U2A26) from [this tweet](https://twitter.com/mutewinter/status/448881774077022208)

### Launching [fnd.io](https://fnd.io) today

[Macstories article on launch](http://www.macstories.net/news/fnd-brings-fast-convenient-itunes-store-search-and-product-pages-to-the-web/)

Really amazing high level use of Ember and Ember Data to wrap the iTunes store search APIs.

_Using fast click for really fast touch events._

## HTMLBars

Erik Bryn and Kris Selden | [@krisselden](https://twitter.com/krisselden) and [@ebryn](https://twitter.com/ebryn) | [Slides](http://talks.erikbryn.com/htmlbars-emberconf/#/) | [Video](http://confreaks.com/videos/3305-emberconf2014-htmlbars-the-next-generation-of-templating-in-ember-js)

Ha! Almost ready. But it's going to be awesome and fast.

__2014-03-26__
  *  *  *  *

## The {{x-foo}} In You

Ryan Florence | [@ryanflorence](https://twitter.com/ryanflorence) | [Instructure](http://instructure.com) | [Slides](https://github.com/rpflorence/talk-emberconf-2014) | [Video](http://confreaks.com/videos/3306-emberconf2014-the-x-foo-in-you)

Components are:

* An optional template
* Isolated Ember.View controlling it
* The view is the context (it is its own controller, sorta kinda)

* Binding demo {{ic-tabs}} for tabs inside a page with query params.
* Actions demo {{ic-menu}} for sending actions from a select menu (whose events do not normally bubble up to the top as expected.)

* "Composite components" are components built out of smaller components.
* "Convenience components" for certain configurations of the component that are commonly used.

Child components tell parent components that they exist rather than parent look for child. Do that on willInsertElement().

* [Instructure Github](http://instructure.github.io/ic-ember)
* [Instructure ic-tabs](https://github.com/instructure/ic-tabs/tree/master/lib)

## Ember CLI

Stefan Penner | [@stefanpenner](https://twitter.com/stefanpenner) | [Yapp](http://yapp.us) | [Slides](http://static.iamstef.net/ember_conf_2014.pdf) | [Video](http://confreaks.com/videos/3307-emberconf2014-software-productivity-and-ember-ember-cli)

Yapp does consulting work.

"Abstractions enable cost sharing" across the entire open source community contributions.

[Ember CLI Github](https://github.com/stefanpenner/ember-cli)

## Ember is for the children

DeVaris Brown | [@devarisbrown](https://twitter.com/devarispbrown) | [Zendesk](http://www.zendesk.com/) | [Slides](https://speakerdeck.com/devarispbrown/ember-is-for-the-children) | [Video](http://confreaks.com/videos/3308-emberconf2014-ember-is-for-the-children)

* 38% unemployment rate African American ages 16-19.
* Tough to be a teacher because of the surrounding context outside the class.
* Need to teach [typing.io](http://typing.io)

### Get involved.

[Code combat](http://codecombat.com/) for teaching kids programming with games.

## The one where Mr. Router embraces the controller

Alex Matchneer | [@machty](https://twitter.com/machty) | [Slides](https://speakerdeck.com/machty/emberconf-2014-mr-router-embraces-the-controller-alex-matchneer) | [Video](http://confreaks.com/videos/3309-emberconf2014-mr-router-embraces-the-controller)

Query parameters are still coming. The holdup is the missing primitive for state and the right defaults so that the behavior matches the most common use cases. There is a general state serialization that the controller will provide that can be targeted at query params or localStorage (or maybe something else like serializing the state to the server).

[Model del state demo](https://machty.s3.amazonaws.com/emberconf/fun.html)

## The Unofficial Ember Testing Guide


Eric Berry | [@coderberry](https://twitter.com/coderberry) | [Slides](https://speakerdeck.com/coderberry/the-unofficial-official-ember-testing-guide) | [Video](http://confreaks.com/videos/3310-emberconf2014-the-unofficial-official-ember-testing-guide)

* qunit is the happy path. but mocha and jasmine should be supported too.
* Ember.test provides helpers, Qunit provides assertions.

## Convergent Divergent Faits Precis

Chris Meiklejohn | [@cmeik](https://twitter.com/cmeik) | [chrisophermeiklejohn.com](http://christophermeiklejohn.com/) | [Slides](https://speakerdeck.com/cmeiklejohn/divergent) | [Video](http://confreaks.com/videos/3311-emberconf2014-convergent-divergent)

* Basho, Georgia Tech grad student, Podcast Think Distributed
* [Syncfree project](http://syncfree.lip6.fr)

* Distributed computing. That's what Ember Data is!
* Ricon 2013 conference put on by Basho on dist computing.

_When you push state to the client, that data is going to become stale._

* Strict linearizable, eventual consistency, causal consistency
* Safety vs liveness
* Consensus: termination, agreement, validity
* Two generals, byzantine generals
* Raft is a simplified Paxos
* Time clocks and the ordering of events in a distributed system, Leslie Lamport, 1973
* Dotted version vectors

* CFRDT: Conflict free replicated data types.
* _Avoid coordination. Want the system to make progress when clients are offline._
* Eventual consistency.
* PAPEC 2014

## Controlling Route Traversal With Flows

Nathan Hammond | [@nathanhammond](https://twitter.com/nathanhammond) | [Slides](https://www.dropbox.com/s/02peoxevqwjz1bu/Controlling%20Route%20Traversal.pdf) | [Video](http://confreaks.com/videos/3312-emberconf2014-controlling-route-traversal-with-flows)

Categories of URLs:

* Resources - Available at any point in time. Pluralized nouns if array controller or singular if object controller. Such as /accounts.
* Actions - REST API such as /login. Always contain a verb.
* Flows - Third type. Changing state across multiple routes. login -> otp. authenticate -> accounts

Directed graph with an attached state machine.

Designing a flow.

1. Router.map
2. List linear paths
3. Convert to a node graph (each node is a route)
4. Edge traversal
5. Figure out backwards traversal because users will hit the back button.
6. Done! (Except for the routes that you forgot.) The diagram will communicate the flow to everyone.

_[Google's libphonenumber](https://code.google.com/p/libphonenumber/) to recognize and format phone numbers!_

Change state and get route traversal for free. How did we do this?

* Naive approach on github (don't use).
* Tanget: replaceWith is awesome. Use it. Prevents pollution of the browser history. Alternative to transitionTo.

* An Improved Approach.
* Definitions of Edge Lists
* Get flow in beforeModel

* [Demo app](https://github.com/alexdiliberto/emberconf-2014-demo)
* [(Eventual) Github](https://github.com/nathanhammond/ember-flows)

## Snappy Means Happy
### Performance in Ember Apps

Matthew Beale | [@mixonic](https://twitter.com/mixonic) | [Slides](http://madhatted.com/2014/3/28/via-emberconf-performance-in-ember-apps) | [Video](http://confreaks.com/videos/3313-emberconf2014-snappy-means-happy-performance-in-ember-apps)

* [Developing an Ember.js Edge](https://gumroad.com/l/XlSx)
* [Client-side Auth with Ember.js (Slides)](http://www.slideshare.net/mixonic/client-side-auth-with-ember)

_Web performance is a bigger topic than just Ember performance._

How fast do we need to be?

* Jakob Nielsen: 100ms, 1 second, 10 seconds
* Ilya Grigorik: 100, 300, 1000, 1 second +, 10 seconds +
* 16ms for 60fps animation

Methodology:

1. gather facts
2. analyze and theorize
3. change a single thing
4. confirm theory

1. Reproduce mobile latency reliably - http://slowyapp.com/
2. Create a clean browser environment
3. Measurement and analysis. Create a clean browser environment
4. Solutions
  * script at bottom
  * script async/defer
5. Make changes

Recommend Ilya's Browser Networking book: [High Performance Browser Networking](http://chimera.labs.oreilly.com/books/1230000000545)

Janky animation

1. Understand how browsers work
2. Measure in the Timeline
  - How long does it take to get something on screen?
  - Open the Render Console in Timeline to get a special console.

Ember debugging a slow list obsever

1. Understanding observers
  - Observers are synchronous
  - .set() -> .setProperties() to coalesce
  - Ember.run.once to do the expensive thing once
2. Profiler in Dev Tools
  - Flame Chart

## Evolution Is Awesome

David Herman | [@littlecalculist](https://twitter.com/littlecalculist) | [Slides](https://speakerdeck.com/dherman/evolution-is-awesome) | [Video](http://confreaks.com/videos/3314-emberconf2014-keynote-evolution)

### Evolution versus Revolution

[Code Rush (Movie)](http://www.imdb.com/title/tt0499004/)

* Revolution is necessary for survival, but comes at great cost so use carefully.
* Evolution is necessary for progress, but can carry a lot of baggage forward.

_Choose wisely between evolution and revolution._

* "use strict"; // Opt-in to good behavior is the wrong approach.
* Modules automatically turn on "use strict";

### [Extensible Web](http://extensiblewebmanifesto.org/)

Need the primitives so that browser vendors and web developers can iterate rather than try and perfect a standard.
