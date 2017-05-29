# Parkinson's And Me Retrospective

### What?

This repo is an attempt to record the useful bits of information and learning from working with Parkinson's UK on the [`Parkinson's and Me`](https://github.com/cast-fuse/parkinsons-and-me) service.

### Why?

The [main repo](https://github.com/cast-fuse/parkinsons-and-me) is a useful resource when looking at the project as a whole but it's difficult to get an idea of the specific challenges we faced when building the project and working with the charity. We hope to record some of these challenges and our thoughts on them so they may be of use to other developers or people working in tech that are working with charities.


## The Project

![screen shot 2017-05-11 at 12 18 22](https://cloud.githubusercontent.com/assets/14013616/25946647/0526af6c-3644-11e7-96b4-ba6b44cea79d.png)

Parkinson's UK's main problem was that people newly diagnosed with Parkinson's were being overwhelmed by the amount of information available to them. The [fuse](http://www.wearecast.org.uk/fuse) product team worked with Parkinson's UK to come up with an idea for a web app that would guide a user through a series of `quotes`:

![screen shot 2017-05-11 at 12 26 28](https://cloud.githubusercontent.com/assets/14013616/25946935/1d72e602-3645-11e7-888a-2b411c1a2cdf.png)

The user would answer either "Yes, this sounds like me" or "No, this doesn't sound like me". After answering all the quotes the user would then be shown a list of services that were most relevant to them. These could either be revisited by a unique url or sent to the user via email.

![screen shot 2017-05-11 at 12 29 10](https://cloud.githubusercontent.com/assets/14013616/25947008/7b18f3e6-3645-11e7-99b5-0b999ecf4572.png)


## The Challenges

### Technology

The [Fuse Programe](http://www.wearecast.org.uk/fuse) is a fast paced 3 months where a charity really gets to grips with building a product using agile processes. In month 3, two of us ([Andrew MacMurray](https://github.com/andrewMacmurray) and [Ivan Gonzalez](https://github.com/ivanmauricio)) were tasked with building a prototype of the service so it could be tested with users and iterated upon. Our main requirements were:

+ we needed to build things fast
+ we needed to be able to change things fast
+ user feedback and data was the most important out come at this stage

We picked some technologies that we thought would help us with these:

+ [elixir](https://elixir-lang.org/) / [phoenix](http://phoenixframework.org/) - for the backend
+ [elm](elm-lang.org) - for the UI


### Elixir & Phoenix

> [Elixir](https://elixir-lang.org/) - "a dynamic, functional language designed for building scalable and maintainable applications."

> [Phoenix](http://phoenixframework.org/) - "A productive web framework that
does not compromise speed and maintainability."

Elixir and Phoenix were both new to us. Previously we'd only had experience with a few `node.js` frameworks, so we were taking a risk using a new language and framework. We'd heard good things from the community of developers we were working around and we were up for a challenge.

It was a risk worth taking as we became significantly more productive in a couple of days of learning than we'd been with several months of using node frameworks.

### Pros

+ very quick to get a project up and running
+ fantastic documentation
+ code generators allow learning and productivity
+ developer experience is top notch

### Cons

+ Not that many elixir developers out there yet (might be difficult to find developers to maintain the project)
+ learning a new language and framework was a little intense!

Whilst the scarcity of elixir developers could be a problem, we felt that the productivity boost outweighed the cost and given the context of the project the data gathered would most likely be used to build an internal version of the project for Parkinson's UK that fits with their existing software architecture.

Because of the productivity boost we will most likely use these technologies on fuse again.

### Elm

> Elm - "A delightful language for reliable webapps.
Generate JavaScript with great performance and no runtime exceptions."

Elm is a typed pure functional language used for building user interfaces. We'd built a small project in elm before and really enjoyed using it.

One of the biggest draws for using elm on the Parkinson's UK project was elm's type system. When refactoring, elm's compiler highlights the mistakes you've made and suggests corrections - this was extremely helpful when we needed to react to change quickly.

### Pros

+ Fantastic documentation
+ Extremely helpful error messages
+ Easy to refactor
+ It never crashes

### Cons

+ elm developers rare (arguably more so than elixir developers)
+ false sense of security with types (a reminder that tests are important!)

we managed to introduce a very subtle bug in our logic that we didn't spot for a while, this was a reminder that even though you don't need tests that functions will handle the correct type of arguments you still need to validate your logic works properly.

We would definitely use elm again on another project but only if the UI was complex enough to need it.

### Managing the Project

We organised the project by adding each of the user stories as github issues, making technical issues from each and deciding on a two week sprint based on how long we thought each issue would take. We had a daily standup via google hangouts with our product owner where we would all feed back on where the project was up to.

This was very productive at first, we had the project on continuous deployment so the product owner could see the current state of the project and the three of us worked well as a team.

We ran into problems as gradually more and more Parkinson's UK stakeholders got involved with the project. The copy and designs for the app were delayed many times by 'sign off', to the point where we only had the content that would make the app work (i.e. the links to the Parkinson's UK services) on the second to last day of the project.

This was a mistake on our part, we took what we thought was the spirit of agile development (reacting to change quickly and in small steps) and forgot to set clear deadlines on when content should be ready.

Another mistake we made was not to loop in the wider fuse team every day where the project was up to (we were updating our team weekly). Members of the team most likely would have spotted the problems we were facing earlier and intervened.

### Successes

+ Daily standups via Google hangouts (very useful)
+ Github issues worked well
+ Continuous deployment great for spotting problems / bugs

### Mistakes

+ Not setting clear content deadlines
+ Not communicating with the rest of the fuse team regularly
