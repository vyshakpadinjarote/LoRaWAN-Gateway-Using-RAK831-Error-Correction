# LoRaWAN-Gateway-Using-RAK831-Error-Correction
Could not register gateway a gateway with id eui-b827ebfffeb836ac already exists

## [Do the following to Create a LoRaWAN Gateway using RAK831](https://github.com/vyshakpadinjarote/LoRa-Gateway-using-RAK831) :
1. Download the Raspberry OS and Etcher.
2. Burn to the Memory Card.
3. Connect all the components and insert the SD card.
4. Run the Raspberry Pi.
5. Go through the required commands.
6. Create account in TTN.
7. Register gateway.
8. Gateway is ready to use.

## During these process there will be a chance to receive an error or warning like:
```Detected EUI XX:XX:XX:XX:XX:XX:XX:XX from eth0```

While this is your error you can't register your gateway. So the possible solution is that you can change your MAC Address and create or register your gateway.

## Procedures
While the terminal is asking you to do an overwrite press ```y``` and ```Enter```.

After that navigate your terminal to the following directory using the ```cd /opt/ttn-gateway/bin/``` command.

Open the file in command line editor such as ```sudo nano local_conf.json```

Now take another terminal and run the following set of commands one by one.
```
git clone https://github.com/things-nyc/random-eui64.git
cd random-eui64/
make random-eui64
```

We are almost done with the codes and now run the command ```./random-eui64 | tr -d '-'``` in the same terminal just now where you downloaded the git. Now your terminal will show you one random MAC Address, just copy the address you recieved now and goto the previous terminal.

So you are inside the file ```local_conf.json``` and you can copy paste the address where the old one is present and now press ```ctrl + X``` and press ```Y``` now press ```Enter```.

Now do the remaining processes like registering your gateway in TTN Console and don't forget that you need to use the MAC Address that you stored in the ```local_conf.json```.

Finally you have your gateway Live now.
