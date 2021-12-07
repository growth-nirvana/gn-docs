---
layout: default
title: Amplitude 
nav_order: 1 
has_children: true
has_toc: false
---

## Amplitude

Amplitude gives you the power to track what’s important to your experience. You can choose to track anything and everything.

In this guide, we’ll give a high level overview of how to correctly configure Amplitude so that Growth Nirvana can seamlessy connect purchase data in your system (first party data) to third party data coming from your advertising partners Facebook and Google (third party data).

## Growth Nirvana Prerequisites
These prerequisites below are the minimum for a successful Growth Nirvana implementation.
* Initialize the library with the correct options in order to track UTM parameters.
* Track the first visit of each user along with the Purchase/Conversion event.
* Identify the user when they are able to be identified with an id that is unique within your system. Most often the primary key in the Users table.
* Configure UTM parameters in your ad platforms

### Initialize
Depending on how you implement Amplitude, you may need to initialize Amplitude in your app. In some cases like Fresh Paint and Segment implementation is done within their application.

The example below shows how to initialize Amplitude in your app to make sure that Amplitude will track both the referrer and utm parameters. This example does not use Fresh Paint or Segment. Instructions on how to set up Amplitude is provided in the <a href="https://developers.amplitude.com/docs/javascript" target="_blank">Amplitude Setup Guide</a>[]()
```javascript
var opt_config = {
    includeReferrer: true,
    includeUtm: true
};

/* 
  Note: The amplitude variable is a global variable that is 
  set up in the Amplitude SDK when using the snippet. 
  Your app may vary if you are using a library via Webpack or other build tools.

  The second parameter is an optional user_id to identify the user. 
  If the user is present you can pass it, if not you can pass null as shown below.
*/
amplitude.getInstance().init(apiKey, null, opt_config);
```

A full list of the options that you can initialize Amplitude with is available in the <a href="https://amplitude.github.io/Amplitude-JavaScript/Options/" target="_blank">Amplitude Setup Guide</a>

### LogEvent Purchase || LogRevenue

The `logEvent` method is used to track events. The `logRevenue` method is used to track revenue.
The documenation for that is found here: <a href="https://developers.amplitude.com/docs/javascript#track-revenue" target="_blank">Tracking Revenue</a>.

### Identify
The example below shows how to identify a user and Amplitude documentation for that can be found here: <a href="https://developers.amplitude.com/docs/javascript#setting-multiple-user-properties" target="_blank">Identifying Users</a>.
```javascript
/* 
  Note: The amplitude variable is a global variable that is set up in 
  the Amplitude SDK when using the snippet. Your app may vary if you are 
  using a library via Webpack or other build tools.
*/

var userProperties = {
  user_id: '12345', // the user id is unique within your system
  email: 'email@email.com', // optional
}

// This is shorthand for the identify call and set call wrapped into one.
amplitude.getInstance().setUserProperties(userProperties);
```

## Google Ads
Growth Nirvana uses the utm_campaign and the utm_content for this connection.
In your ad platform you can set up the utm_campaign and utm_content parameters to send the id of the ad group and the id of the ad. This allows you to track the conversion event for each ad.

Documenation to set up UTM parameters in your ad platform is available here: <a href="https://support.google.com/google-ads/answer/6305348#zippy=%2Cfinal-url-tracking-template-or-custom-parameter%2Ctracking-template-only%2Cfinal-url-only%2Cshopping-campaigns-only%2Cvideo-campaigns-only%2Chotel-campaigns-only" target="_blank">Google Ads</a>
* UTM campaign
    * In the utm_campaign you should use the Value Attributes from in the Google Ads platform to add the ad group id, which can be reference using {adgroupid}. 
    * Example utm_campaign={adgroupid}
* UTM content 
    * should use the ad id which is available through the parameter {creative}
    * Example: utm_content={creative}
* After this is properly configured Amplitude and Growth Nirvana will automatically be able to connect your ad spend with conversion data coming from Amplitude for both first and last click attribution.

## Facebook Ads
URL parameters can help you understand the effectiveness of your ads. You can input your own custom URL parameters or you can use the dynamic URL parameters Facebook offers for your ads. Dynamic parameters are helpful because they provide an automated way to populate the values of your parameters based on information you provide when setting up your ad and information related to how your ads are delivered.
* UTM Campaign
    * Should use the adset id
    * Dynamic parameter {% raw %}{{adset.id}}{% endraw %}
* UTM Content
    * Should use the ad id
    * Dynamic parameter {% raw %}{{ad.id}}{% endraw %}

More documentation can be found here: <a href="https://www.facebook.com/business/help/2360940870872492" target="_blank">Facebook Ads</a>
