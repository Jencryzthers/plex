###Informations
-----------
This is a Dockerfile setup for plex with plexpass - http://plex.tv/

Plex Media Server 0.9.10.3 is now available for Plex Pass users. 0.9.10.2 was too good, so we skipped it and jump directly to 0.9.10.3. 
Lot of changes under the hood here, make sure to provide feedback on things that is working in 0.9.10.1 but does not work in 0.9.10.3.

###Support
-----------
* Plex Forum: https://forums.plex.tv/

###Features 
-----------

* NEW:
	- Media server is now localized ~ http://www.getlocali...lexMediaServer/
	
* FIXES:
	- An issue shuffling all episodes.
	- Improve Cinema Trailer selection when video has unknown content rating.
	- After a network issue, the server could become unresponsive.
	- The media analysis scheduled task could make the server unresponsive.
	- When shuffling a play queue, ensure current item is at the start.
	- Transcoding subtitles which didn't exist could cause a crash.
	- Some files were not getting thumbnails during media analysis.
	- Fix transcoder to handle some MPEG files properly.
	- An issue affecting video streaming to the Android TV.
	- Some cases in which graphics (posters, art) could end up partially downloaded.
	- Make sure selected graphics are stored (could result in missing locked graphics).
	- An issue where missing metadata could result in low-resolution graphics.
	- An issue where the transcoded video could show "technicolor snow".
	- Inconsistent unwatched episode count in some cases.
	- (Windows) Fix the icon.
	- (Note QNAP ARM download is currently offering a older version, we are looking into it)

	
	
###Configurations / Install
-----------

```
docker run -d --net="host" --name="plex" -v /path/to/plex/config:/config -v /path/to/video/files:/data -v /etc/localtime:/etc/localtime:ro needo/plex
```

If you would like to specify a specific version of plex to run:

```
docker run -d --net="host" --name="plex" -v /path/to/plex/config:/config -v /path/to/video/files:/data -v /etc/localtime:/etc/localtime:ro -e VERSION=0.9.10.3.665-c9109e2 needo/plex
```

NOTE: It *must* be the full version name (i.e. 0.9.10.3.665-c9109e2 replace with the version you desire in the command above

After install go to:

http://server:32400/web/index.html#!/dashboard and login with your myPlex credentials 

###Use
-----------
* Navigate to: https://plex.tv and login with your myPlex credentials
