GIFPoint
========

Middleman, Angular-powered HTML slides that make it super easy to add full-screen GIFs.

Setup
-----

First, we need to install `bundler`, `bundle`, and then start the Middleman
server.

```bash
gem install bundler
bundle install
```

Next, we need to set up the project dependencies via Bower. If you don't have bower installed:

```bash
npm install -g bower
```

Install the dependencies:

```bash
bower install
```

Start the Middleman server:

```bash
middleman s
```

Go to `localhost:4567/#/` and you should see the first slide.

Set Page Title
--------------

To set the page title, open up `config.rg` and change the `page_title`.

Creating Slides
---------------

All of the slides are in `source/index.haml`. They are written as Angular
directives in Haml.

Here are some different slide types you can use:

### Basic Slide

```haml
/ Text
%slide
  .slide-content
    %h1 Slide Title

/ Title Slide
%slide.slide--title
  .slide-content
    %h1 Slide Title

/ Centered Text + Subtitle
%slide
  .slide-content
    .middle.tac
      %h1.mbxs Another Title
      %p This is a subtitle.

/ Image
%slide
  .slide-content
    .middle.tac
      = image_tag 'http://placehold.it/800x400', alt: 'Placeholder', class: 'slide-media'
```

### Colors

```haml
/ Light
%slide.slide--light
  .slide-content
    .middle.tac
      %h1 Light

/ Dark
%slide.slide--dark
  .slide-content
    .middle.tac
      %h1 Dark

/ Subdued
%slide.slide--subdue
  .slide-content
    .middle.tac
      %h1 Subdued

/ Success
%slide.slide--success
  .slide-content
    .middle.tac
      %h1 Success

/ Error
%slide.slide--error
  .slide-content
    .middle.tac
      %h1 Error

/ Warning
%slide.slide--warning
  .slide-content
    .middle.tac
      %h1 Warning
```

### Code

```haml
%slide.slide--light
  .slide-content
    .middle.middle--auto
      :code
        # lang: sass

        // Code goes here...
```

### Positioning


```haml
/ Middle
%slide
  .slide-content
    .middle
      %h1 Slide Title

/ Middle Center (text)
%slide
  .slide-content
    .middle.tac
      %h1 Slide Title

/ Bottom
%slide
  .slide-content
    .bottom
      %h1 Slide Title

/ Bottom Center
%slide
  .slide-content
    .bottom.tac
      %h1 Slide Title

/ Bottom Right
%slide
  .slide-content
    .bottom.right
      %h1 Slide Title
```

### Grids/Lists

```haml
%slide.slide--light
  .slide-content
    %h1.mbs List of Things
    .grid
      .grid-box.grid-box--1of2
        %ul
          %li One thing
          %li Here's another thing
          %li And another
      .grid-box.grid-box--1of2
        %ul
          %li Oh man! Another thing
          %li Here's another thing
          %li And, finally, another
```

### Longer Text

```haml
%slide
  .slide-content
    .bottom
      %p.tsxl
        What would happen if I put some longer, more thought-provoking
        text here that fills up more space?
```

### Quote

```haml
%slide
  .slide-content
    .bottom
      %blockquote.mbxs
        "What would happen if I put some longer, more thought-provoking
        text here that fills up more space?"
      %p &mdash; Drew Barontini
```

### Image Overlay

```haml
/ Basic
%slide.slide--fade(img='IMAGE_URL')
  .slide-content
    .middle.tac
      %h1.mbxs Slide Title
      %p This is standard slide.

/ Dark
%slide.slide--fade.slide--fade--dark(img='IMAGE_URL')
  .slide-content
    .middle.tac
      %h1.mbxs Slide Title
      %p This is standard slide.

/ Light
%slide.slide--fade.slide--fade--light(img='IMAGE_URL')
  .slide-content
    .middle.tac
      %h1.mbxs Slide Title
      %p This is standard slide.

/ Success
%slide.slide--fade.slide--fade--success(img='IMAGE_URL')
  .slide-content
    .middle.tac
      %h1.mbxs Slide Title
      %p This is standard slide.

/ Error
%slide.slide--fade.slide--fade--error(img='IMAGE_URL')
  .slide-content
    .middle.tac
      %h1.mbxs Slide Title
      %p This is standard slide.

/ Warning
%slide.slide--fade.slide--fade--warning(img='IMAGE_URL')
  .slide-content
    .middle.tac
      %h1.mbxs Slide Title
      %p This is standard slide.
```

### Full-screen GIF/Image

```haml
/ Contain
%slide.slide--contain(img='IMAGE_URL')

/ Fill
%slide(img='IMAGE_URL')

/ Inset
%slide.slide--inset(img='IMAGE_URL')

/ Tiled
%slide.slide--tile(img='IMAGE_URL')

/ Local
%slide(img="#{image_path('IMAGE_URL')}")
```

### Video (YouTube)

You can use the `%yt-video` directive to load a responsive YouTube video. Just add:

- The width
- The height
- The embed ID

```haml
%slide.slide--video
  .middle.tac
    .slide-video
      %yt-video(width="1280" height="720" video-src="xZY43QSx3Fk")
```

## Slide Transitions

- Use the `right arrow` or `spacebar` to move right.
- Use the `left arrow` to move left.
- Use `escape` to bring up the preview.

### Remove Transition From All Slides

`source/assets/stylesheets/foundation/_settings.sass`:
```sass
$slide-transition: false
```

### Remove Transition From a Single Slide

```haml
%slide.noTransition
  .slide-content
    .middle.tac
      %h1 Slide Title
```

