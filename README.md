"# cut60seconds" 



## FFMPEG command for cutting into 60 seconds 
Command ffmpeg -i audio.wav -f segment -segment_time 60 -c copy out%03d.wav

## Combine transcripts 

$transcript = ConvertFrom-Json (get-content C:\temp\text.json -Raw)
$transcript.AudioFileResults.SegmentResults | ForEach-Object {write-output "$($_.Offset/10000000): $($_.NBest.Display)"} > c:\temp\pretty.txt
