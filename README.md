Sketchocalypse
==============

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

