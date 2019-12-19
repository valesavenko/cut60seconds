"# cut60seconds" 


Command ffmpeg -i audio.wav -f segment -segment_time 60 -c copy out%03d.wav
