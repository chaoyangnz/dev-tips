# How to install lagacy version from homebrew

Sometimes, the latest version of a package has bugs so I want to revert to a previous version. 

Unfortunately, HomeBrew doesn't provide that option for most of the software package.

The following, I take `hugo` package for an example.

To make sure if you can install a previous version, run first

```bash
brew search hugo
```

Sadly, there is no previous version provided.

So please follow these steps:

- open [Homebrew Core](https://github.com/Homebrew/homebrew-core) and go to directory [Formula](https://github.com/Homebrew/homebrew-core/tree/master/Formula)
- search your package, like mine [`hugo.rb`](https://github.com/Homebrew/homebrew-core/blob/master/Formula/hugo.rb)
- once found, click `History` button and find the commit of your expected version
- until now, we get its [history version](https://github.com/Homebrew/homebrew-core/blob/5f0dab7e13ea215f816660dae46fd9fda81b1606/Formula/hugo.rb) of this file, view its `Raw` content, copy the URL, like:
https://raw.githubusercontent.com/Homebrew/homebrew-core/5f0dab7e13ea215f816660dae46fd9fda81b1606/Formula/hugo.rb
- run `brew install https://raw.githubusercontent.com/Homebrew/homebrew-core/5f0dab7e13ea215f816660dae46fd9fda81b1606/Formula/hugo.rb`

Bingo! If you need to install other package, the way is the same.


## reference
https://www.fernandomc.com/posts/brew-install-legacy-hugo-site-generator/
