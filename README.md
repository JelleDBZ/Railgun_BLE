# Railgun 
## Made by Jelle and Jasper
Welcome to our railgun project featuring "bluetooth".
this is a simple application you can run on your raspberry pi.
you can connect with your raspberry pi with the following app.
```
https://play.google.com/store/apps/details?id=no.nordicsemi.android.mcp&hl=en
```
we will come back on this later on in the readme.

## Updates/installation

### Make sure to update apt repository index and upgrade system
```
sudo apt update
sudo apt upgrade
```
### Stop the Bluetooth daemon
```
sudo systemctl stop bluetooth
sudo systemctl disable bluetooth
```
### Install dependencies
```
sudo apt-get install bluetooth bluez libbluetooth-dev libudev-dev
```
### Setup npm package and create package.json
```
npm init
```
### Now bleno can be installed
```
cd ~/bluetooth/devices
npm install @abandonware/bleno@latest --save
```
## run the project without PM2
```
sudo node src/index.js
```
## run the project with PM2
### install PM2
```
$ npm install pm2@latest -g
# or
$ yarn global add pm2
```
### change to super user
```
sudo su
```
### start the project
```
pm2 start 'path to index.js'
```
### setup startup script
```
pm2 startup
pm2 save
```

## Testing

### Connect with your device
Open the app you've installed in the beginning of the readme.
and connect to your device, in this case it will be called: **railgun_Jelle**

once found, connect to it and start testing.
there are two characteristics, a **shoot** and **charge** characteristic.
when you call upon the characteristic it will ask for a value, simply type in an integer, select Uint8 and send.
