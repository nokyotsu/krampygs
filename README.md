krampygs
========

Unleash the power of [Kramdown][] with [Pygments][] and [Typogruby][] in [Jekyll][].

If you want to know, read why it is such a good idea to [use Kramdown with Pygments][initial].

## Usage

Add `krampygs.rb` to your `_plugins` directory, and the following bogus Markdown extension

    markdown_ext: foo
    
to your `_config.yml`. This is a workaround to get Jekyll ignore its own Markdown converters and use instead the custom converter provided (which explicitly looks for `.md` files).

Code in your pages can now be syntax highlighted using the power of Pygments.

    For example fenced code
    
    ~~~ ruby
    print "Hello World"
    ~~~
    
    Or inline code like this: `\section{foo}`{:.language-latex}

You can also define a global default for a whole site adding

    kramdown:
      default_lang: python

to your `_config.yml`; or, for a single page, by adding something like

    {::options coderay_default_lang="fortran" /}
    
near the top of a page. (No, coderay is _not_ being used, but that was the easiest hack I could find to get the value of the option into Kramdown.)


Github flavor markdown syntax is also supported by adding 

    kramdown:
      input: GFM

to your `_config.yml`. For example GFM code
    
    ```ruby
    print "Hello World"
    ```

## Tested with

* ruby 2.0.0p247
* jekyll (1.1.2)
* kramdown (1.1.0)
* pygments.rb (0.5.2)
* typogruby (1.0.15)

[kramdown]: http://kramdown.rubyforge.org/
[pygments]: http://pygments.org/
[typogruby]: http://avdgaag.github.io/typogruby/
[jekyll]: http://jekyllrb.com/

## Thanks

To Matthias for his [initial plugin idea][initial], and his help getting it [fixed to work with Jekyll 1.x][fix].

[initial]: http://bloerg.net/2013/03/07/using-kramdown-instead-of-maruku.html
[fix]: http://stackoverflow.com/q/18214424/359178
