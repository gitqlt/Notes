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

**Rotete video, sets metadata only;** display_rotation: 0 90 180 270

    $ ffmpeg -display_rotation 90 -i input.mp4 -codec copy output.mp4

 **Rotete video, re-encode video**
 
    $ ffmpeg -i <input> -vf "transpose=X" new.<inp>
|| Transpose=X |
|-|-|
| 90d counterclockwise and vertical flip (default)| X: 0 |
| 90d clockwise                                   | X: 1 |
| 0d counterclockwise                             | X: 2 |
| 90d clockwise and vertical flip                 | X: 3 |

