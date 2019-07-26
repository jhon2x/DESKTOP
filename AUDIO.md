https://www.youtube.com/watch?v=gKsBAEnVxEA
How to enable noise cancellation on Linux Ubuntu, echo-canceled feature 

=====================================
$ sudo nano /etc/pulse/default.pa

### Enable Echo/Noise-Cancelation
load-module module-echo-cancel aec_method=webrtc aec_args="analog_gain_control=0 digital_gain_control=1" source_name=echoCancel_source sink_name=echoCancel_sink
set-default-source echoCancel_source
set-default-sink echoCancel_sink

-----------------------------------------------------------------------
To stop and restart the pulse audio

$ pulseaudio -k
$ pulseaudio --start

====================================


linux active noise cancellation,
pulseaudio noise cancellation,
module-echo-cancel,
ubuntu microphone background noise,
pulseaudio webrtc,
reload pulseaudio,
linux echo cancellation,
linux echo cancellation software, 
echo-canceled