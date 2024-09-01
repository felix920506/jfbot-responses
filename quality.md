The quality selector on most/all clients will only trigger a transcode if you select a value lower than the video's native bit rate.  Selecting a higher bit rate does not increase the resolution, upscale, or increase the quality of a video.
The resolution in the "quality" selection is not strict.  There is additional logic on the server that determines the output resolution.
For example: You have a video with a combined audio+video bit rate of 10Mbps that your client is direct playing.  If you select 20Mbps nothing will happen.  But selecting "720P - 8Mbps" will trigger a transcode.
