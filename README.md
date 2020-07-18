# Interestingness
Generates a graph with a timeline of how "interesting" a video is.

### How does it work?
Modern video encoding (at least for mpeg, make sure your video is an mp4/mkv!) ensures the least amount of data is kept as possible. This is achieved with I frames (full images) and P/B frames (only data about pixels changes since last image). [Read more](https://en.wikipedia.org/wiki/Video_compression_picture_types).

By substituting I frame sizes with the previous and next P/B frame, we get a series of numbers that plot the "action" of a video, or, more technically, how shaky the camera is / how much the scene is changing.

### Dependencies
* \*nix with Bash
* Python >= 3.5
* pandas, matplotlib (`pip install pandas matplotlib`)
* pv, ffprobe (`sudo apt install pv ffprobe`)

### Example
Here's the interestingness graph for the [Bee Movie Trailer](https://www.youtube.com/watch?v=VONRQMx78YI):
`./interestingness trailer.mp4`
![Example](https://raw.githubusercontent.com/Harrison-Mitchell/Interestingness/master/example.png "Example")