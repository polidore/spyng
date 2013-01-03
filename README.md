# Spyng

Spyng (pronounced sping) is an AngularJS module that helps you create data for usability analysis.

# Design

This will be an angular directie that you can apply to most elements.  You will get callbacks for various behaviors on these elements like click, mouse over, etc.  

## Markup

Call back on your event handler whenever someone clicks a specific button

```html
<button spyng='event=click; name=submit'/>
```

Use some defaults.  Here you'll be called back with a name of mainSubmit on click

```html
<button id="mainSubmit" spyng=''/>
```

Callback on a mouseover with the duration

```html
<div id="importantPlace" spyng='event=mouseover'/>
```

## Code

```javascript
angular.module('yourApp',['$spyngProvider'], function($spyngProvider) {
  $spyngProvider.context({
    appName: 'My App',
    userId: yourAppsContext.username
  });
  $spyngProvider.spy(function(secret) {
    persister.save({
      timeStamp: secret.timeStamp,
      appName: secret.context.appName,
      userId: secret.context.userId,
      eventType: secret.eventType,
      eventId: secret.eventId
    });
  });
});

```
