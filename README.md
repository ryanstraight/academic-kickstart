# To Do:



# Update log

Updated using version 4.4 in 2019 July
Updated to 4.5 on 2019 July 29
Updating to 4.6.0 Dec 9
Updating to 4.8.0 on Mar 14 2020
Updating to 4.9.0 (WIP) on April 30 2020 and using Hugo 0.69.2 Extended

# Notes to self:

To make a noise when the site build is completed:

beepr::beep_on_error(blogdown::build_site()), sound = 5)
beepr::beep(sound = 1)

In-line Latex: $ r^{2} $


Change TOC footer in `layouts / partials / docs_toc_foot.html`

to:

```
<div style="font-size: small;">
  <ul class="connect-links fa-ul">
    <li><i class="fa-li fas fa-question-circle"></i><a href="#" target="_blank">Ask questions</a></li>
    <li><i class="fa-li fas fa-comments"></i><a href="#" target="_blank">Request features</a></li>
    <li><i class="fa-li fas fa-bug"></i><a href="#" target="_blank">Report issues</a></li>
    <li><i class="fa-li fas fa-edit"></i><a href="#">Edit this page</a></li>
  </ul>
</div>
```

To show what a whole R code chunk looks like, use this syntax:

````markdown
`r ''````{r label}
code here
```
````
```



---
Original readme:

# [Academic Kickstart](https://sourcethemes.com/academic/)

**Academic** makes it easy to create a beautiful website for free using Markdown, Jupyter, or RStudio. Customize anything on your site with widgets, themes, and language packs. [Check out the latest demo](https://academic-demo.netlify.com/) of what you'll get in less than 10 minutes, or [view the showcase](https://sourcethemes.com/academic/#expo).

**Academic Kickstart** provides a minimal template to kickstart your new website.

- [**Get Started**](#install)
- [View the documentation](https://sourcethemes.com/academic/docs/)
- [Ask a question](http://discuss.gohugo.io/)
- [Request a feature or report a bug](https://github.com/gcushen/hugo-academic/issues)
- Updating? View the [Update Guide](https://sourcethemes.com/academic/docs/update/) and [Release Notes](https://sourcethemes.com/academic/updates/)
- Support development of Academic:
  - [Donate a coffee](https://paypal.me/cushen)
  - [Become a backer on Patreon](https://www.patreon.com/cushen)
  - [Decorate your laptop or journal with an Academic sticker](https://www.redbubble.com/people/neutreno/works/34387919-academic)
  - [Wear the T-shirt](https://academic.threadless.com/)

[![Screenshot](https://raw.githubusercontent.com/gcushen/hugo-academic/master/academic.png)](https://github.com/gcushen/hugo-academic/)

## Install

You can choose from one of the following four methods to install:

* [**one-click install using your web browser (recommended)**](https://sourcethemes.com/academic/docs/install/#install-with-web-browser)
* [install on your computer using **Git** with the Command Prompt/Terminal app](https://sourcethemes.com/academic/docs/install/#install-with-git)
* [install on your computer by downloading the **ZIP files**](https://sourcethemes.com/academic/docs/install/#install-with-zip)
* [install on your computer with **RStudio**](https://sourcethemes.com/academic/docs/install/#install-with-rstudio)

Then [personalize your new site](https://sourcethemes.com/academic/docs/get-started/).

## Ecosystem

* **[Academic Admin](https://github.com/sourcethemes/academic-admin):** An admin tool to import publications from BibTeX or import assets for an offline site
* **[Academic Scripts](https://github.com/sourcethemes/academic-scripts):** Scripts to help migrate content to new versions of Academic

## License

Copyright 2017-present [George Cushen](https://georgecushen.com).

Released under the [MIT](https://github.com/sourcethemes/academic-kickstart/blob/master/LICENSE.md) license.

[![Analytics](https://ga-beacon.appspot.com/UA-78646709-2/academic-kickstart/readme?pixel)](https://github.com/igrigorik/ga-beacon)
