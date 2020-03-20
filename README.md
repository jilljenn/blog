# Un escargot à Manhattan

This is a rare specimen of Octopress blog in 2019 refreshed using Jekyll 3.8.6.

## Usage

    bundle install
    bundle exec rake generate

Will create the whole blog in a `public` folder that you can then push via rsync.

Here is the minimal list of plugins that you will need:

    category_generator.rb  # For the category links
    image_tag.rb  # {% img <link> %}
    youtube.rb  # {% youtube <link> %}

© 2011–2020 (see [this tweet](https://twitter.com/jjvie/status/1161999750071087104))
