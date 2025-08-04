Practical `git` (under construction) (online edit help: https://dillinger.io/)
===
#### Checkout from branch (copy file)
    git checkout <otherBranch> <myFile>

#### Pull with rebase
    git pull -r
    
#### Find the commits that are not part of any branch or tag:**
    git rev-list --all --not $(git rev-list --branches --tags)

#### fsck
    git fsck

## remote:
     git remote [-v | --verbose]
     git remote add [-t <branch>] [-m <master>] [-f] [--[no-]tags] [--mirror=(fetch|push)] <name> <url>
     git remote rename <old> <new>
     git remote remove <name>
     git remote set-head <name> (-a | --auto | -d | --delete | <branch>)
     git remote set-branches [--add] <name> <branch>...
     git remote get-url [--push] [--all] <name>
     git remote set-url [--push] <name> <newurl> [<oldurl>]
     git remote set-url --add [--push] <name> <newurl>
     git remote set-url --delete [--push] <name> <url>
     git remote [-v | --verbose] show [-n] <name>...
     git remote prune [-n | --dry-run] <name>...
     git remote [-v | --verbose] update [-p | --prune] [(<group> | <remote>)...]

|Remote||||
|-|-|-|-|
| git remote rename   | | <old> <new>
| git remote remove   | | <name>
|Remote 2||||
|-|-|-|-|
| git remote set-head | | <name> | -a(--auto) / -d(--delete) / <branch> |       

|Remote||||
|-|-|-|-|
| git remote          | [-v(--verbose)] 
| git remote add      | [-t <branch>] [-m <master>] [-f] [--[no-]tags] [--mirror=(fetch/push)] | <name> <url>
| git remote rename   | | <old> <new>
| git remote remove   | | <name>
| git remote set-head | | <name> | -a(--auto) / -d(--delete) | <branch>

| Cut the end of the output: | ffmpeg -i <file.mp4> -c copy -t 00:01:33 head.mp4
| Cut the trail and the end of the output | ffmpeg -i <file.mp4> -c copy -ss 00:00:11 -t 00:01:22 middle.mp4
| Skip the input and cut the end | ffmpeg -ss 00:00:08 -i <file.mp4> -c copy -t 00:01:25 middle.mp4
