# Proposal
When a site is in full screen, it will be permitted to request a system keyboard lock allowing it to override all keys as well as system-level shortcuts. Users exit the keyboard lock through an exit gesture, such as holding down the Escape key for 2 seconds.

## Requirements
* System keyboard lock is restricted to full screen and secure origins.
* The site will need to request system keyboard lock capabilities once in full screen, otherwise the request will be automatically denied.
* Sites and browsers can optionally add permission, consent or reminder UI to ensure users understand how to exit system keyboard lock mode.
* Once system keyboard lock is granted, the browser will disable the typical behavior of the system keys and shortcuts and make them available to the web site. Potential keys and shortcuts include:
  * Escape
  * Super (e.g., Windows key, ChromeOS search key)
  * Alt/Cmd+Tab
  * Alt+F4
  * Alt+Backtick
  * Prt Scn
  * Mouse 6 & 7
  * OS-hot corners
  
## Sample Code
__Requesting keyboard lock__
```javascript
document.requestSystemKeyboardLock();
document.addEventListener(‘keydown’, event => {
  event.preventDefault();
  game.toggleMenu();
}, false);
```

Note that preventDefault may not work for some system keys, particularly Alt+Tab on Windows. This is because the APIs for intercepting them require the handler to make a decision whether or not to pass the event to the next handler in the sequence or to consume it. If this depends on whether or not the JavaScript calls preventDefault, it may not be possible to make this decision.

__User experience__

1. Enter full-screen mode via some UI provided by the web-page.
2. Press the Escape key.
3. See the in-game menu open/close; the web-page remains full-screen.

__Monitoring keyboard lock__
```javascript
document.addEventListener(‘systemKeyboardLockChanged’, event => {
  if (event.systemKeyboardLockEnabled) {
    console.log(‘System keyboard lock enabled.’);
  } else {
    console.log(‘System keyboard lock enabled.’);
  }
}, false);
```
