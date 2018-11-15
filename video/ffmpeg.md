# RTSP -> RTMP
ffmpeg -rtsp_transport tcp -i rtsp://root:password@192.168.0.108/live.sdp -c:v copy -c:a aac -f flv rtmp://192.168.0.101/live/test

# RTSP -> HLS
ffmpeg -rtsp_transport tcp -i rtsp://root:password@192.168.0.108/live.sdp -c:v copy -c:a aac -hls_allow_cache 0 -hls_list_size 30 -hls_time 60 -use_localtime 1 -hls_segment_filename %Y%m%d-%H-%M_%S.ts live.m3u8

# RTSP -> RTP
ffmpeg -rtsp_transport tcp -i rtsp://root:password@192.168.0.115/live.sdp -c:v copy -an -f rtp rtp://127.0.0.1:1234

save SDP info to sdp file and open sdp file by VLC


# MacOS
ffmpeg -f avfoundation -list_devices true -i ""

ffmpeg -f avfoundation -framerate 30 -i "0:0" out.avi

# Video Capture to SRTP
ffmpeg -f avfoundation -framerate 30 -i "0:" -c:v h264 -strict -2 -srtp_out_suite AES_CM_128_HMAC_SHA1_80 -srtp_out_params l37rfafaE1zXMpXOYdSlx/2+M60MSRZDpqUQo+qp -f rtp srtp://192.168.0.115:1234

# Audio Capture to RTP
ffmpeg -f avfoundation -i ":0" -c:a aac -strict -2 -f rtp rtp://192.168.0.115:1234

# Play audio RTP to ALSA
ffmpeg -nomsgq -v error -i /tmp/audio.sdp -f alsa -ac 1 hw:0,0

# RTP Payload type 96
-payload_type 96