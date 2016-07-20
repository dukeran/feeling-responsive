---
#
# Use the widgets beneath and the content will be
# inserted automagically in the webpage. To make
# this work, you have to use › layout: frontpage
#
layout: frontpage
header:
  image_fullwidth: header_unsplash_12.jpg
widget1:
  title: "Code for Thought"
  url: 'http://dukeran.github.io/feeling-responsive/code/'
  image: widget-1-302x182.jpg
  text: 'Read how an inexperienced programmer began her journey into the world of Ruby on Rails and how she faced the many challenges of entering the tech world with no background experience.'
widget2:
  title: "Healthy Roots "
  url: 'http://dukeran.github.io/feeling-responsive/healthy-roots/'
  text: '<em>Healthy Roots</em> is a section which discusses how to eat healthier, live healthier, and overall exist healthier. We will explore any ideas - ranging from the most arcane to common sense!'
  video: '<a href="#" data-reveal-id="videoModal"><img src="http://phlow.github.io/feeling-responsive/images/start-video-feeling-responsive-302x182.jpg" width="302" height="182" alt=""/></a>'
widget3:
  title: "Download Theme"
  url: 'http://dukeran.github.io/feeling-responsive/literature-and-musings'
  image: widget-github-303x182.jpg
  text: 'A place for one and all to publish their works of art and their musings! Anything from short stories, poetry, to political commentary. A platform to launch your ideas.'
#
# Use the call for action to show a button on the frontpage
#
# To make internal links, just use a permalink like this
# url: /getting-started/
#
# To style the button in different colors, use no value
# to use the main color or success, alert or secondary.
# To change colors see sass/_01_settings_colors.scss
#
callforaction:
  url: https://tinyletter.com/feeling-responsive
  text: Inform me about new updates and features ›
  style: alert
permalink: /index.html
#
# This is a nasty hack to make the navigation highlight
# this page as active in the topbar navigation
#
homepage: true
---

<div id="videoModal" class="reveal-modal large" data-reveal="">
  <div class="flex-video widescreen vimeo" style="display: block;">
    <iframe width="1280" height="720" src="https://www.youtube.com/embed/3b5zCFSmVvU" frameborder="0" allowfullscreen></iframe>
  </div>
  <a class="close-reveal-modal">&#215;</a>
</div>
