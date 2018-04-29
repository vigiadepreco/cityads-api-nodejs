# Cityads API

[![npm package](https://nodei.co/npm/cityads-api.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/cityads-api/)

API integration with Cityads

## Install

```bash
$ npm install cityads-api
```

## Get Api Key

* Create account - https://cityads.com/main/en/start/webmasters/
* Client_id, Secret_key, Remote_auth - https://developers.cityads.com/api/dev/auth?lang=en

## Usage

```js
"use strict";

let Cityads = require("cityads-api"),
    cityads = new Cityads("Client_id", "Secret_key", "Remote_Auth");

//Get GEOID in https://cityads.com/api/dev/webmaster/lists?lang=en#GETgeo-list
cityads.programs(32, function(err, result){
    console.log(result);
});

//Create coupon filter in https://cityads.com/publisher/coupons
cityads.coupons("NDQ5NzY1NjE2", function(err, result){
    console.log(result);
});

cityads.report("statistics-rate", "event_time_day", "2016-10-01", "2016-11-18", function(err, result){
    console.log(result.data);
});

cityads.deeplink("https://www.amomuito.com/", 8065, (err, url) => {
    console.log(url);//http://cityadspix.com/click-DQFB8U6A-PNLJQTEF?url=https%3A%2F%2Fwww.amomuito.com%2F
});
```
