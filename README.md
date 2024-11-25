# My website

## Building the website locally

Windows:

- From admin command prompt: `choco install jekyll` -- this failed with an error installing jekyll but did seem to install its dependencies
- Close and open another admin command prompt: `gem install github-pages wdm webrick`

Mac:

- Follow https://jekyllrb.com/docs/installation/macos/
```sh
brew install chruby ruby-install
ruby-install ruby 3.3.5
echo "source $(brew --prefix)/opt/chruby/share/chruby/chruby.sh" >> ~/.zshrc
echo "source $(brew --prefix)/opt/chruby/share/chruby/auto.sh" >> ~/.zshrc
echo "chruby ruby-3.3.5" >> ~/.zshrc # run 'chruby' to see actual version
```
- New terminal
```sh
ruby -v
gem install jekyll
```

- Open a regular command prompt, and type `jekyll -v` to check that it worked.
- In project dir: `jekyll serve`
