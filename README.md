# HEIG-VD Software Engineering blog

This blog is all about knowledge sharing and exposure of the heig-vd software engineering team projects, efforts and improvements.

## People we want to share with

As a blog is about creating posts, we address those to engineers, technical advisor, professors and more. To not forget how we share: "Minimum Interface, Content First, Maximum knowledge shared".

For that, we used the [Hydeout](https://github.com/fongandrew/hydeout) theme, an updated version of the [Hyde](https://github.com/poole/hyde) theme for [Jekyll](http://jekyllrb.com) 3.x and 4.x. It adds new functionality and is maintained.

![Desktop](/_screenshots/1.png?raw=true)
<img alt="Mobile home page" src="/_screenshots/2.png?raw=true" width="300px" />
<img alt="Mobile post page" src="/_screenshots/3.png?raw=true" width="300px" />

## Installation

Hydeout is available as the `jekyll-theme-hydeout` Ruby Gem.
Add `gem "jekyll-theme-hydeout", "~> 4.1"` to your Gemfile and run
`bundle install`.

If you're installing on Github pages, you may also have to add
`remote_theme: fongandrew/hydeout` to your `_config.yml`. [See the Github
instructions for more details.](https://help.github.com/articles/adding-a-jekyll-theme-to-your-github-pages-site/)

## Jekyll-paginate-v2

In order to paginate other pages than the blog page, we need to replace the `jekyll-paginate` plugin by a new one: [jekyll-paginate-v2](https://github.com/sverrirs/jekyll-paginate-v2).

As we already added the `gem "jekyll-paginate-v2", "~> 3.0"` to the Gemfile, the `bundle install` command should install it. If necessary, run:

```
gem install jekyll-paginate-v2
```

The `_config.yml` and the pages are already configured too, but you can find informations [here](https://github.com/sverrirs/jekyll-paginate-v2/blob/master/README-GENERATOR.md#site-configuration).

## Keep It Simple

In keeping with the original Hyde theme, Hydeout aims to keep the overall
design lightweight and plugin-free. JavaScript is currently limited only
to Disqus and Google Analytics (and is only loaded if you provide configuration
variables).

Hydeout makes heavy use of Flexbox in its CSS. If Flexbox is not available,
the CSS degrades into a single column layout.

## Customization

Hydeout replaces Hyde's class-based theming with the use
of the following SASS variables:

```scss
$sidebar-bg-color: #202020 !default;
$sidebar-fg-color: white !default;
$sidebar-sticky: true !default;
$layout-reverse: false !default;
$link-color: #268bd2 !default;
```

To override these variables, create your own `assets/css/main.scss` file.
Define your own variables, then import in Hydeout's SCSS, like so:

```scss
---
# Jekyll needs front matter for SCSS files
---

$sidebar-bg-color: #ac4142;
$link-color: #ac4142;
$sidebar-sticky: false;
@import "hydeout";
```

See the [_variables](_sass/hydeout/_variables.scss) file for other variables
you can override.

You can see the full set of partials you can replace in the
[`_includes`](_includes) folder, but there are a few worth noting:

* `_includes/copyright.html` - Insert your own copyright here.

* `_includes/custom-head.html` - Insert custom head tags (e.g. to load your
  own stylesheets)

* `_includes/custom-foot.html` - Insert custom elements at the end of the
  body (e.g. for custom JS)

* `_includes/custom-nav-links.html` - Additional nav links to insert at the
  end of the list of links in the sidebar.

  Pro-tip: The `nav`s in the sidebar are flexboxes. Use the `order` property
  to order your links.

* `_includes/custom-icon-links.html`- Additional icon links to insert at the
  end of the icon links at the bottom of the sidebar. You can use the `order`
  property to re-order.

* `_includes/favicons.html` - Replace references to `favicon.ico` and
  `favicon.png` with your own favicons references.

* `_includes/font-includes.html` - The Abril Fatface font used for the site
  title is loaded here. If you're overriding that font in the CSS, be sure
  to also remove the font load reference here.

## New Features

* Hydeout adds a new tags page (accessible in the sidebar). Just create a
  new page with the tags layout:

  ```
  ---
  layout: tags
  title: Tags
  ---
  ```

* Hydeout adds a new "category" layout for dedicated category pages.
  Category pages are automatically added to the sidebar. All other pages
  must have `sidebar_link: true` in their front matter to show up in
  the sidebar. To create a category page, use the `category` layout:

  ```
  ---
  layout: category
  title: My Category
  ---

  Description of "My Category"
  ```

* You can control how pages are sorted by using the `sidebar_sort_order`
  parameter in the front matter. This works for both category and non-category
  pages, although non-category pages will always come first. Take a look at
  [`_includes/sidebar-nav-links.html`](./_includes/sidebar-nav-links.html) if
  you want to customize this behavior.

  ```
  ---
  layout: page
  title: My page
  sidebar_sort_order: 123
  ---

  Some content.
  ```

* A simple redirect-to-Google search is available. Just create a page with
  the `search` layout.

  ```
  ---
  layout: search
  title: Google Search
  ---
  ```

* Disqus integration is ready out of the box. Just add the following to
  your config file:

  ```yaml
  disqus:
    shortname: my-disqus-shortname
  ```
  You must sign up for a Disqus account [here](https://disqus.com/) if you haven't already. [More informations](https://desiredpersona.com/disqus-comments-jekyll/).

  If you don't want Disqus or want to use something else, override
  `comments.html`.

* For Google Analytics support, define a `google_analytics` variable with
  your property ID in your config file.

There's also a bunch of minor tweaks and adjustments throughout the
theme. Hope this works for you!

## Drafts

Drafts are posts without a date in the filename. They’re posts you’re still working on and don’t want to publish yet. To get up and running with drafts, create a _drafts folder in your site’s root and create your first draft:

```
.
├── _drafts
│   └── a-draft-post.md
...
```

To preview your site with drafts, run ```bundle exec jekyll serve --livereload --drafts``` or simply ```npm run drafts```. Each will be assigned the value modification time of the draft file for its date, and thus you will see currently edited drafts as the latest posts.

When the post is ready to be published, add the date at the beginning of the file name:

```
YEAR-MONTH-DAY-title.MARKUP
```

Where YEAR is a four-digit number, MONTH and DAY are both two-digit numbers, and MARKUP is the file extension representing the format used in the file. For example, the following are examples of valid post filenames:

```
2011-12-31-new-years-eve-is-awesome.md
2012-09-12-how-to-write-a-blog.md
```

Finally, add your post to _posts directory:

```
.
├── _posts
│   ├── 2011-12-31-new-years-eve-is-awesome.md
│   └── 2012-09-12-how-to-write-a-blog.md
...
```

## Projects

If you want to add a project to the blog, you should create a `project-name.md` file. It should be like so:

```
---
layout: project
title:
contributors: (coma separated)
client:
start_date: (YEAR-MONTH-DAY)
end_date: (YEAR-MONTH-DAY) (or nothing if still in progress)
excerpt:
img: /pictures/projects/...
---

Content of the project.

```

You can also use the `_drafts` folder to keep your changes but notice that the layout is not the same (`post`) for drafts.

When your file is ready, just add it in the `_projects` folder.