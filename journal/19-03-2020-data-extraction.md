19-03-2020-data-extraction.md

Finally extracted all keypoints from 84 flacks and 96 backflips.

The total amount of files generated is 19 119.

~319 sec = 5 min 19 sec backflips and flacks

Average frame processing time on an Amazon GPU instance was 0.08 sec. This is nothing comparing to the processing time on my personal MacBook Pro with the processing time of ~30 sec per frame.

So the total time for processing on an Amazon GPU instance was 19 199 * 0.08 = 1529.52 sec => 25 min 30 sec

Compared to Mac Pro 19 199 * 30 = 573570 sec => 9559 min 30 sec => 159 h => 6 days 15h

This means that Amazon GPU is 375x faster than my Mac. :)