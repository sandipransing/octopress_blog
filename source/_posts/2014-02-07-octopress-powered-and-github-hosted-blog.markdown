---
layout: post
title: "Getting started: Octopress powered and Github hosted blog"
date: 2014-02-07 19:20:07 +0530
comments: false
categories: octopress github-pages
---
There are various blogging sites like `blogspot`, `wordpress`, `posterious`, and many more. But each has their own limitations.
Anyone who has some technical background can start with octopress blog. This gives us the power of freedom of doing anything.
So, Lets first understand about octopress framework and its features.

## Octopress

> Octopress is a framework designed by Brandon Mathis for Jekyll, the blog aware static site generator. more info can be found [here](http://octopress.org/2011/07/23/octopress-20-surfaces/)

## Octopress Setup

1. Before starting make sure you have `git` installed. If not then - 
```
sudo apt-get install git
```
2. Install `ruby` 1.9.3 or higher

Make git clone of octopress source code
```
git clone git://github.com/imathis/octopress.git octopress
cd octopress
bundle install
```
## Installing Octopress theme
Install the default Octopress theme using
```
rake install
```

In order to install custom themes,
Please [browse through themes](http://opthemes.com/) and make a selection for your blog.
Once choice is made, you need to do `git clone` of theme source and install it.

```
cd octopress
git clone https://github.com/kAworu/octostrap3 .themes/octostrap3
rake 'install[octostrap3]'
```

To genrate infrastrcture for your blog i.e. `layouts`, `js` and `css` 
```
rake generate
```
Edit `_config.yml` to configure blog `title`, `header`, `metadata`, `plugins` and `3rd Party Settings`.
more on configurations can be found [here](http://octopress.org/docs/configuring/).

We are almost done, and now ready to create our first blog post -
```
rake new_post["My first octopress post"]
mkdir -p source/_posts
Creating new post: source/_posts/2014-02-09-my-first-octopress-post.markdown
```
Now you can open a post inside editor and change as you wanted. More on writing markdown can be found [here](https://github.com/adam-p/markdown-here/wiki/Markdown-Here-Cheatsheet#wiki-html) and [here too](http://daringfireball.net/projects/markdown/syntax)

Well, now its time to view how our blog looks like -
```
cd octopress
rake watch
rake preview
```
Visit browser `http://localhost:4000` and you should be seeing blog running there.

## Deployment

There are ways to deploy this blog. You can either deploy this blog on `heroku` or on `github` using github pages.
### Heroku
More on Heroku deployment can be found [here](http://def.reyssi.net/blog/2012/01/14/get-blogging-with-octopress-on-heroku/)

### With Github Project pages
Github deployment is simple. First you need to create a github repository called `username.github.io`
```
rake setup_github_pages
git remote add origin git@github.com:username/username.github.io.git
rake generate
rake deploy
```

Visit `http://username.github.io` to see your blog hosted on github.
Also, do not forget to commit and push your source code on github.
```
git add .
git commit -m 'octopress first blog'
git push origin source
```

## Adding custom domain
First create a `CNAME` file and add naked domain name to it.
```
echo 'funonrails.com' >> source/CNAME
```
Then goto your domain provider website and point your `domain` i.e A record to github ip address `204.232.175.78`.
### Subdomain
If you want to point subdomain to github blog then -
```
echo 'blog.sandipransing.in' >> source/CNAME
```
then goto your domain provider website and create a CNAME record for your `subdomain` i.e. `blog` pointing to `yourname.github.io.`
If you want more help then see [here](http://octopress.org/docs/deploying/github/) and also [here](http://help.github.com/pages/#custom_domains)
