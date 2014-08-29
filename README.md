word2vec-macosx-maverics
========================

## About word2vec

Tool for computing continuous distributed representations of words.

This tool provides an efficient implementation of the continuous bag-of-words and skip-gram architectures for computing vector representations of words. These representations can be subsequently used in many natural language processing applications and for further research.

## Info

I have nothing to do with the original paper. I wanted to play around with the word2vec implementation, but I had some trouble compiling it on my Mac, because some header files were in the wrong place. This is a fixed repository that might be useful for other Mac users. I got the right file paths from here:

http://tottokug.hatenablog.com/entry/2014/04/17/160603


## Original repository

https://code.google.com/p/word2vec/

Apache License 2.0

## Quick start

* ~~Download the code: `svn checkout http://word2vec.googlecode.com/svn/trunk/`~~
* Download the code: `git clone https://github.com/h10r/word2vec-macosx-maverics.git`
* Run 'make' to compile word2vec tool
* Run the demo scripts: ./demo-word.sh and ./demo-phrases.sh (See other issues)
* For questions about the toolkit, see http://groups.google.com/group/word2vec-toolkit

## Other issues

I also noticed that running demo-word.sh crashed, mainly due to the line 

```
gzip -d text8.gz -f text8
```

I just used Archive Utility.app to decompress text8.gz and then ran

```
time ./word2vec -train text8 -output vectors.bin -cbow 0 -size 200 -window 5 -negative 0 -hs 1 -sample 1e-3 -threads 12 -binary 1
./distance vectors.bin
```

in the terminal.
