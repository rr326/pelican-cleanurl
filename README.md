# pelican-cleanurl plugin

A python [pelican](https://github.com/getpelican/pelican) plugin
that creates clean urls for a page-based site.

For instance:

```
**Filename**                                 **URL**                                 **Output File**
pages/index.md                           ==> /                                    ==> index.html
pages/error.md                           ==> /error.html                          ==> error.html
pages/folder1/index.md                   ==> /folder1                             ==> folder1/index.html
pages/folder1/contents1.html             ==> /folder1/contents1                   ==> folder1/contents1/index.html
pages/folder1/contents2.html             ==> /folder1/contents2                   ==> folder1/contents2/index.html
pages/folder1/folder2/index.html         ==> /folder1/folder2                     ==> folder1/folder2/index.html
pages/folder1/folder2/contents1.html     ==> /folder1/folder2/contents1           ==> folder1/folder2/contents1/index.html
pages/folder1/folder2/contents2.html     ==> /folder1/folder2/contents2           ==> folder1/folder2/contents2/index.html
```

## Installation

`pip install git+https://github.com/rr326/pelican-cleanurl.git`


## Simple Usage (tested)

```
# pelicanconf.py
PLUGINS=['pelican_cleanurl']
PAGE_URL = '{cleanurl}'
PAGE_SAVE_AS = '{cleanurl_saveas}'
INDEX_SAVE_AS = 'sitemap.html' # Otherwise it will conflict with your own index.html
```

## Sample Dir Structure

```
pages
    /index.md
    /error.md
    /file1.md
    /folder1
        /index.md
        /contents1.html
        /contents2.html
        /folder2
            /index.html
            /contents1.html
            /contents2.html
```

This will create a "clean" url structure such as:

```
/ <-- index.html
/error.html # <-- This is a special page
/file <-- root level file
/folder1 <- folder1/index.html
/folder1/contents1
...
```

## Other features

I put a bunch of other hooks in the code, but I didn't test them.
I'm not going to work on them because I don't know if anyone else other
than I will use this repo.

## License

This project is licensed under the MIT license.
