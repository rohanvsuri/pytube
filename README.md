
##  (24 JULY 2020) Note: Actively soliciting contributers!
Ping @ronncc if you would like to help out 

<div align="center">
  <p>
  <img src="https://github.com/nficano/pytube/blob/master/images/pytube.png?raw=true" width="350" height="328" alt="pytube logo" />
  </p>
  <p align="center">
	  <img src="https://img.shields.io/pypi/v/pytube.svg" alt="pypi">
	  <a href="https://travis-ci.org/nficano/pytube"><img src="https://travis-ci.org/nficano/pytube.svg?branch=master" /></a>
	  <a href="http://python-pytube.readthedocs.io/en/latest/?badge=latest"><img src="https://readthedocs.org/projects/python-pytube/badge/?version=latest" /></a>
	  <a href="https://codecov.io/gh/nficano/pytube"><img src="https://codecov.io/gh/nficano/pytube/branch/master/graph/badge.svg" /></a>
      <a href="https://pypi.org/project/pytube/"><img src="https://img.shields.io/pypi/dm/pytube.svg" alt="pypi"></a>
	  <a href="https://pypi.python.org/pypi/pytube/"><img src="https://img.shields.io/pypi/pyversions/pytube.svg" /></a>
    <p>
  </p>
</div>

# Call for Successor
Hello, I am unable to maintain and contribute to this project much these days. If you would like to it become the successor, please email me at nficano(at)gmail.com.

## Installation

To install from pypi with pip:

```bash
$ python -m pip install pytube
```

Sometime, the pypi release becomes slightly outdated. To install from the source with pip:

```bash
$ python -m pip install git+https://github.com/nficano/pytube
```

## Description
YouTube is the most popular video-sharing platform in the world and as a hacker you may encounter a situation where you want to script something to download videos.  For this I present to you *pytube*.

*pytube* is a lightweight library written in Python. It has no third party dependencies and aims to be highly reliable.

*pytube* also makes pipelining easy, allowing you to specify callback functions for different download events, such as  ``on progress`` or ``on complete``.

Finally *pytube* also includes a command-line utility, allowing you to quickly download videos right from terminal.

### Behold, a perfect balance of simplicity versus flexibility:

```python
 >>> YouTube('https://youtu.be/2lAe1cqCOXo').streams.first().download()
 >>> yt = YouTube('http://youtube.com/watch?v=2lAe1cqCOXo')
 >>> yt.streams
  ... .filter(progressive=True, file_extension='mp4')
  ... .order_by('resolution')
  ... .desc()
  ... .first()
  ... .download()
```

## Features
- Support for Both Progressive & DASH Streams
- Support for downloading complete playlist
- Easily Register ``on_download_progress`` & ``on_download_complete`` callbacks
- Command-line Interfaced Included
- Caption Track Support
- Outputs Caption Tracks to .srt format (SubRip Subtitle)
- Ability to Capture Thumbnail URL.
- Extensively Documented Source Code
- No Third-Party Dependencies

## Getting started

Let's begin with showing how easy it is to download a video with pytube:

```python
>>> from pytube import YouTube
>>> YouTube('https://youtube.com/watch?v=2lAe1cqCOXo').streams.first().download()
```
This example will download the highest quality progressive download stream available.

Next, let's explore how we would view what video streams are available:

