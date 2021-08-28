# About this directory
You can add backup files like database or JSON, but you should not track them on Git because they may contain the credential information. All files in this directory will not be tracked except this README.



# How to import from your Ghost blog
When it comes to Ghost, there are two ways to import to a Jekyll blog.

* [jekyll-import](https://import.jekyllrb.com/docs/ghost/)
* [jekyll_ghost_importer](https://github.com/eloyesp/jekyll_ghost_importer)

At the instruction below, I assume you have already installed all gems used in this project by `bundle install`.

[jekyll-import](https://import.jekyllrb.com/docs/ghost/), which is the official importer tool, lets you import your Ghost blog posts to a new Jekyll blog as follow:

```shell
cd /path/to/this/directory
scp <YOUR_GHOST_SERVER>:<GHOST_ROOT>/content/data/ghost.db .
ruby -r rubygems -e 'require "jekyll-import";
  JekyllImport::Importers::Ghost.run({
    "dbfile"   => "./ghost.db"
  })'
```

You will see `_posts` directory and maybe find `_drafts` directory if you have not published some posts yet on your Ghost blog.

Alternatively, you can use [jekyll_ghost_importer](https://github.com/eloyesp/jekyll_ghost_importer), which was made by [Eloy Espinaco](https://github.com/eloyesp).

```shell
cd /path/to/this/directory
jekyll_ghost_importer <YOUR_GHOST_BLOG_DOMAIN>.ghost.<YYYY-MM-DD>.json
```

`<YOUR_GHOST_BLOG_DOMAIN>.ghost.<YYYY-MM-DD>.json` can be downloaded from your Ghost blog admin page like `https://example.com/ghost/settings/labs/`.

The generated files and directories are same as jekyll-import.

The differences between two importers are as follow:

* jekyll_ghost_importer can get each post’s date correctly, but jekyll-import can’t
  * by this, all posts are not in order if you use jekyll-import
* jekyll_ghost_importer can get each post’s tags, but jekyll-import can’t

I recommend jekyll_ghost_importer rather than jekyll-import because the above.
