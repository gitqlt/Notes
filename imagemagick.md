imagemagick: Image manipulation programs
====

**Add 'CreateDate' annotation**

    $ Img=...; dTxt=$(exiftool -CreateDate -s -s -s $Img)
    $ convert $Img -pointsize 96 -fill white -gravity northeast -annotate +100+100 "$dTxt" \
      -gravity southeast -annotate +100+100 "$dTxt" dated${Img}
      
**Iiii**

    $ iii
