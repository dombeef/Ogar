# agar-clone

## Introduction
This is a clone of agar.io. In this project we aim to acheive the following. 

- [x] Hack main_out.js and make the variables and function names readable. Now most of the variable and function name should make sense. 
- [x] Add uploading custom skins features (Done)
- [ ] Add mobile device support (On-going)
- [ ] Add in-game chat feature. (On-going)
- [ ] Support multi-server feature (On-going)


##Setup

You can use nginx that support PHP to deploy it on your server. 

### Support your server
Replace the CONNECTION_URL with your own ip and port in main_out.js

###Upload feature
The upload module does two things. The first is to upload a skin onto skins folder. The second is that the client request the server to run checkdir.php every 15 seconds to check what skins are uploaded and add them into knownNameDict. Then the skins can be loaded. 

To make this feature work, you need to give upload.php priviliage to read skins folder. 


``` 
chmod 777 skins 
```

will make it work.


## Test and known issues

This client has been tested on LEMP stack on OS X 10.10 and Ubuntu 14.04 with server side [Ogar](https://github.com/vram4/Ogar).

It is known that some of the variables and function names still make no sense, we are working on that. 

## Protocol extensions
As the server has to tell whether the client supports protocol extensions, the values of package 254 and 255 have been adjusted.
Package 255 now contains "Ogar" in ASCII (1332175218) while package 254 contains the version number. When modifying the protocol,
only new features can be implemented. Also, the client must remain compatible with older versions of the server.

Original protocol can be found [here](https://github.com/vram4/Agar.io-Protocol). Changes to the protocol have to be [documented](PROTOCOL.md).

## Contribution
Pull Request are welcome. 