```python
>>> yt = YouTube('https://youtube.com/watch?v=2lAe1cqCOXo')
>>> yt.streams
 [<Stream: itag="18" mime_type="video/mp4" res="360p" fps="30fps" vcodec="avc1.42001E" acodec="mp4a.40.2" progressive="True" type="video">,
 <Stream: itag="22" mime_type="video/mp4" res="720p" fps="30fps" vcodec="avc1.64001F" acodec="mp4a.40.2" progressive="True" type="video">,
 <Stream: itag="137" mime_type="video/mp4" res="1080p" fps="30fps" vcodec="avc1.640028" progressive="False" type="video">,
 <Stream: itag="248" mime_type="video/webm" res="1080p" fps="30fps" vcodec="vp9" progressive="False" type="video">,
 <Stream: itag="399" mime_type="video/mp4" res="None" fps="30fps" vcodec="av01.0.08M.08" progressive="False" type="video">,
 <Stream: itag="136" mime_type="video/mp4" res="720p" fps="30fps" vcodec="avc1.4d401f" progressive="False" type="video">,
 <Stream: itag="247" mime_type="video/webm" res="720p" fps="30fps" vcodec="vp9" progressive="False" type="video">,
 <Stream: itag="398" mime_type="video/mp4" res="None" fps="30fps" vcodec="av01.0.05M.08" progressive="False" type="video">,
 <Stream: itag="135" mime_type="video/mp4" res="480p" fps="30fps" vcodec="avc1.4d401e" progressive="False" type="video">,
 <Stream: itag="244" mime_type="video/webm" res="480p" fps="30fps" vcodec="vp9" progressive="False" type="video">,
 <Stream: itag="397" mime_type="video/mp4" res="None" fps="30fps" vcodec="av01.0.04M.08" progressive="False" type="video">,
 <Stream: itag="134" mime_type="video/mp4" res="360p" fps="30fps" vcodec="avc1.4d401e" progressive="False" type="video">,
 <Stream: itag="243" mime_type="video/webm" res="360p" fps="30fps" vcodec="vp9" progressive="False" type="video">,
 <Stream: itag="396" mime_type="video/mp4" res="None" fps="30fps" vcodec="av01.0.01M.08" progressive="False" type="video">,
 <Stream: itag="133" mime_type="video/mp4" res="240p" fps="30fps" vcodec="avc1.4d4015" progressive="False" type="video">,
 <Stream: itag="242" mime_type="video/webm" res="240p" fps="30fps" vcodec="vp9" progressive="False" type="video">,
 <Stream: itag="395" mime_type="video/mp4" res="None" fps="30fps" vcodec="av01.0.00M.08" progressive="False" type="video">,
 <Stream: itag="160" mime_type="video/mp4" res="144p" fps="30fps" vcodec="avc1.4d400c" progressive="False" type="video">,
 <Stream: itag="278" mime_type="video/webm" res="144p" fps="30fps" vcodec="vp9" progressive="False" type="video">,
 <Stream: itag="394" mime_type="video/mp4" res="None" fps="30fps" vcodec="av01.0.00M.08" progressive="False" type="video">,
 <Stream: itag="140" mime_type="audio/mp4" abr="128kbps" acodec="mp4a.40.2" progressive="False" type="audio">,
 <Stream: itag="249" mime_type="audio/webm" abr="50kbps" acodec="opus" progressive="False" type="audio">,
 <Stream: itag="250" mime_type="audio/webm" abr="70kbps" acodec="opus" progressive="False" type="audio">,
 <Stream: itag="251" mime_type="audio/webm" abr="160kbps" acodec="opus" progressive="False" type="audio">]
```
You may notice that some streams listed have both a video codec and audio codec, while others have just video or just audio, this is a result of YouTube supporting a streaming technique called Dynamic Adaptive Streaming over HTTP (DASH).

In the context of pytube, the implications are for the highest quality streams; you now need to download both the audio and video tracks and then post-process them with software like FFmpeg to merge them.

The legacy streams that contain the audio and video in a single file (referred to as "progressive download") are still available, but only for resolutions 720p and below.

To only view these progressive download streams:

```python
 >>> yt.streams.filter(progressive=True)
  [<Stream: itag="18" mime_type="video/mp4" res="360p" fps="30fps" vcodec="avc1.42001E" acodec="mp4a.40.2" progressive="True" type="video">,
  <Stream: itag="22" mime_type="video/mp4" res="720p" fps="30fps" vcodec="avc1.64001F" acodec="mp4a.40.2" progressive="True" type="video">]
```

Conversely, if you only want to see the DASH streams (also referred to as "adaptive") you can do:

