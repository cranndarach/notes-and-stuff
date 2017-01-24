# Installing Ruby and Rails

>Should work for Debian-based systems.

Information on this is pretty scattered and did not all work for me. I tried
RVM and did not find it helpful. Eventually I was able to piece together
enough info from [the Rails docs](http://guides.rubyonrails.org/getting_started.html), [this stackoverflow question](http://stackoverflow.com/questions/17655806/error-when-installing-ruby-on-rails-failed-to-build-gem-native-extension),
[this other stackoverflow question](http://stackoverflow.com/questions/20559255/error-while-installing-json-gem-mkmf-rb-cant-find-header-files-for-ruby),
and [this blog post](http://kazhack.org/?post/2014/12/12/pip-gem-install-without-sudo).

## 1. Install Ruby

Available in apt:

```sh
sudo apt-get install ruby
```

## 2. Install Ruby development environment

```sh
sudo apt-get install ruby-dev
```

This is necessary in order for gems to compile.

## 3. Configure gem to not require sudo

```sh
echo "gem: --user-install" >> ~/.gemrc
```

## 4. Add gem directories to your path

Add to your `~/.bashrc`:

```bash
for dir in $HOME/.gem/ruby/*; do
  [ -d "$dir/bin" ] && PATH="${dir}/bin:${PATH}"
done
```
and then run `source ~/.bashrc`

## 5. Update gem

```sh
sudo gem update --system
```

## 6. Install rails

```sh
gem install rails
```

That should do it!
