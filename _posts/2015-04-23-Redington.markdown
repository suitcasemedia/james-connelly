---
title:  Massive bright pink squiggle of oil paint
subtitle: Branding for financial consultants
author: "Jimmy"
avatar: "img/authors/jimmy.svg"
image: "img/Redington.svg"
date:   2015-04-23 12:12:12
---


### Live URL: <a href="https://redington-mini-project-remix.glitch.me/" target="_blank" >https://redington-mini-project-remix.glitch.me/</a>


### Code: <a href="https://glitch.com/edit/#!/redington-mini-project-remix?path=src/components/Header.js:2:43">https://glitch.com/edit/#!/redington-mini-project-remix?path=src/components/Header.js:2:43</a>
The company has probably the most audacious mission statement I have ever seen: "BRINGING FINANCIAL SECURITY TO 100 MILLION PEOPLE...". Their new visual language in the rebrand reflects the boldness of their mission statment.
The central motif is a huge virtuoso  bright pink spontaniously  brushed squiggle of thick oil paint. Its on the front of the website, the walls of the office and on all their print materials. It communicates a raw passion which is really refreshing to see unashamedly on display in the branding of a leading company in the financial sector. 

### Rolling out the new brand to the dev team

The lead developer told me they are now thinking of ways to use front end development techniques to bring the new brand to their in house data driven reporting tools which were increasingly being shared with customers. Continuity is really important.

One of the lead developers told me they use <a href="https://tleunen.github.io/react-mdl/"  target="blank"> React Material Design</a> or <a href="https://material.io/components/web/">something similar</a> which saves them a lot of work but were open to the idea of developing their own UI kit.

One of my ideas is to add the bright pink paint texture to the typography in pages headings.
There are 2 ways to do this.
1. Displaying the pink squiggle in an 'img' element and giving the image a CSS class with  <a hred="https://developer.mozilla.org/en-US/docs/Web/CSS/clip-path" target="blank">clip-path property</a> - that links to an SVG clip path
2. Embeding the pink squiggle image in an SVG and reference the <a href="https://developer.mozilla.org/en-US/docs/Web/SVG/Element/clipPath">SVG clipPath element </a>defined in the same SVG.

I chose the latter as it is more widely supported in current browsers.

As a front end developer it is important to make elements reusable and consistent. Its also important to make design features easy to implement for developers who prefer writing backend code.

I built a react component that generates the SVG and takes the title text as a 'prop' parameter and renders the title inside a 'text' elent which is inturn nested inside the 'clipPath' element and referenced by the embeded image. The completed SVG with the embeded image and clipPath text is embeded on the page automatically. 

I used to find clipPath masks  confusing because  I always thought of a mask as a thing that covers something else up. What an SVG clipPath actually does is kind of the opposite. When I add link a clipPath to an element the clipPath covers the whole element EXECPT for the area covered by the clipPath inner area. So if I create an SVG image with the pink squiggle embeded in it - then I define a clipPath property containing  'text' element saying 'Your Summary' then all of the image will be hidden except for the parts that are covered by the text saying 'Your Summary' because that is the clipPath area.

I've created a react component that will render comments about the data to the right hand side of the page.
