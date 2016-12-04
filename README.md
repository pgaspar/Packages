### Note about this Fork:

I'm coming back to SublimeText after a year or so using Atom. One thing I liked a lot was that certain keywords like `TODO` and `NOTE` were automatically highlighted inside comments. This was made possible by [Atom's TODO package](https://github.com/atom/language-todo).

This fork changes the Ruby language syntax to include these keywords under the `storage.type.annotation` scope.

<img width="368" alt="screen shot 2016-12-04 at 04 08 24" src="https://cloud.githubusercontent.com/assets/31735/20864083/d1620e24-b9d9-11e6-8c45-5cf1d92a6d31.png">

Supported keywords:

```
TODO, FIXME, CHANGED, XXX, IDEA, HACK, NOTE, REVIEW, NB, BUG, QUESTION, COMBAK, TEMP, WARNING
```

For now, I don't plan to make a plugin out of this, so if you want this, download the [Ruby syntax file](https://github.com/pgaspar/Packages/blob/master/Ruby/Ruby.sublime-syntax) and use something like [PackageResourceViewer](https://github.com/skuroda/PackageResourceViewer) to edit this file in your Sublime Text installation.

# Sublime Packages

> **These packages are developed against the latest [Sublime Text 3 Dev Build](http://sublimetext.com/3dev). Bugs may exist on older builds, and the format used is not compatible with builds older than 3092.**

## Installation

If you want to make changes to these packages and test them locally, fork this repository and then symlink the changed packages into your *Packages* folder.

*Replace `Python` in the following commands with the name of the syntax to install.*

### OS X

```bash
$ git clone https://github.com/sublimehq/Packages.git
$ ln -s `pwd`/Packages/Python ~/Library/Application\ Support/Sublime\ Text\ 3/Packages/
```

### Linux

```bash
$ git clone https://github.com/sublimehq/Packages.git
$ ln -s `pwd`/Packages/Python ~/.config/sublime-text-3/Packages/
```

### Windows

On Windows, you can use directory junctions instead of symlinks (symlinks require administrative rights; directory junctions don't):

```powershell
# Using PowerShell
PS> git clone https://github.com/sublimehq/Packages.git
PS> cmd /c mklink /J "$env:APPDATA/Sublime Text 3/Packages/Python" (convert-path ./Packages/Python)
```

Alternatively, download the portable version, and clone this repository directly as a subdirectory of the *Data* folder.

---

After you've finished, keep in mind that you're now overriding a default package. When Sublime Text updates to a new version, you'll run the risk of having an out-of-date package unless you pull the latest changes from this repository.

## Pull Requests

Pull requests should:

 1. Start with the name of the package in square brackets, e.g. `[XML]`.
 2. Be as small and self-contained as is reasonable. *Smaller changes are quicker to review.*
 3. Include a new, or enhanced, [syntax test](http://www.sublimetext.com/docs/3/syntax.html) when changing a `.sublime-syntax` file.
 4. Have multiple syntax tests and a set of performance measurements (old vs. new) when making significant changes.

### New Packages

Pull requests for new packages won't be accepted at this stage, as new packages can cause issues for users who have a package with the same name installed via Package Control. There are some planned changes that will address this in the future.

Complex plugins such as auto complete systems and linters should generally be in a stand-alone package, rather than included in the default set of packages.

## Missing Packages

This repository only contains syntax-definition-focused packages. Notably, packages such as *Default* and *Theme - Default* are not included.
