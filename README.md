## NNU Aerospace Club Website

Github Pages is hosting the website, the information required to make it of which is contained in here. It uses the Jekyll Markdown - HTML maker of web-deving easier. 

To modify the website, you can change the various .md files. index.md is the home page, it contains links to each year's .md pages. These are stored in the `/docs` folder

`/_includes` is a modified header file from the default Jekyll theme 'minima' It stretches everything out and puts the logo at the top. 

`/assets` holds most image files. favicon.ico is the thumbnail displayed in the tab.

`/_config.yml` controlls the static site stuff like the youtube and github links. The `header-pages:` title controls which pages get shown in global navigation at the top. Google is your friend when trying to figure out how to change stuff. If you just want to add a new year's project, then clone the whole thing, copy `2026.md` and make `2027.md`, or whatever year you want, modify the file appropriately, add `2027.pdf` (the final report) and the update `index.md` with a link to `2027.md`, or whever the reports folder is. 


### Setup Instructions
If you want to update the website, here are instructions on how to get to the point you can start editing things.

You need some version of Ruby in order to mess with Jekyll. rbenv is a handy way to do it on linux distros. If you don't have linux, use wsl in windows. Install the ubuntu image and open a terminal, all of this should run just fine. Sorry if you have a mac. It's probably pretty similar, except you'll be using zsh instead of bash

This site was built using ruby 3.3.8 because ruby 4.x doesn't seem to work with github pages at the time of writing this.

[Jekyll and GitHub Pages Documentation](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll)

#### Install rbenv
First, install necessary dependencies

```bash
sudo apt update
sudo apt install -y git build-essential curl \
    libssl-dev zlib1g-dev libreadline-dev \
    libyaml-dev libsqlite3-dev sqlite3 \
    libxml2-dev libxslt1-dev libffi-dev \
    libgdbm-dev libncurses5-dev libtool bison pkg-config
```

Now clone the rbenv git repo
```bash
git clone https://github.com/rbenv/rbenv.git ~/.rbenv
git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
```

Put the following two lines in ~/.bashrc

```bash
export PATH="$HOME/.rbenv/bin:$PATH"
eval "$(rbenv init - bash)"
```

Reload shell

```bash
source ~/.bashrc
```

Install ruby version 3.3.8 (install builds it from source, so it may take a while)

```bash
rbenv install 3.3.8
rbenv global 3.3.8
```

Install Bundler

```bash
gem install bundler
bundle install
```

#### Setup local files

```bash
cd ~
mkdir website
cd website
git clone https://github.com/nnu-aerospace/nnu-aerospace.github.io
cd nnu-aerospace.github.io
```

Launch local web server

```bash
bundle exec jekyll serve
```
Presuming everything works, you can now open http://localhost:4000/ and preview the website
When you update any of the markdown files, presuming the terminal you ran `bundle exec jekyll serve` is still open, it will automatically update the web page. Just reload it to see your changes. If you navigate to a new page and it hasn't updated, refresh the page to update the cache. 

To update the public website, commit and push everything to github. Presuming everything builds fine, it'll update a few minues afterwards and https://nnu-aerospace.github.io/ will reflect your changes

Ye oughta be in the root directory when ya run this stuff, if you followed the directions, `~/website/nnu-aerospace.github.io`

```bash
git add .
git commit -m "Your comments about why you\'re adding stuff"
git push
```





