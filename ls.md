ls - list directory contents
====
ls [OPTION]... [FILE]...

#### Long listing, time-related options
|Short|Desc|Common Mistake|Note|'find' Note<br>(See: 'stat')|
|-|-|-|-|-|
|ls -l<br>ls -l --time=mtime |Show mtime (last modification time) |(NOT **ls -lm**, which is different)|Sort by name (default)|With find: -mtime
|ls -lc<br>ls -l --time=ctime|Show ctime (last status change t.)  |                                    |Sort by name (default)|With find: -ctime
|ls -lu<br>ls -l --time=atime|Show atime (last access time)       |(NOT **ls -la**, which is different)|Sort by name (default)|With find: -atime
||
|ls -lt, ls -lrt   ||Show and sort by mtime
|ls -ltc, ls -lrtc ||Show and sort by ctime
|ls -ltu, ls -lrtu ||Show and sort by atime
