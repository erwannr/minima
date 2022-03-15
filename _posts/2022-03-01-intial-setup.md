
## Initial setup
This is from memory I haven't tested.

Packages:
```
sudo apt-get install ruby-full build-essential zlib1g-dev
sudo gem install jekyll bundler
```

Config:
```
$ sudo apt-get install webrick
$ echo ' - jekyll-relative-links' >> _config.yml
$ echo ' - show_drafts' >> _config.yml
$ echo "gem 'jekyll-relative-links'" >> Gemfile
$ sudo bundle add webrick
```
The last step takes care off adding wr to `_config.yml`.

Add `_drafts/dummy`:
```
$ mkdir _drafts
$ touch dummy.md
$ printf "%s\n" '---' 'layout: page' '---'
```

To serve locally, first look for open processes matching jekyll and kill them.
```
$ sudo netstat -anp | grep 4000
$ sudo kill -9 <PID>
```
Then:
```
$ sudo bundler exec jekyll serve
```
This will create `_site`. 
In the browser, type address `http://127.0.0.1:4000`.
This address should load: `http://127.0.0.1:4000/dummy/`

###  Resources

https://jetholt.com/micro/jekyll-tags-and-categories/
https://lazyren.github.io/devlog/creating-tag-list-page.html
