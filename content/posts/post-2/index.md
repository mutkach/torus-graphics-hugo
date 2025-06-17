+++
title = "Make sheet music from any track"
date = 2025-04-17
+++

Sometimes you hear an interesting piano lead in a song or a particular [famous piano solo](https://www.youtube.com/watch?v=3MufzuaKfZg) and you want to use it for later. Or maybe you would want to study it (music theory or just for kicks). But the problem is that this particular part is nowhere to be found in a sheet music form, or rather you want to do it yourself or some reason.

Plan for today.

1. Find and download/record that track.

2. Open it in Audacity or any other music editing software that supports spectrogram view and some minor spectral editing functions (though not mandatory). If you are familiar with Fourier transforms and would like to do it all by hand (to get extra points, of course) - possibly you could use `python` with only `scipy` and `matplotlib` for spectrogram visualization. Though the current guide would be aimed at quick result even for non-professionals in signal analysis.

3. Set your spectrogram scale to linear - and limit the frequencies to, say, 50 to 2000 (that would encompass octaves 2 to 6), that lower bounds for octaves start at `16.35 Hz`, `32.70 Hz`, `65.41 Hz`, `130.81 Hz`, `261.63 Hz`, `523.25 Hz`, `1046.50 Hz`, `2093.00 Hz`, `4186.01 Hz`. Adjust your bounds respectively for a lower or a higher pitched parts. Here I set it to 1-2000hz. Also set the window size a bit higher - 4096 or 8192 for better resolution.


{{< figure src="music/image1.jpg" alt="example screenshot"  alt="screen shot" width="600" >}}

4. Find a frequency table like [this](https://mixbutton.com/music-tools/frequency-and-pitch/music-note-to-frequency-chart) or use a calculator.
5. Notice the regions that correspond to a particular note playing. 

{{< figure src="music/image2.jpg" alt="example screenshot"  alt="screen shot" width="600" >}}

Now you can "see" the notes that are played at any moment of time. You can see chords and different parts (bass, lead, vocals, etc.) Actually, there's a typo - these should be G4, B4, E5, etc. But you get the idea.

{{< figure src="music/image3.jpg" alt="example screenshot"  alt="screen shot" width="600" >}}

Of course, there are a plenty of programmatical solutions to that. Key finding is an interesing problem and many minds are working to solve it (or did it already). 

I also want to build a spectrogram myself and maybe do something like a non-maximum suppression to find peaks and their corresponding frequency. But to that I would have to figure out the reworked scipy interface to ffts and spectrograms - and why that did not work out-of-the-box for me. 


