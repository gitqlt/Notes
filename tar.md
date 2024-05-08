tar practical
===
**Get list of names to archive from standard input**

    $  git ls-files             | tar -czvf /tmp/project.tar.gz -T - 
    $  ls -dp .* | grep -v '/$' | tar -czvf /tmp/dot.tar.gz     -T - 
**exclude pattern when directory** (do not use trailing / in the pattern)

    $  ls -dp .c* | grep '/$'   | tar --exclude '*cache*' --exclude '*con*' -czvf /tmp/dotc.tar.gz -T -
