# Parkinson's And Me Retrospective

## What?

This repo is an attempt to record the useful bits of information and learning from working with Parkinson's UK on the [`Parkinson's and Me`](https://github.com/cast-fuse/parkinsons-and-me) service.

## Why?

The [main repo](https://github.com/cast-fuse/parkinsons-and-me) is a useful resource when looking at the project as a whole but it's difficult to get an idea of the specific challenges we faced when building the project and working with the charity. We hope to record some of these challenges and our thoughts on them so they may be of use to other developers or people working in tech that are working with charities.


### The Project

![screen shot 2017-05-11 at 12 18 22](https://cloud.githubusercontent.com/assets/14013616/25946647/0526af6c-3644-11e7-96b4-ba6b44cea79d.png)

Parkinson's UK's main problem was that people newly diagnosed with Parkinson's were being overwhelmed by the amount of information available to them. The [fuse](http://www.wearecast.org.uk/fuse) product team worked with Parkinson's UK to come up with an idea for a web app that would guide a user through a series of `quotes`:

![screen shot 2017-05-11 at 12 26 28](https://cloud.githubusercontent.com/assets/14013616/25946935/1d72e602-3645-11e7-888a-2b411c1a2cdf.png)

The user would answer either "Yes, this sounds like me" or "No, this doesn't sound like me". After answering all the quotes the user would then be shown a list of services that were most relevant to them. These could either be revisited by a unique url or sent to the user via email.

![screen shot 2017-05-11 at 12 29 10](https://cloud.githubusercontent.com/assets/14013616/25947008/7b18f3e6-3645-11e7-99b5-0b999ecf4572.png)


## The Challenges

### Time and Tech

The [Fuse Programe](http://www.wearecast.org.uk/fuse) is a fast paced 3 months where a charity really gets to grips with building a product using agile processes. In month two of us ([Andrew MacMurray](https://github.com/andrewMacmurray) and [Ivan Gonzalez](https://github.com/ivanmauricio)) were tasked with building a prototype of the service so it could be tested with users and iterated upon.

> We needed to act fast and be able to respond to change fast.

Based on these requirements we decided to use some technologies that were new to us and relatively new in web development:

+ `elm` - for rendering the user UI
+ `tachyons` - a css methodology / framework
+ `elixir / phoenix` - for the backend

#### Elixir & Phoenix

Working with Phoenix and Elixir was a revelation for us. Neither of us had used the language before let alone the framework. This meant a bit of trepidation going into the project. However we had heard so many positives about these technologies that we decided to put our faith in them. This really paid off!

One of the first things we noticed was how easy it was to get up and running with Phoenix. After a few simple commands we had the skeleton for a fully functioning app. This theme continued throughout the project. As when learning any new technology - there were moments where we realised that we had no idea how to build the feature we were after. Phoenix to the rescue! There were commands for generating the database models and migrations and the RESTful API we needed. Inserting mock data for testing purposes turned out to have an out of the box solution too.

Originally we planned to build just the user facing interface. We thought that we would have no time to build an admin interface, even though we knew this would be useful. We knew that the scoring system for generating the results was going to go through a lot of change as it had never been tested. We had resigned ourselves to inputting these changes in ourselves even though we knew this would be time consuming. We quickly realised however how easy it would be to set up this admin interface thanks to Phoenix. It was a breeze to build a fully functioning, authenticated admin dashboard where all the data that being used by the user facing app could be deleted, modified and added to. This made for a very happy Product Owner and meant that we had more time to solve higher level problems.

In summary, Phoenix turned out to be a great choice! It was thanks to this great framework that we were able to get a lot done in a short amount of time, in fact we accomplished a lot more than we would have known if we had used technologies we already knew. It handled all the lower level problems leaving us to get on with the fun stuff! This along with amazing documentation, lots of common sense conventions and an awesome community made for very happy developers!

#### Elm

Needing to be able to respond to change fast was our main motivation for using Elm for our rendering layer. We had read a few `NoRedInk` blogs that mentioned that they had had no runtime exceptions for a year. Being used to JavaScript and the dreaded `object is undefined` we thought this claim to good to be true and were eager to test it out.

We soon came to love the safety that Elm provided. Elm's compiler became our new best friend, the best coding assistant we could hope for. Coding becomes like playing with Lego, you get immediate feedback of whether a piece (read function) you are trying to plug in somewhere fits or doesn't fit. When you are not quite sure how to wire something up you can really on types to give you a helping hand.

All of this meant that as the aims of the app changed throughout the project, it was easy to us to rip the old out and put the new in with the knowledge that everything would not break. When the inevitable changes to our data structure came, we were guided around the app by the compiler with helpful messages showing us the parts that needed modifying. Having felt the pain of refactoring apps in JS before, with all the accompanying breaking changes, we were delighted with the freedom that our new toy gave us!

Elm has turned out to be a great tool for agile development, for getting robust prototypes out the door rapidly, ready to go out into the big bad world of user testing.

#### Tachyons

The last part of our functional trifecta was Tachyons. This choice was again driven by the necessity to respond to change fast.

A recurring pattern in this project was ever changing designs. By the the time we finished we had gone through 4 or 5 different layouts. Using Tachyons we saved ourselves time and pain. In previous projects CSS files always found a way to become unwieldy in no time at all. Once more the accumulation of junk code became inevitable. Custom classes written for previous iterations cluttered the codebase, it becomes too much effort to check whether they are being used and taking them out without this reassurance is too risky.

Embracing the functional CSS methodology left us with less than 100 lines of custom CSS. Going through different iterations meant that the styling was ripped out along with the HTML, meaning no unused code. 
