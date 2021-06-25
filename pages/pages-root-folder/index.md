---
#
# Use the widgets beneath and the content will be
# inserted automagically in the webpage. To make
# this work, you have to use › layout: frontpage
#
layout: frontpage
header:
  image_fullwidth: header_home.jpg
widget1:
  title: "Tutorials"
  url: 'https://python-tutorials.nl/blog/'
  image: widget-1-302x182.jpg
  text: 'Here you can find all the tutorials about python'
widget2:
  title: "About"
  url: 'https://python-tutorials.nl/about/'
  text: 'About page'
#  image: About_Me.jpeg

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

permalink: /index.html
#
# This is a nasty hack to make the navigation highlight
# this page as active in the topbar navigation
#
homepage: true
---


