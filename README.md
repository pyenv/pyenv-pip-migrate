# pyenv-pip-migrate

pyenv-pip-migrate is a [pyenv](https://github.com/yyuu/pyenv) plugin
that provides a `pyenv migrate` command to migrate pip package from a Python
version to another.

## Installation

### Installing as a pyenv plugin

Installing pyenv-pip-migrate as a pyenv plugin will give you access to the
`pyenv migrate` command.

    $ git clone git://github.com/yyuu/pyenv-pip-migrate.git $(pyenv root)/plugins/pyenv-pip-migrate

This will install the latest development version of pyenv-pip-migrate into
the `$(pyenv root)/plugins/pyenv-pip-migrate` directory. From that directory, you
can check out a specific release tag. To update pyenv-pip-migrate, run `git
pull` to download the latest changes.


### Installing with Homebrew (for OS X users)

Mac OS X users can install pyenv-pip-migrate with the
[Homebrew](http://brew.sh) package manager.
This will give you access to the `pyenv-migrate` command. If you have pyenv
installed, you will also be able to use the `pyenv migrate` command.

*This is the recommended method of installation if you installed pyenv
 with Homebrew.*

```
$ brew install pyenv-pip-migrate
```

Or, if you would like to install the latest development release:

```
$ brew install --HEAD pyenv-pip-migrate
```

## Usage

### Using `pyenv migrate` with pyenv

pyenv-pip-migrate uses `pip freeze` to dump all installed packages in a Python version,
and then tries to `pip install` them into another version.

Let's say if you have following two versions in pyenv.

    $ pyenv versions
    * 2.7.4 (set by /home/yyuu/.pyenv/version)
      2.7.5
    $ pip freeze
    distribute==0.6.43
    nose==1.3.0
    wsgiref==0.1.2

To migrate installed packages from `2.7.4` to `2.7.5`, use `pyenv migrate`.

    $ pyenv migrate 2.7.4 2.7.5
    $ pyenv global 2.7.5
    $ pip freeze
    distribute==0.6.43
    nose==1.3.0
    wsgiref==0.1.2

## Version History

#### 20130527

 * Initial public release.

### License

(The MIT License)

* Copyright (c) 2013 Yamashita, Yuu

Permission is hereby granted, free of charge, to any person obtaining
a copy of this software and associated documentation files (the
"Software"), to deal in the Software without restriction, including
without limitation the rights to use, copy, modify, merge, publish,
distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to
the following conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND
NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE
LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
