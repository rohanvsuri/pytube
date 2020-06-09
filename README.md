<div align="center">
  <p>
  <img src="https://assets.nickficano.com/gh-pytube.min.svg" width="456" height="143" alt="pytube logo" />
  </p>
  <p align="center">
	  <img src="https://img.shields.io/pypi/v/pytube.svg" alt="pypi">
	  <a href="http://python-pytube.readthedocs.io/en/latest/?badge=latest">
      <img src="https://readthedocs.org/projects/python-pytube/badge/?version=latest" />
    </a>
	  <a href="https://codecov.io/gh/nficano/pytube">
      <img src="https://codecov.io/gh/nficano/pytube/branch/master/graph/badge.svg" />
    </a>
    <a href="https://pypi.org/project/pytube/">
      <img src="https://img.shields.io/pypi/dm/pytube.svg" alt="pypi">
    </a>
	  <a href="https://pypi.python.org/pypi/pytube/">
      <img src="https://img.shields.io/pypi/pyversions/pytube.svg" />
    </a>
  </p>
</div>

<<<<<<< 4e12eb54d1ee72e41e9a7e53a3d708e300ccf661
=======
# Call for Successor
Hello, I am unable to maintain and contribute to this project much these days. If you would like to it become the successor, please email me at nficano(at)gmail.com.
>>>>>>> Update README.md

### Actively soliciting contributers!
Have ideas for how pytube can be improved? Feel free to open an issue or a pull
request!

# pytube
*pytube* is a very serious, lightweight, dependency-free Python library (and
command-line utility) for downloading YouTube Videos.


## Documentation
Detailed documentation about how to use the library can be found on our
[readthedocs](https://python-pytube.readthedocs.io) page. This is recommended
for most use cases. If you just want to quickly download a single video,
the [quickstart](#Quickstart) guide below might be what you're looking for.


## Description
YouTube is the most popular video-sharing platform in the world and as a hacker
you may encounter a situation where you want to script something to download
videos. For this I present to you *pytube*.

*pytube* is a lightweight library written in Python. It has no third party
dependencies and aims to be highly reliable.

*pytube* also makes pipelining easy, allowing you to specify callback functions
for different download events, such as  ``on progress`` or ``on complete``.

Finally *pytube* also includes a command-line utility, allowing you to quickly
download videos right from terminal.


## Features
- Support for both progressive & DASH streams
- Support for downloading complete playlist
- Easily register ``on_download_progress`` & ``on_download_complete`` callbacks
- Command-line interfaced included
- Caption track support
- Outputs caption tracks to .srt format (SubRip Subtitle)
- Ability to capture thumbnail URL
- Extensively documented source code
- No third-party dependencies

## Quickstart
This guide is only meant to cover the most basic usage of the library. For more
detailed information, please refer to our
[readthedocs](https://python-pytube.readthedocs.io) page.

### Installation
Pytube requires an installation of python 3.6 or greater, as well as pip.
Pip is typically bundled with python installations, and you can find options
for how to install python at https://python.org.

To install from pypi with pip:

```bash
$ python -m pip install pytube
```

Sometime, the pypi release becomes slightly outdated. To install from the
source with pip:

```bash
$ python -m pip install git+https://github.com/pytube/pytube
```

### Using pytube in a python script
To download a video using the library in a script, you'll need to first import
the YouTube class from the library, and pass it an argument of the video url.
From there, you can access the streams and download them.

```python
 >>> from pytube import YouTube
 >>> YouTube('https://youtu.be/2lAe1cqCOXo').streams.first().download()
 >>> yt = YouTube('http://youtube.com/watch?v=2lAe1cqCOXo')
 >>> yt.streams
  ... .filter(progressive=True, file_extension='mp4')
  ... .order_by('resolution')
  ... .desc()
  ... .first()
  ... .download()
```

### Using the command-line interface
Using the CLI is extremely straightforward as well. To download a video at the
highest progressive quality, you can use the following command:
```bash
$ pytube https://youtube.com/watch?v=2lAe1cqCOXo
```

You can also do the same for a playlist:
```bash
$ pytube https://www.youtube.com/playlist?list=PLS1QulWo1RIaJECMeUT4LFwJ-ghgoSH6n
```
<<<<<<< 4e12eb54d1ee72e41e9a7e53a3d708e300ccf661
=======

Finally, if you're filing a bug report, the cli contains a switch called ``--build-playback-report``, which bundles up the state, allowing others to easily replay your issue.

```
usage: pytube3 [-h] [--version] [--itag ITAG] [-r RESOLUTION] [-l] [-v]
               [--build-playback-report] [-c [CAPTION_CODE]] [-t TARGET]
               [-a [AUDIO]] [-f [FFMPEG]]
               [url]

Command line application to download youtube videos.

positional arguments:
  url                   The YouTube /watch or /playlist url

optional arguments:
  -h, --help            show this help message and exit
  --version             show program's version number and exit
  --itag ITAG           The itag for the desired stream
  -r RESOLUTION, --resolution RESOLUTION
                        The resolution for the desired stream
  -l, --list            The list option causes pytube cli to return a list of
                        streams available to download
  -v, --verbose         Verbosity level, use up to 4 to increase logging -vvvv
  --build-playback-report
                        Save the html and js to disk
  -c [CAPTION_CODE], --caption-code [CAPTION_CODE]
                        Download srt captions for given language code. Prints
                        available language codes if no argument given
  -t TARGET, --target TARGET
                        The output directory for the downloaded stream.
                        Default is current working directory
  -a [AUDIO], --audio [AUDIO]
                        Download the audio for a given URL at the highest
                        bitrate availableDefaults to mp4 format if none is
                        specified
  -f [FFMPEG], --ffmpeg [FFMPEG]
                        Downloads the audio and video stream for resolution
                        providedIf no resolution is provided, downloads the
                        best resolutionRuns the command line program ffmpeg to
                        combine the audio and video
```


## Development

<a href="https://deepsource.io/gh/hbmartin/pytube3/?ref=repository-badge" target="_blank"><img alt="DeepSource" title="DeepSource" src="https://static.deepsource.io/deepsource-badge-light-mini.svg"></a>
<a href="https://www.codacy.com/manual/hbmartin/pytube3?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=hbmartin/pytube3&amp;utm_campaign=Badge_Grade"><img src="https://api.codacy.com/project/badge/Grade/53794f06983a46829620b3284c6a5596"/></a>
<a href="https://github.com/ambv/black"><img src="https://img.shields.io/badge/code%20style-black-000000.svg" /></a>

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

To run code checking before a PR use ``make test``

#### Virtual environment

Virtual environment is setup with [pipenv](https://pipenv-fork.readthedocs.io/en/latest/) and can be automatically activated with [direnv](https://direnv.net/docs/installation.html)

#### Code Formatting

This project is linted with [pyflakes](https://github.com/PyCQA/pyflakes), formatted with [black](https://github.com/ambv/black), and typed with [mypy](https://mypy.readthedocs.io/en/latest/introduction.html)


#### Code of Conduct

Treat other people with helpfulness, gratitude, and consideration! See the [Python Community Code of Conduct](https://www.python.org/psf/codeofconduct/).

## GUIs and other libraries
* [YouTubeDownload](https://github.com/YouTubeDownload/YouTubeDownload) - Featured GUI frontend for pytube3
* [Pytube-GUI](https://github.com/GAO23/Pytube-GUI) - Simple GUI frontend for pytube3
* [StackOverflow questions](https://stackoverflow.com/questions/tagged/pytube)
* [PySlackers](https://pyslackers.com/web) - Python Slack group
>>>>>>> Update README.md
