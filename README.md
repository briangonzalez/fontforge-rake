# FontForge Rake
A set of Rake tasks for working with FontForge. 

There is no need to install FontForge on your system in order to get this repo working. It comes bundled with a universal binary, which can be found [here](http://fuuko.libferris.com/osx/packages/).

## Usage
Type `rake -T` to see all tasks.

## Adding a new script
Place your script inside of `./scripts` and look inside the `Rakefile` for the conventions on how to call it within a new Rake task.