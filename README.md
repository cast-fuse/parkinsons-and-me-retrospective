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
