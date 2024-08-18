# Radio Metadata Fetcher

This PHP script fetches and displays the current song metadata from a streaming radio URL. It retrieves the song title, artist, and album art using various APIs.

## Description

This script is designed to connect to a streaming radio URL and extract metadata about the currently playing song. It supports retrieving album art from iTunes and Deezer APIs.

## Features

- Fetches current song title and artist.
- Retrieves album art from iTunes and Deezer.
- Returns metadata in JSON format.

## Usage

1. **Upload the Script**

   Place the `radio-metadata-api.php` file on your server.

2. **Make a Request**

   Access the script via a web browser or a tool like `curl` with the following query parameter:
   http://yourserver.com/radio-metadata-api.php?stream-url=<your-stream-url>


Replace `<your-stream-url>` with the URL of the streaming radio you want to get metadata from.

3. **Response Format**

The response is returned in JSON format. For example:

json
{
  "current_track": {
    "title": "Song Title",
    "artist": "Artist Name",
    "album_art_url": "http://example.com/path/to/album/art.jpg"
  }
}

* If there is an error, the response will be:
json
{
  "error": "Failed to fetch metadata."
}

* Code Overview
getRadioMetadata($stream_url): Fetches and parses metadata from the provided stream URL.

splitTitleAndArtist($current_song): Splits the song title and artist based on common delimiters.

fetchUrl($url): Fetches content from a URL using cURL.

getAlbumArt($title, $artist): Retrieves album art from iTunes and Deezer APIs.

* PHP 5.4 or higher.
cURL extension enabled in PHP.

* License
This script is provided under the MIT License. Feel free to modify and use it as needed.