```python
>>> yt.streams.filter(adaptive=True)
 [<Stream: itag="137" mime_type="video/mp4" res="1080p" fps="30fps" vcodec="avc1.640028" progressive="False" type="video">,
 <Stream: itag="248" mime_type="video/webm" res="1080p" fps="30fps" vcodec="vp9" progressive="False" type="video">,
 <Stream: itag="399" mime_type="video/mp4" res="None" fps="30fps" vcodec="av01.0.08M.08" progressive="False" type="video">,
 <Stream: itag="136" mime_type="video/mp4" res="720p" fps="30fps" vcodec="avc1.4d401f" progressive="False" type="video">,
 <Stream: itag="247" mime_type="video/webm" res="720p" fps="30fps" vcodec="vp9" progressive="False" type="video">,
 <Stream: itag="398" mime_type="video/mp4" res="None" fps="30fps" vcodec="av01.0.05M.08" progressive="False" type="video">,
 <Stream: itag="135" mime_type="video/mp4" res="480p" fps="30fps" vcodec="avc1.4d401e" progressive="False" type="video">,
 <Stream: itag="244" mime_type="video/webm" res="480p" fps="30fps" vcodec="vp9" progressive="False" type="video">,
 <Stream: itag="397" mime_type="video/mp4" res="None" fps="30fps" vcodec="av01.0.04M.08" progressive="False" type="video">,
 <Stream: itag="134" mime_type="video/mp4" res="360p" fps="30fps" vcodec="avc1.4d401e" progressive="False" type="video">,
 <Stream: itag="243" mime_type="video/webm" res="360p" fps="30fps" vcodec="vp9" progressive="False" type="video">,
 <Stream: itag="396" mime_type="video/mp4" res="None" fps="30fps" vcodec="av01.0.01M.08" progressive="False" type="video">,
 <Stream: itag="133" mime_type="video/mp4" res="240p" fps="30fps" vcodec="avc1.4d4015" progressive="False" type="video">,
 <Stream: itag="242" mime_type="video/webm" res="240p" fps="30fps" vcodec="vp9" progressive="False" type="video">,
 <Stream: itag="395" mime_type="video/mp4" res="None" fps="30fps" vcodec="av01.0.00M.08" progressive="False" type="video">,
 <Stream: itag="160" mime_type="video/mp4" res="144p" fps="30fps" vcodec="avc1.4d400c" progressive="False" type="video">,
 <Stream: itag="278" mime_type="video/webm" res="144p" fps="30fps" vcodec="vp9" progressive="False" type="video">,
 <Stream: itag="394" mime_type="video/mp4" res="None" fps="30fps" vcodec="av01.0.00M.08" progressive="False" type="video">,
 <Stream: itag="140" mime_type="audio/mp4" abr="128kbps" acodec="mp4a.40.2" progressive="False" type="audio">,
 <Stream: itag="249" mime_type="audio/webm" abr="50kbps" acodec="opus" progressive="False" type="audio">,
 <Stream: itag="250" mime_type="audio/webm" abr="70kbps" acodec="opus" progressive="False" type="audio">,
 <Stream: itag="251" mime_type="audio/webm" abr="160kbps" acodec="opus" progressive="False" type="audio">]
```

You can also interact with Youtube playlists:

```python
>>> from pytube import Playlist
>>> pl = Playlist("https://www.youtube.com/watch?v=Edpy1szoG80&list=PL153hDY-y1E00uQtCVCVC8xJ25TYX8yPU")
>>> for video in pl.videos:
>>>     video.streams.first().download()
```

Pytube allows you to filter on every property available (see the documentation for the complete list), let's take a look at some of the most useful ones.

To list the audio only streams:

```python
>>> yt.streams.filter(only_audio=True)
  [<Stream: itag="140" mime_type="audio/mp4" abr="128kbps" acodec="mp4a.40.2" progressive="False" type="audio">,
  <Stream: itag="249" mime_type="audio/webm" abr="50kbps" acodec="opus" progressive="False" type="audio">,
  <Stream: itag="250" mime_type="audio/webm" abr="70kbps" acodec="opus" progressive="False" type="audio">,
  <Stream: itag="251" mime_type="audio/webm" abr="160kbps" acodec="opus" progressive="False" type="audio">]
```

To list only ``mp4`` streams:

