# Scribal Website Documentation
## Intro

The Scribal website is based on the [Lanyon Jekyll theme](https://github.com/poole/lanyon) and hosted at Github Pages (GHP). Jekyll is an open-source Ruby-based static website generator. It is tightly integrated with Github and is probably the easiest way to get a DIY website up and running quickly.

We opted for Lanyon because of its clean design, because it integrates a side-drawer which enables us to display basic "About" and "Contact" info for our company, and because Lanyon itself has options which let the user modify the look and feel. 

The documentation for [Jekyll](https://jekyllrb.com), [Lanyon](https://github.com/poole/lanyon) and [Poole](https://github.com/poole/poole) on which Lanyon is based are starting points for learning how to use the theme, but there are a few additional tricks you have to understand in order to deploy successfully on Github Pages(GHP).

## Deployment on Github Pages

There are a couple of particularly tricky aspects to publishing (and modifying Lanyon on GHP):
- Syncing Jekyll versions between GHP and your own local development machine. 
- Deploying Lanyon to GHP because it is not one of the default themes supported by Github.
- Ensuring that links that work on your local machine work on Github and vice versa.

 ### 1. Install the gh-pages gem in the project directory on your local machine

Do this ASAP - it installs in your local environment all the Ruby/Jekyll dependencies that are used by Github to deploy GHP. It's desirable to be able to review changes to your site locally before pushing to Github because GHP deploys those changes automatically. The current versions of Jekyll-related packages are listed on [this page](https://pages.github.com/versions/). The gh-pages gem also installs gems such as jekyll-sitemap which improves SEO. What you need to do is described  in [this blog post](https://idratherbewriting.com/documentation-theme-jekyll/mydoc_publishing_github_pages.html).

### 2. Take the following steps to get Lanyon css and internal links working properly

The most important thing for getting Lanyon to run properly on GHP are the links in the .'config_yml' file in the repo's home directory. There is an important distinction to make between sites that use a custom URL and those which use the default GHP URLs:
- if using a custom URL copy it into the URL slot in "Setup" and leave the 'baseurl' slot blank. You also have to create a CNAME file in the home directory which contains text pointing to your CNAME info. [Full documentation on how to configure this can be found here](https://docs.github.com/en/free-pro-team@latest/github/working-with-github-pages/managing-a-custom-domain-for-your-github-pages-site).
- if you are using the GHP default URL, the 'url' slot should be left blank and there shouldn't be any 'CNAME' file in the home directory. Instead, the 'baseurl' slot should be filled in with the name of the repo in Unix directory style (for this site it is - '/lanyon-jh-test/'). It took a lot of trial and error to get this to run correctly.

### 3. Use the formatting described below for internal/relative links so they will work locally and on GHP

Lanyon contains a fair amount of CSS so getting the settings for relative/absolute links is important. It's not enough to run Lanyon on a locally-hosted Jekyll instance because 

A second item to bear in mind are links within your Lanyon site. Relative links formatted in a standard way may work on your local Jekyll installation or on GHP, but rarely work on both. Instead, follow the following models (using the Liquid templating language ):

    {% post_url 2019-03-06-post-title.md %}
    {{ site.baseurl }}{% post_url 2019-03-06-post-title.md %}
    {{ site.baseurl }}{% post_url /folder/2019-03-06-post-title.md %}

For a more complete explanation look [at this post](https://www.webisland.agency/blog/jekyll-internal-links/) from which the code block was drawn. 

## Blogging Workflow

When Github pages detects changes in your repo, those changes are automatically deployed to the web. When multiple users have commit permission to the repo, there is always the possiblity of conflicting changes. Some rules of thumb to minimize the chances that this will cause problems either with a user's local copy of the repo or (less likely, but more disastrously) with the deployed site:
- Make sure to pull an up-to-date version of the repo before starting to make changes. The Git command that makes this easiest is 'git pull -- rebase' - for more complete explanation of how to use git to sync changes and updates [this blog post is helpful](https://supercollider.github.io/development/git-cheat-sheet).
- If we reach a point where there are multiple contributors to the site, one way to manage it is to designate a 'webmaster' with control over the repo and make everyone else fork the repo and have them submit pull requests in order for a post to appear on the production site.

## General References

Following are some helpful resources for deploying a Lanyon-based site:
- [Building your own Personal Website in Jekyll](https://chrisschuld.com/2019/02/building-your-own-website-in-jekyll/)
- [How to set up lanyon-plus jekyll theme](https://davidbarber.github.io/readme/)

## Google Analytics

For a basic view of your website's traffic, you can look at the ["Insights" tab](https://github.com/scribal-io/scribal-io.github.io/graphs/traffic) in the repo with your Github pages code. There is no need to install anything.

Sooner or later, most website operators want more insights and power features for their analytics. Google Analytics is a free, default option with wide adoption among experts. While powerful, GA is tricky to configure, all the more so on a DIY platform like Jekyll for GHP. At the time of writing (Mar 2021), [this blog post provides the most accurate instructions](https://desiredpersona.com/google-analytics-jekyll/) for installing Google analytics on a Jekyll-based GHP website. This tutorial provides [step-by-step instructions on setting up a Google Analytics account and setting up "properties" within the account](https://blog.hootsuite.com/how-to-set-up-google-analytics/) though many of the screenshot illustrations are drawn from previous versions of GA, not the current Google Analytics 4 (GA4) version of the product. Finally, [this tutorial walks you through troubleshooting steps](https://holini.com/google-analytics-isnt-working/) if you try to set up GA and it isn't working. Again,the post and the examples are a couple years old, but the troubleshooting methodology is solid. The tag manager extension was invaluable in helping us to get our installation working.

## Contact Us Form

Static sites do not natively handle user inputs such as contact or sign up forms.  In order to meet this need we have implemented a solution using the Serverless Framework which you can read about [here](https://docs.google.com/document/d/1zQVDQy-gEinpLucAmaZ67hhKUn7rmyi8SI3NFDZrlI4/edit?usp=sharing).  





