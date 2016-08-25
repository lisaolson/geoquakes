# Lisa Olson - GeoQuakes Assignment

## Link to repo
    https://github.com/lisaolson/geoquakes
### Reflection

  I worked on this assignment with Zach and Jason.  It really helped working in a group on this assignment. I'm happy with the progress we made. We didn't quite finish, but we got at least 2 markers to show up on the map.  




<img src="https://cloud.githubusercontent.com/assets/7833470/10423298/ea833a68-7079-11e5-84f8-0a925ab96893.png" width="60">
#GeoQuakes Training

## Introduction

> ***Note:*** *This is a pair programming activity! You must work with a partner on this project! There are many pieces that could trip you up, so having two pairs of eyes and two brains on one set of code will be an important tactic to minimize errors and generate ideas.*

In this training, we attempt to put together much of the work from this week. We'll be using jQuery's `ajax()` function to make calls to a third party API.  We will be using live data from the USGS (United States Geological Survey), specifically a data set showing significant earthquakes (M4.0 or greater) from the past week.

## Objectives

Developers will be able to:
- Use AJAX to grab data from the USGS earthquakes API
- Create and compile a Handlebars template
- Use Handlebars templating to display data from an AJAX call on your HTML page
- Use the Google Maps API to embed a map

## GeoQuakes

#### Starter code

Get started with the code provided in `index.html` and `scripts/app.js`.

#### Deliverable

Our goal is to:
- List information about each quake.
- Display a Google Map with a pin at the epicenter of each quake.

Here's a screenshot of what the final product could look like:

![geoquakes](https://cloud.githubusercontent.com/assets/6520345/17942822/c6531b7c-69ed-11e6-9802-80bb3304a941.png)

If your partner forked the repository originally, you should fork their repository **after you finish working together** so that you'll have your own copy of your work to edit in the future. Link your own repo to your personal website.


## Instructions

#### Part 1. Rendering Data
Take a moment to familiarize yourself with the dataset by opening it in your browser: [http://earthquake.usgs.gov/earthquakes/feed/v1.0/summary/significant_week.geojson](http://earthquake.usgs.gov/earthquakes/feed/v1.0/summary/significant_week.geojson).

+ What is the structure of the data?
    + How many earthquakes does it list?
    + How would you grab the first earthquake?
        * How would you grab it's title?
        * How would you grab it's geological coordinates:
            - *latitude*?
            - *longitude*?
        * When did it happen?
            - How many hours ago is that?

Write out the AJAX call that will grab the data and `console.log` the list of earthquakes.

#### Part 2. Add the title data to the page using Handlebars templates

Now, take a moment to familiarize yourself with the layout in `index.html`.
- Your short term goal is to render each *title* to the `<div id="info">` of the page (see the commented example in your HTML)
  - write the Handlebars template in the html and give it a unique `id` and remember to `type` it correctly.
  - Compile the Handlebars template in your javascript.
  - In the AJAX success function:
    - pass the data into your `template()` function.
    - Append the html to the view.

Building up an html string in javascript is no fun and the rows in the `<div id="info">` would be unwieldy to build that way. Let's add a Handlebars template.

#### Part 3. Add Google Maps
- Your next goal is to integrate Google Maps:
    - Follow the tutorial at [Google Maps Javascript API](https://developers.google.com/maps/documentation/javascript/tutorial)
        + Note that you would normally need to sign up for an API key, but we've provided one (See `index.html` line 18)
        + Be VERY careful when you copy and paste code!
    - Please center your map on San Francisco: `{ lat: 37.78, lng: -122.44}`

#### Part 4. Add pins to your map
Once you've got the map to show up, your next goal is to drop a single pin on San Francisco. This is a sanity check.  
- Next, can you add only the first earthquake to the map?
- Can you add pins for *all* the earthquakes to the map?

#### Bonus:
Extend your template:  
- Calculate how long ago the quake occurred and add it to the page. E.g. "28 hours ago". Currently, the time that the API returns is in Unix time (seconds since 1/1/1970). That's a nice format for computers, but not a nice format for humans.
- Parse the title to only include the location, E.g. Instead of "M 4.2 - 1km ESE of Fontana, California", it should just say "Fontana, California."
- Create a visual indicator of the magnitude of a quake. For instance, maybe a 4.0 is indicated by a "yellow" dot, a 5.0 by an "orange" dot, and anything larger is "red".
