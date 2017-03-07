## Raspberry Pi Notes

Setting up the Raspberry Pi is sometimes painful, because you need a keyboard, and a mouse to connect to WiFi. I never wanted to use the Pi as a computer, I just wanted to use it as a server. Luckily, I can just connect the Pi to the network via the Ethernet cable - no need to set up the WiFi. It is possible to set the device to connect to a dedicated IP, but I found looping through the IP's in the local network more useful. Here's a snippet how I do it:

    IPS=arp -a | awk -F'[ ()]' '{OFS=";"; print $3}'
    for LINE in $IPS; do ssh "pi@$LINE" done

This repo is a collection on tricks, how-to-s, links for playing with a Raspberry Pi. First I'm just gonna throw a bunch of commands here, I'll break it down when it makes sense.
