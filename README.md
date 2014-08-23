## What the hell?

I suppose you know what alfred-workflow is.
This vim plugin is a collection of unite.vim extentions as a alternative of that.

### github events

![ge](./screenshots/github_event.png)

Fetch recent github events of a certain user.

### github feeds

Fetch github timeline of a certain user(defaults to g:github_user).

### github repository searching

Search for github repos by keywords.

### gist user

NOTE:This feature requires [gist-vim](https://github.com/mattn/gist-vim).
![gu](./screenshots/gist_user.png)
List public gists created by a certain user(defaults to g:github_user).
Actions:
    * edit, open with `:Gist id`.
    * start, open in a browser.

### gist searching

Search for gists.
Similar to gist-user.

### reddit

Fetch hot topics from reddit.
use `g:unite#workflow#reddit#front` to specify user front feed json url.
Should be like this `http://www.reddit.com/.json?feed={hash}&user={username}`.
If not, the fetching scope will be 'all'.
If used with input, the input is taken as subreddit like this:

![re](./screenshots/reddit.png)

### v2ex

Latest topics of http://www.v2ex.com
![v2](./screenshots/v2ex.png)

### youdao

有道词典/翻译
![yd](./screenshots/youdao.png)

## Installation

You need these plugins installed and loaded.

* [unite.vim](https://github.com/shougo/unite.vim)
* [webapi-vim](https://github.com/mattn/webapi-vim)
* [gist-vim](https://github.com/mattn/gist-vim) for gist sources

Then just use your preferred managing tool for this plugin.

## Customization

* `g:unite#workflow#show_icon` 0 to disable avatar display.
* `g:unite#workflow#reddit#front` as described above.

Example:

``` vim
let g:unite#workflow#reddit#front = 'http://www.reddit.com/.json?feed=foo&user=bar'
call unite#custom#profile(
            \ 'source/github/search, source/github/event, '.
            \ 'source/github/feed, source/gist/search, '.
            \ 'source/gist/user, source/v2ex, '.
            \ 'source/reddit',
            \ 'context',
            \ {
            \   'keep_focus' : 1,
            \   'no_quit' : 1
            \ })
call unite#custom#profile(
            \ 'source/youdao',
            \ 'context',
            \ {
            \   'max_multi_lines' : 10
            \ })
```

## License

MIT