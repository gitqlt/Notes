Transform video
====

**Cut video (timing in sec)**

    $ ffmpeg -i <input> -c copy -ss <skip> -t <length> new.<inp>
    $ ffmpeg -ss <skip> -i <input> -c copy -t <length> new.<inp>

|Examples||
|-|-|
| Cut the end of the output: | ffmpeg -i <file.mp4> -c copy -t 00:01:33 head.mp4
| Cut the trail and the end of the output | ffmpeg -i <file.mp4> -c copy -ss 00:00:11 -t 00:01:22 middle.mp4
| Skip the input and cut the end | ffmpeg -ss 00:00:08 -i <file.mp4> -c copy -t 00:01:25 middle.mp4

**Rotete video, sets metadata only**

    $ ffmpeg -display_rotation <deg> -i input.mp4 -codec copy output.mp4
    display_rotation: degree, counterclockwise

 **Rotete video, re-encode video**
 
    $ ffmpeg -i <input> -vf "transpose=X" new.<inp>
    X0: 90d counterclockw. +vert.flip (default);  X1: 90d clockw.
    X2: 90d counterclockw;                        X3: 90d clockw. +vert.flip

**Concat videos (concat demuxer, no re-encode)**

    $ ffmpeg -f concat -safe 0 -i <( printf "file `pwd`/%s\n" file1.mp4 file2.mp4 ) -c copy ccat.mp4
