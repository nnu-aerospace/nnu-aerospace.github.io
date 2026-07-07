## NNU Aerospace Club

Github Pages is hosting the website, the information required to make it of which is contained in here. It uses the Jekyll Markdown - HTML maker of web-deving easier. 

To modify the website, you can change the various .md files. index.md is the home page, it contains links to each of the years .md pages. These are stored in the /docs folder

/_includes is a modified header file from the default Jekyll theme 'minima' It stretches everything out and puts the logo at the top. 

/assets holds most image files. favicon.ico is the thumbnail displayed in the tab.


### Setup Instructions

First, install ruby. Pages can't seem to use ruby 4.0.x, so you got to use an older version. This was developed using Ruby 3.3.8. On linux install rbenv and read the necessary setup stuff to get it running. [Jekyll and GitHub Pages Documentation](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/creating-a-github-pages-site-with-jekyll)

Then you run bundle exec jekyll serve in the directory all your website stuff is stored in. It launches a localhost version of the website so you can see what you're doing in realtime. Whenever you modify any file other than  _config.yml, it auto updates. Just refresh the page to see your changes.

By default it puts it at http://localhost:4000/ Just enter that into your browser and you'll be good to go. When a working version is developed, push it to GitHub and after a minute or two it will rebuild the site and the https://nnu-aerospace.github.io will show your new changes



