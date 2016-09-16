# hexo-theme-kunkka

A simple, responsive theme ported from Wordpress by [iMuFeng](https://github.com/iMuFeng).
Repo of wordpress version: [Kunkka](https://github.com/iMuFeng/kunkka)(Already deleted). You can visit [his site](https://mufeng.me/) to see what this theme looks like.

## Installation
In your hexo directory, execute:

```Bash
git clone https://github.com/unnamed42/hexo-theme-kunkka themes/kunkka
npm install hexo-renderer-ejs hexo-renderer-stylus --save
```

Then modify `theme` entry in the global `_config.yml`.
```yaml
theme: kunkka
```

Then regenerate your blog:
```bash
hexo clean && hexo g
```
## Notice

Currently all css designs are based on html generated by `hexo-renderer-markdown-it`. If you use the default `hexo-renderer-marked`, the styles may break.

## Configuration

```yaml
keywords: 

since: 

nav:
  - title: 归档
    url: archives/index.html
    icon: fa-archive
    description: 
  - title: 关于
    url: about/index.html
    icon: fa-user
    description: 

notice:
  - "**Notice** one"
  - "~~Notice~~ two"

global_navigation: true

sidebar: true

duoshuo_shortname:

# Register at https://disqus.com/api/applications to get disqus_api_key
# Use the API Key, not the API Secret
disqus_shortname: 
disqus_api_key: 

search: true

busuanzi: true

tag_number: 25
full_content: false

# Provided colors: red, green, blue, purple
color_theme: blue

cdn: 
placeholder: 

mathjax: true

# Available: by | by-nc | by-nc-nd | by-nc-sa | by-nd | by-sa | zero | publicdomain
creative_commons: by-sa

sns: 
  github: 
  twitter:
  facebook:
  linkedin:
  googleplus_id: 
  steam_id:
  weibo:
  zhihu: 
  tieba: 

buttons:
  base: true
  border: false
  borderless: false
  raised: false
  3d: false
  glowing: false
  dropdown: false
  group: false
  wrapper: false
  shadow: false

links:
  - title: Friend1
    url: https://www.friend1.com
    description: My only friend
```
+ **keywords** - Keywords to sum up your site, should be delimited by comma. It will help search engines better find your site.
+ **since** - Year when your site established. Used for footer license message generation.
+ **nav** - Add extra entries to your navbar. `url` should be a relative link, and `icon` must exist in [FontAwesome](http://fontawesome.io/icons/).
+ **notice** - Add a global notice bar to your blog, one string per line, and you can use markdown syntax. If you don't want any notices, just leave it empty.
+ **global_navigation** - Must be `true` if you don't want your navbar gone.
+ **sidebar** - Set to false to disable sidebar.
+ **duoshuo_shortname** - [Duoshuo](http://duoshuo.com/) shortname of yours.
+ **disqus_shortname** - [Disqus](https://disqus.com/) shortname of yours.
+ **disqus_api_key** - Disqus API Key of yours, you need to [register](https://disqus.com/api/applications/register/) to get it. To use the recent posts widget for disqus, this entry must be set.
+ **search** - [A jQuery-based Local Search Engine for Hexo](http://hahack.com/codes/local-search-engine-for-hexo/). **Requires `hexo-generator-search` installed**.
+ **busuanzi** - Enable the [busuanzi](http://busuanzi.ibruce.info/) visit count when set to `true`.
+ **tag_number** - Set the maximum number of tags displayed in navigation area.
+ **full_content** - Display the whole post content in preview page when set to `true`.
+ **color_theme** - Determines the color of nearly all anchors. If empty, will use a default color instead.
+ **cdn** - cdn of your own. It's a global setting.
+ **placeholder** - The default thumbnail image of a post, set to empty if you don't want this.
+ **mathjax** - Enables [MathJax](https://www.mathjax.org/) support.
+ **creative_commons** - The Creative Commons icon. When disabled, the footer license will be copyright. 
+ **sns** - SNS links. Fill in your personal informations and you will see the links inside the footer. Currently, you can not add extra entries.
+ **buttons** - Some beautiful [button styles](http://www.bootcss.com/p/buttons/). For each entry, set to `true` if you want the corresponding style, but `base` should be enabled to use them. For any problems about usage, please visit their site [this](http://www.bootcss.com/p/buttons/) or [this](https://github.com/alexwolfe/Buttons/).
+ **links** - Links to your friends.

## Features

#### SNS Label

Syntax:
```plain
{% sns [icon] [text] [url] %}
```
`icon` must exist in [FontAwesome](http://fontawesome.io/icons/). The third argument `url` is optional, it will make the whole element clickable.

You can use this in your posts and pages.

#### Search page

We have an isolated page for displaying search results. Our search engine is [A jQuery-based Local Search Engine for Hexo](http://hahack.com/codes/local-search-engine-for-hexo/). To use this, install dependency first:

```bash
npm install hexo-generator-search --save
```

then set `search` in theme config to true.

#### Footnote

To use footnote, you have to switch your markdown renderer to `hexo-renderer-markdown-it`, and enable the `markdown-it-footnote` plugin first.

We have made a special style for footnotes, just for you to enjoy.

#### Separated widgets

HTML contents of widgets are generated inside `[path_to_site]/public/componets` folder, especially the `recent_posts` widget. They're loaded dynamically using jQuery. Thanks to this, there's no need to generate all posts over and over on single post modification.
