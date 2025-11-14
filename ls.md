ls - list directory contents
====
ls [OPTION]... [FILE]...

#### Long listing, time-related options
|Short|Long|Desc|Note||
|-|-|-|-|-|
|ls -l |ls -l --time=mtime|Show mtime (last modification time) |(NOT **ls -lm**, which is different)|Sort by name (default)
|ls -lc|ls -l --time=ctime|Show ctime (last status change time)|                                    |Sort by name (default)
|ls -lu|ls -l --time=atime|Show atime (last access time)       |                                    |Sort by name (default)
||
|ls -lt, ls -lrt   ||Show and sort by mtime
|ls -ltc, ls -lrtc ||Show and sort by ctime
|ls -ltu, ls -lrtu ||Show and sort by atime
