<pre>
sudo docker run -e "EMULATOR=android-22" -e "ARCH=x86" -d -P -p 5900:5900 -p 5555:5555 --name android tracer0tong/android-emulator

Doing a adb kill-server on the host imediatelly followed by an adb connect ip on the remote machine did the trick.

adb reverse tcp:8081 tcp:8081

adb shell input keyevent 82

adb shell input text "RR"
</pre>