# Hacker Tips #
This page gives few tips to ease your life when using the WebIOPi application and framework.

## Create a dedicated folder for your project ##
Typically in your home folder (**/home/pi/myproject**)

---


## Don't edit orignal HTML files, make copies and use doc-root configuration instead ##
To be able to use default web apps and debug your circuits

---


## Launch WebIOPi foreground to debug your scripts and REST calls ##
```
sudo webiopi -d -c /etc/webiopi/config
```

---


## Use a decent powered computer ##
To edit your project files and access Internet documentations.

---


## Use your Pi headless ##
Learn on how to use SSH to remotely administrate your Pi.

---


## Use network shares to edit files ##
Instead of uploading files repeatedly on your Pi, you can remotely edit files, like if they was on your computer. If you are on Windows, install Samba on your Pi. If your are on Mac, install Netatalk instead.

---


## Write you Javascript code in a separated file ##
Put all your Javascript code inside a separated **script.js** file, next to your **index.html**. Then use `<script>` tag in **index.html**.
```
<html>
<head>
    <title>My WebIOPi application</title>
    <script type="text/javascript" src="/webiopi.js"></script>
    <script type="text/javascript" src="script.js"></script>
</head>
<body>
...
</body>
</html>
```
Take note of the heading slash used to load webiopi.js but not for script.js.

---


## Write you CSS code in a separated file ##
Put all your CSS code inside a separated **style.css** file, next to your **index.html**. Then use `<link>` tag in **index.html**.
```
<html>
<head>
    <title>My WebIOPi application</title>
    <script type="text/javascript" src="/webiopi.js"></script>
    <script type="text/javascript" src="script.js"></script>
    <link rel="stylesheet" type="text/css" href="style.css">
</head>
<body>
...
</body>
</html>
```

---


## Look on jQuery documentation ##
[jQuery](http://api.jquery.com/) is the library used in the Javascript/HTML part with many function to help modifying the UI. There is also plenty examples on Internet.

---
