# RTP
gst-launch-1.0 -v videotestsrc ! x264enc ! rtph264pay ! udpsink host=192.168.0.114 port=1234

# SRTP
gst-launch-1.0 -v videotestsrc ! x264enc ! rtph264pay ! application/x-rtp,payload=(int)103 ! srtpenc key="756e4d4d646b5979756f784645565353495a646a7653534c6d56327935476c3038484d4f335a5730663474596375" rtp-cipher="aes-256-icm" rtp-auth="hmac-sha1-80" ! udpsink host=192.168.0.144 port=1234
