# Responsive Images

John Mellor (Google) introduces.

### Introduction

- Yoav Weise
- Mid 2000 mobile only sites (lame)
- Responsive web design came along, it was cool. All device through a single site. But this was slow. This is because most site serve same resources for all devices (mobile to desktop). Images account for a lot of this page weight.
- Up to 72% of image data can be saved when serving to smaller viewports. Retina makes this even worse.
- Most devs own retina devices and want their work to look good on these devices. Therefore most website are serving very large images to all type of device.
- DPR switching (serving retina images to retina devices)
- ‘Viewport Switching’ serving the correct size image for the viewport.
- This has been proven to be a major use case.
- Solutions:
  - srcset - Covers the resolution switching case. Includes multiple sources defining device requirements for each src.
  - <picture> - Targeted at art directions. Many sources. First matching resource is downloaded and displayed. Can be used in combination with `srcset`. Media attrs should match layout breakpoints.
  - Client hints  - CLient sends out its capabilities to the server. Server uses hints to decide which assets to send down to the client. Opt-in only.
  - Responsive image container - Uses layers to enhance image quality for different devices and situations. The browser downloads diffs. But: complicated to implement. Decode perf.
  - (John Mellor takes mic) - Parallel image loading of progressive jpegs, gives the user content quickly at a lower quality.

**First question:** Do I even need all these different sizes of image when I can compress the hell out of a @2x image and get an acceptable file size?

- Scrolling and paints could get heavier and the browser is using more memory to downsize the large images. Performance is the main issue.
- Peter MIller: He’s looked at the solution. May be subjective opinion as to whther these heavily compressed images look at good.
- Androids and FireFox OS have much lower memory, may struggle.

**Second Question:** Would it make sense in the future to just send hight-res images to all users?

- Would be nice if we could, but we can’t do this yet.
- Browser should download only what it needs.
- We’re never going to be able to have just one image solution.
- Art direction means that we will need multiple iamges.

**Audience question:** Should new image formats solve the pitfalls of older formats like jpeg?

- You can afford higher compression as new images formats (like webp) don’t show the same obvious artifacts that you can see from jpeg.
- WebP does not have progressive loading. That is an issue for Mozilla.

**Third Question (Kyle Simpson):** Should we be able to respond to more complex situations that just screen size. For example if a device has very low battery, should we be able to make the decision to not download large images?

- This type of decision should probably be decided by the browser and not the web developer.

Fourth Question (Calvin Spealman): Are we fighting a losing battle. Creating all these different images formats is only going to get more complicated as device market fragments even further.

- The most elegant solution is to give the server one super high-res image that is used to provide the client with a suitable size.
- Browser/ISP should not be making the decisions.
- Use client hints to allow the server to decide.
- Is it not easier for the browser to make these decisions? The browser knows a lot more than the server.
- Developers should not be making image sets manually.

Audience question: How will edge caches cope with this. Can we still use CDNs?

-

**Fifth Question (Peter Miller):** What about the art direction case?

Sixth Question (Jeffrey Zeldman): Are these new declarative image solutions polluting our markup. Where is the separation of content and presentation?
- The ‘Clown Car’ technique separates content from presentation
- Screen size does always correlate with image size. At larger screens multiple columns can actually shrink image display size down.
- Create @media query variables. Use them to keep things DRY. Should solve separation of concerns. Used via  `media` attribute.
- Clown Car technique emulates Element Media Queries via SVG.
- Still a fan of progressive jpegs (audience laughs).

**Audience Question:** What is best practice right now?

- Sending jpeg sources into the html at a json string on a attribute.
- Default low-res source
- We have a bunch of hacks right now.
- All current hacks have performance trade offs. Deferring the image loading to a later time.
- <x-picture> component to emulate <picture> element.
- Future hacks will get better.
- Look forward to `srcset`.
- Just make sure you’re not sending huge assets to limited devices.
- CSS use media queries to swithc out the right image.
- For html: Double size highly compressed image is responsible.
  - Load very low-quality placeholder. Then later with JS switch this out with an appropriate sized image. There is a library http://github.com.johnmellor/respswap.
  - ‘Picture Fill’ - Stop gap before <picture> element is ready.
- Could send a fake ‘DomContenLoaded’ event to speed up things.




