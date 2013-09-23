
## Legacy Clients

Paul Irish introduces panel.

#### Opening Speaker:

- Life used to be easy.
- Legacy clients.
- Then the iPhone came along. Followed by an avalanche of devices.
- The problem is agility VS. Robustness.
- Testing IE7/8 is hard, is it worth it?
- Now anyone can do web development. Easy to start, hard to scale up to a larger audience.
- We want Ubiquity, in other words, 'Browser support'.
- "It's the ubiquity of the web that wins"
- BBC decided to support everything.
- The responsive site has a 'Core Experience' and an 'Enhanced Experience'
- Browsers that don't 'cut the mustard' only get the core experience.
- With CSS preprocessors we can output a stylesheet at any breakpoint.
- Use conditional comments to serve this legacy stylesheet to old clients.
- Use a solid base of progressive enhancement as a springboard for JavaScript

#### Why is there be a stigma attached to supporting legacy clients?

- There is, but there shouldn't be.
- There are valid reasons to support old browsers
  - The user may not know how to update their browser.
  - The may use a proxy browsers.
  - Limited data plans.
- If you're a government website, these services are mandatory.
- Service like Gmail it's more acceptable to drop older browsers.
- What is support? Support may not be a binary decision.
- Sometimes sites blanket ban IE, even if it's IE10!
- IE6 stylesheet by Andy Clark can be used to take IE6 clients right back to a typography only layout.
- Sending a 'not supported' error message is the worst thing you can do.

#### What's the best way to make legacy clients a visible part of the development process?

- At the BBC, all design/development starts at the 'Core Experience'

#### Is there a way to communicate to the user that they are on a degraded version, will the be confused if they see both experiences?

- As long as they are getting the content it is ok.
- There is not much we can do.

#### What can we do as a community to convert IT departments to upgrade?

- IE6 lost 0.5% in the 6 months on gov.uk
- At weekend IE6 is not really there.
- Everyone is trying to get out of these old legacy clients.

#### Is it worth spending the effort supporting old clients when if it can impact developer retention?

- Google apps dropped support for IE8.
- Google has a policy of supporting the latest and latest - 1 browser.
- Argue before signing the contract that older browsers won't be supported.
- Clients are becoming more interested in supporting modern devices than old browsers.

#### There are people who are consciously not updating because they are scared of change.

- Browser vendors should make this transition as easy as possible.

#### IE8 on XP, iOS6 on iPhone 3 will stick around because they are great products that cannot upgrade.

- Support for Windows XP will be dropping in April 2014
- Windows made the decision to drop support for their old users. Alex Russell supported for them by developing Chrome Frame.

#### For how long is it worth polyfilling for old browsers, taking into account the performance cost?

- Increased bytes and work at runtime.
- If a users doesn't have support for CSS animations then don't fallback to JS animations, just don't give them the animation.
- Sometimes CSS animations can look good on one browser and not others.
- Sometimes you can have cheap devices running modern version of Android. Environment looks good from the perspective of the browser, but can be very different in practice.
- Some feature you will never be able to degrade gracefully (WebGL, getUserMedia, ...)
- Don't always try to polyfil features like or like.

#### Content websites should always work without JS, but should JS heavy applications? (John Resig)

- Some apps cannot be done without JavaScript.
- Any website that has a loading bar is missing the opportunity to show the content first, JavaScript should upgrade the experience.
- Sometimes even when a device can support JS, it's best to give them the non-JS experience.
- A lot of progressive enhancement is idealistic. It is often hard to argue the case of one to your product manager. But when they are all put together you are 'swimming with the web', you get a lot of gain for free.
- 98.4% of screen reader users have JS enabled.