```python
>>> yt.streams.filter(subtype='mp4').all()
 [<Stream: itag="18" mime_type="video/mp4" res="360p" fps="30fps" vcodec="avc1.42001E" acodec="mp4a.40.2" progressive="True" type="video">,
 <Stream: itag="22" mime_type="video/mp4" res="720p" fps="30fps" vcodec="avc1.64001F" acodec="mp4a.40.2" progressive="True" type="video">,
 <Stream: itag="137" mime_type="video/mp4" res="1080p" fps="30fps" vcodec="avc1.640028" progressive="False" type="video">,
 <Stream: itag="399" mime_type="video/mp4" res="None" fps="30fps" vcodec="av01.0.08M.08" progressive="False" type="video">,
 <Stream: itag="136" mime_type="video/mp4" res="720p" fps="30fps" vcodec="avc1.4d401f" progressive="False" type="video">,
 <Stream: itag="398" mime_type="video/mp4" res="None" fps="30fps" vcodec="av01.0.05M.08" progressive="False" type="video">,
 <Stream: itag="135" mime_type="video/mp4" res="480p" fps="30fps" vcodec="avc1.4d401e" progressive="False" type="video">,
 <Stream: itag="397" mime_type="video/mp4" res="None" fps="30fps" vcodec="av01.0.04M.08" progressive="False" type="video">,
 <Stream: itag="134" mime_type="video/mp4" res="360p" fps="30fps" vcodec="avc1.4d401e" progressive="False" type="video">,
 <Stream: itag="396" mime_type="video/mp4" res="None" fps="30fps" vcodec="av01.0.01M.08" progressive="False" type="video">,
 <Stream: itag="133" mime_type="video/mp4" res="240p" fps="30fps" vcodec="avc1.4d4015" progressive="False" type="video">,
 <Stream: itag="395" mime_type="video/mp4" res="None" fps="30fps" vcodec="av01.0.00M.08" progressive="False" type="video">,
 <Stream: itag="160" mime_type="video/mp4" res="144p" fps="30fps" vcodec="avc1.4d400c" progressive="False" type="video">,
 <Stream: itag="394" mime_type="video/mp4" res="None" fps="30fps" vcodec="av01.0.00M.08" progressive="False" type="video">,
 <Stream: itag="140" mime_type="audio/mp4" abr="128kbps" acodec="mp4a.40.2" progressive="False" type="audio">]
```

Multiple filters can also be specified:

```python
>>> yt.streams.filter(subtype='mp4', progressive=True).all()
>>> # this can also be expressed as:
>>> yt.streams.filter(subtype='mp4').filter(progressive=True).all()
  [<Stream: itag="18" mime_type="video/mp4" res="360p" fps="30fps" vcodec="avc1.42001E" acodec="mp4a.40.2" progressive="True" type="video">,
  <Stream: itag="22" mime_type="video/mp4" res="720p" fps="30fps" vcodec="avc1.64001F" acodec="mp4a.40.2" progressive="True" type="video">]
```
You also have an interface to select streams by their itag, without needing to filter:

```python
>>> yt.streams.get_by_itag(22)
  <Stream: itag="22" mime_type="video/mp4" res="720p" fps="30fps" vcodec="avc1.64001F" acodec="mp4a.40.2" progressive="True" type="video">
```

If you need to optimize for a specific feature, such as the "highest resolution" or "lowest average bitrate":

```python
>>> yt.streams.filter(progressive=True).order_by('resolution').desc().all()
  [<Stream: itag="22" mime_type="video/mp4" res="720p" fps="30fps" vcodec="avc1.64001F" acodec="mp4a.40.2" progressive="True" type="video">,
  <Stream: itag="18" mime_type="video/mp4" res="360p" fps="30fps" vcodec="avc1.42001E" acodec="mp4a.40.2" progressive="True" type="video">]
```
Note that ``order_by`` cannot be used if your attribute is undefined in any of the Stream instances, so be sure to apply a filter to remove those before calling it.

If your application requires post-processing logic, pytube allows you to specify an "on download complete" callback function:

```python
 >>> def convert_to_aac(stream, file_handle):
         return  # do work

 >>> yt.register_on_complete_callback(convert_to_aac)
```

Similarly, if your application requires on-download progress logic, pytube exposes a callback for this as well:

```python
 >>> def show_progress_bar(stream, chunk, file_handle, bytes_remaining):
         return  # do work

 >>> yt.register_on_progress_callback(show_progress_bar)
```

## Command-line interface

pytube also ships with a tiny cli interface for downloading and probing videos.

Let's start with downloading:

```bash
$ pytube http://youtube.com/watch?v=2lAe1cqCOXo --itag=22
```
To view available streams:

```bash
$ pytube http://youtube.com/watch?v=2lAe1cqCOXo --list
```

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
