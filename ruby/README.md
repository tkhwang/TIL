# Ruby

## Manage ruby versions

[How to update Ruby Version 2.0.0 to the latest version in Mac OSX Yosemite? - Stack Overflow](https://stackoverflow.com/questions/38194032/how-to-update-ruby-version-2-0-0-to-the-latest-version-in-mac-osx-yosemite)

```
Open your terminal and run

\curl -sSL https://get.rvm.io | bash -s stable
When this is complete, you need to restart your terminal for the rvm to work.

Now, run rvm list known

This shows the list of versions of the ruby.

Now, run rvm install ruby-2.4.1

If you type ruby -v in the terminal, it still shows you ruby 2.0.

To use the latest installed version. Run rvm use ruby-2.4.1

To set this as the default version, run rvm use ruby-2.4.1 --default
```