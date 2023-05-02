Transform video
====

**Cut video (timing in sec)**

    $ ffmpeg -i <input> -c copy -ss <skip> -t <length> new.mp4
    $ ffmpeg -ss <skip> -i <input> -c copy -t <length> new.mp4

|Examples||
|-|-|
| Cut the end of the output: | ffmpeg -i <file.mp4> -c copy -t 00:01:33 head.mp4
| Cut the trail and the end of the output | ffmpeg -i <file.mp4> -c copy -ss 00:00:11 -t 00:01:22 middle.mp4
| Skip the input and cut the end | ffmpeg -ss 00:00:08 -i <file.mp4> -c copy -t 00:01:25 middle.mp4

