Heroku buildpack: FFMpeg
=======================

This is a Heroku buildpack for ffmpeg.tar.gz - x264, mp3lame, libvorbis, libogg

It doesn't do anything else, so to actually compile your app you should use [heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi) to combine it with a real buildpack.

Usage
-----
To use this buildpack, you should prepare .buildpacks file that contains this buildpack url and your real buildpack url.  

    $ ls
    .buildpacks
    ...
    
    $ cat .buildpacks
    https://github.com/brooks/heroku-buildpack-ffmpeg-x264
    https://github.com/heroku/heroku-buildpack-ruby

    $ heroku create --buildpack https://github.com/ddollar/heroku-buildpack-multi

    $ git push heroku master
    ...

You can verify installing ffmpeg by following command.

    $ heroku run "ffmpeg -version"

