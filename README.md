# Home-Security

This is an entirely DIY'ed system using off-the-shelf components and software and tied together in a sane way that makes it easy to expand or modify

## Hardware

### Cameras

Using a mix of fixed cameras (Reolink RLC-410W) and PTZ capable ones (Reolink E1 Pro, E1 Outdoor) its possible to view the cameras remotely using the Reolink application itself or with a more fine tuned option such as the Frigate NVR system.

Each camera utilizes on-board microSD cards (64GB) to store recordings locally in addition to them being stored on the NVR system providing a level of redundancy that retains recordings even if internet connectivity is interrupted.

### Sensors and Hub

Windows and doors are equipped with magnetic reed switches to detect open/close conditions, the sensors utilize the Zigbee protocol and don't rely on wifi at all. Response time under ideal conditions is measured in fractions of a second between a sensor activiating and an alert being delivered.

The Hub used is a Hubitat Elevation Model C-7 and provides communication to both Zigbee devices as well as Z-Wave which provides flexibility in chosing sensors. This device manages the sensors and presents a web interface for configuring them as well as advanced alerting, automation and more.

### Server

I run the software for this (minus the Hubitat dashboards) off a Lenovo M93p book-sized PC bought on the used market and equipped with additional RAM as well as a 1TB SSD for storage purposes, in my case I run a lot of software off of it but for a purpose built NVR system this device would be more than sufficient.

## Software

### Reolink App

The app provided by Reolink allows you to remotely view and configure cameras without any kind of a subscription. Using the app you can also review recorded events store on the cameras microSD cards and save the files to your device.

### Frigate NVR

This provides a second location for storage of recordings as well as viewing cameras in single camera views as well as a grid view. There are options for object detection, detection zones and much more.

### Tailscale Mesh VPN

While not a requirement this adds a layer of security allowing the Reolink Cameras to be denied any outbound network access and acts as a backup should there be any kind of an outage of the Reolink infrastructure which enables their app to function. 

### Pushover, ntfy.sh, etc

There are several ways to deliver notifications from the systems to personal devices such as tablets and smart phones, I personally prefer ntfy.sh because of its simplicity but there are a lot of options out there to acheive this.