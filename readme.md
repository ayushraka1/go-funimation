Note: This method no longer works since Funimation [updated their website](https://www.funimation.com/blog/2016/09/23/funimationnow-discover-an-extraordinary-user-experience/) in October 2016

# Funimation Downloader

Download videos from funimation!

## Basic Usage

The following command will download the first episode of **Steins; Gate** at the highest quality that is publicly viewable

```
funimation download steins-gate 1
```

## Installation

### Via `go get`

In your command line, with the latest version of go installed, you can simply use the following command:

```
go get golang.ssttevee.com/funimation
```

### anual Install

Download one of the prebuilt executables, and extract it to somewhere that is in your environment path variable

## Advanced Usage

###Terminology

The `{episode-url}` is the url of an episode

The `{series-num}` is the id of a series, arbitrarily assigned by funimation (not publicly visible)

The `{episode-num}` is the nth episode in a series

The `{series-tag}` is the url slug of a series

The `{episode-tag}` is the url slug of an episode in a series

#### Clarification
Given the following `{episode-url}`: `http://www.funimation.com/shows/steins-gate/videos/official/turning-point`

The `{series-tag}` is _steins-gate_

The `{episode-tag}` is _turning-point_

### Command Variants

#### List

Lists every episode in the series as well as their language and bitrate availability

```
funimation list {series-tag}
```

#### Download

Download one or more episodes of a series

```
funimation download [options] {episode-url} ...
```
```
funimation download [options] {series-tag} {episode-tag} ...
```
```
funimation download [options] {series-tag} {episode-num} ...
```
```
funimation download [options] {series-num} {episode-num} ...
```

Note: The ellipsis (`...`) means the multiple of the last argument may be added to the end to download multiple episodes consecutively

##### Options

`-email <email address>` your funimation account email address

`-password <password>` your funimation account password

`-quality <quality>` the video quality to download at; either sd, hd, or fhd (default "max")

`-language <language>` either sub or dub

`-url-only` shows the url instead of downloading it

`-threads <threads>` the number of threads for a multithreaded download

### Batching

The `{episode-num}` or `{episode-tag}` may be replace with an asterisk (`*`) to download all episodes in a series as well as a range of episodes (i.e. `1-4` or `6-24`).
