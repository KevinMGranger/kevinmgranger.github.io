--- title: On curlFS, webFS ---

## The Vision

My plans for curlFS isn't fully defined at this point, but here's my overarching
vision and thoughts right now.

- I want to be able to `cd` into my favorite websites, and `ls` to see updates.
- I want to be able to `cat` a URL and see the page in my terminal.
- I want to be able to `echo` data into a URL to POST to it.

To expand upon this, I want to be able to read updates / pages from my favorite
websites in a clean, readable format that works well with existing tools.

Unfortunately, not too many websites out there have a `text/plain` option!

I'm thinking of solving the problem in the following way:

- Define your favorite websites in terms of their API schema
- Define translators / transformers for the data. Looking at unfomatted JSON can
  `{"get":["visually","exhausting"]}`

What if you could just see a markdown formatted post in your terminal? What if
you could see images from the article processed with
[libcaca](http://caca.zoy.org/wiki/libcaca) or
[aalib](http://aa-project.sourceforge.net/aalib/)?

Well, maybe that's a bit too far.

I'm going to try and get a rudimentary, all-inclusive curlFS up and running.
Later, I will try to split it out into several smaller, focused libraries.

## The Stack

The stack would have the following components:

### libcpptsb: C++11/C++14 thread-safe buffers.

Read and write at the same time as long as the read won't overlap the writing
point, at which point it will block.

### curlcpppp: an extended curlcpp.

I'd like to add a bit to the existing
[curlcpp](https://github.com/JosephP91/curlcpp) library. It's overall a nice,
simple, small library, but I think it could be made a little nicer to work with.
Whether this would be an additional wrapper on top, a fork, or changes
contributed upstream remains to be seen.

Coincidentally, while looking for the link to curlcpp, I found the
simlarly-named [curlpp](https://github.com/jpbarrette/curlpp), which I'll need
to investigate.

### curlFS: A FUSE interface for CURL.

Picture `ls` or `stat` as a HEAD request, reading from the file a GET, and
writing to the file a POST.

### transformator: Transform content, transparently.

Picks translation programs based on path, configuration, and analyzing the
content. These programs would take the file contents at the given path,
determine the transforming program, write to its standard input, and read back
its standard output. This would be an additional FUSE filesystem layered over
curlFS. However, I'd like to look into plan9's `plumber` a bit more-- it might
be the perfect tool for this job.
