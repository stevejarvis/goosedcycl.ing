# Goosed Cycling
This is a blog about Minnesota bike racing really. Probably. It's at least what I have in mind at the moment I'm writing this README.

# Author Setup and Posting
Check out the [post on the subject](https://www.goosedcycl.ing/authoring-stuff-on-this-blog/).

# Dev Setup
## Local
This is a Jekyll site. Basically
1. Install Ruby
2. `bundle install` 
3. `bundle exec jekyll serve`

## Upgrading
[Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) is our theme.
We're using the [remote-theme plugin](https://github.com/benbalter/jekyll-remote-theme) to pin to the latest release.

## Overriding
The remote-theme plugin downloads the Gem on the fly and unzips it to somewhere in `/private/var/...`. Recommend running 
`bundle exec jekyll serve --verbose` to see exactly where, then doing something like this to find the actual file the theme
is using (in this case, the footer):

```
cat /private/var/folders/1n/8lrxxq3d4ss6fd69krdv9hym0000gn/T/jekyll-remote-theme-20240329-15255-9k9kb4/_includes/footer.html
```