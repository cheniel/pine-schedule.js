# pine-schedule.js
Pine Schedule is a schedule widget built on [D3.js](http://d3js.org/) originally built for the [HackDartmouth website](https://github.com/hackdartmouth/hackdartmouth.github.io).


## Why?
- It looks nice and is easy to set-up.
- Requires very little modification in the event of a schedule change.
- Produces HTML output which is simple to style and customize.


## Usage
1. [Download pine-schedule.js](https://raw.githubusercontent.com/cheniel/pine-schedule.js/master/pine-schedule.js)
2. Create an div to place the schedule in
3. Load [D3.js](http://d3js.org/) and pine-schedule.js
4. Specify the appearance and contents of the schedule in a script which uses pine-schedule.js.


**index.html**

```html
<div id="pine-schedule" style="width: 500px; border: solid black 1px; padding: 10px;"></div>
<script src="https://cdnjs.cloudflare.com/ajax/libs/d3/3.5.6/d3.min.js" charset="utf-8"></script>
<script src="pine-schedule.js" charset="utf-8"></script>
<script src="main.js" charset="utf-8"></script>
```

**main.js**

All times are specified in military time using a float, e.g. 9.5 is 9:30 am and 14.0 is 2:00 pm.
```js
PineSchedule.load("#pine-schedule", {
  "day_of_week": "SATURDAY",            // for header display
  "month": "OCT",                       // for header display
  "day": 3,                             // for header display
  "range": {                            // start and end times of schedule
    "start": 9.0, 
    "end": 23.0
  },
  "events": [
    {
      "time_range": "10-11am",          // used for event display
      "name": "REGISTRATION",           // used for event display
      "location": "Cook Auditorium",    // used for event display
      "color": "#8BB9B6",               // background color for event
      "start": 10.0,
      "end": 11.0
    },
    // ... more events
  ]
});
```


## Optional specifications
You may further customize the apperance by adding an additional "optionals" object. Here is an example which reflects what HackDartmouth uses:
```js
PineSchedule.load("#pine-schedule", {
  "optionals": {
    "borders": true,                               // default is false
    "background_color": "#FFFFFF"                  // default is undefined (transparent) 
    "header_alignment": "center"                   // default is "right"
    "header_font_size": "25px"                     // default
    "header_font": "Verdana, Geneva, sans-serif"   // default
    "show_grid_on_event": false                    // default
  },
  // ... remaining specifications
});
```

## Thanks
[kathydong](https://github.com/kathydong) for the design, [HackDartmouth](https://github.com/hackdartmouth) for the motivation.
