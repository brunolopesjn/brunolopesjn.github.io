---
title: "Homepage Layout"
date: 2020-08-13
draft: false
description: "Configuring the homepage layout in the Blowfish theme."
slug: "homepage-layout"
tags: ["homepage", "layouts", "docs"]
---

Blowfish provides a fully flexible homepage layout. There are two main templates to choose from with additional settings to adjust the design. Alternatively, you can also provide your own template and have complete control over the homepage content.

The layout of the homepage is controlled by the `homepage.layout` setting in the `params.toml` configuration file. Additionally, all layouts have the option to include a listing of [recent articles](#recent-articles).

## Profile layout

The default layout is the profile layout, which is great for personal websites and blogs. It puts the author's details front and centre by providing an image and links to social profiles.

![Screenshot of profile layout](home-profile.png)

The author information is provided in the languages configuration file. Refer to the [Getting Started]({{< ref "getting-started" >}}) and [Language Configuration]({{< ref "configuration##language-and-i18n" >}}) sections for parameter details.

Additionally, any Markdown content that is provided in the homepage content will be placed below the author profile. This allows extra flexibility for displaying a bio or other custom content using shortcodes.

To enable the profile layout, set `homepage.layout = "profile"` in the `params.toml` configuration file.


## Page layout

The page layout is simply a normal content page that displays your Markdown content. It's great for static websites and provides a lot of flexibility.

![Screenshot of homepage layout](home-page.png)

To enable the page layout, set `homepage.layout = "page"` in the `params.toml` configuration file.


## Custom layout

If the built-in homepage layouts aren't sufficient for your needs, you have the option to provide your own custom layout. This allows you to have total control over the page content and essentially gives you a blank slate to work with.

To enable the custom layout, set `homepage.layout = "custom"` in the `params.toml` configuration file.

With the configuration value set, create a new `custom.html` file and place it in `layouts/partials/home/custom.html`. Now whatever is in the `custom.html` file will be placed in the content area of the site homepage. You may use whatever HTML, Tailwind, or Hugo templating functions you wish to define your layout.

To include [recent articles](#recent-articles) on the custom layout, use the `recent-articles.html` partial.

As an example, the [homepage]({{< ref "/" >}}) on this site uses the custom layout to allow toggling between the profile and page layouts. Visit the [GitHub repo](https://github.com/nunocoracao/blowfish/blob/main/exampleSite/layouts/partials/home/custom.html) to see how it works.

## Recent articles

All homepage layouts have the option of displaying recent articles below the main page content. To enable this, simply set the `homepage.showRecent` setting to `true` in the `params.toml` configuration file.

![Profile layout with recent articles](home-profile-list.png)

The articles listed in this section are derived from the `mainSections` setting which allows for whatever content types you are using on your website. For instance, if you had content sections for _posts_ and _projects_ you could set this setting to `["posts", "projects"]` and all the articles in these two sections would be used to populate the recent list. The theme expects this setting to be an array so if you only use one section for all your content, you should set this accordingly: `["blog"]`.

## Thumbnails

Blowfish was built so it would be easy to add visual support to your articles. If your familiar with Hugo article strucutre, you just need to place an image file (almost all formats are supported bue we recommend `.png` or `.jpg`) that starts with `feature*` inside your article folder. And that's it, Blowfish will then able to both use the image as a thumbnail within your website as well as for <a target="_blank" href="https://oembed.com/">oEmbed</a> cards across social platforms. 

[Here]({{< ref "thumbnails" >}}) is also a guide with more info and a [sample]({{< ref "thumbnail_sample" >}}) if you want to see how you can do it.