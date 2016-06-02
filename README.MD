

###DCIT Test data
This is just a repo of test data. It can be used to populate [DCIT](https://github.com/HyperSprite/dcit) with enough data to make it interesting.

A running example of this data can be found here: [dcit.hypersprite.com](http://dcit.hypersprite.com)

```js
mongorestore -h localhost -d dcit-test dump/dcit-test
```

If you have not setup DCIT, take a look at the [wiki](https://github.com/HyperSprite/dcit/wiki) for configuration information. Once you are setup, go ahead and start DCIT in test mode to use this data.

```js
NODE_ENV=test node dcit.js
```

Now open [```http://localhost:3000```](http://localhost:3000)

You should be redirected to an ```https```  warning, this is because the cert is self generated, the error can be ignored, click ```ok``` or ```accept``` and proceed.

On first start up, you will need to make a new root user, go take a look at the [wiki](https://github.com/HyperSprite/dcit/wiki/3.---Users-and-Options) for that.

You should now be looking at the DCIT home page.
###Data Centers
To get started you can click the DCIT drop down in the upper left corner and select Data Centers.
This will give you a list of Data Centers, go ahead and pick ```San Francisco Data Centers Inc. - sf01```
You are now on the Data Center overview page.
Here you can see the production servers overview, not all that interesting with only one environment.

Contacts: a convenient place to store all of your data center contacts and nearby restaurants, hotels and airports.

Cages: these could be rooms, cages, a set of stand alone cabinets, it is really just a unit of space to put your racks. In this example, there are links to google drawings of the data center floor plans.

Racks: As explained in the [wiki](https://github.com/HyperSprite/dcit/wiki/4.-Data-Centers) these are not so much racks as rack position place holders. Assuming you are logged in with root, you probably noticed the edit and copy icons. These are the same icons used throughout for these functions. If you need to make a copy of a rack, just click the copy button and a form with many of the vital stats will open.

Networks: Here we define our networks, not only is it handy to have, it is also used for configuration data.

Power: this is not yet fully implemented.

###Exploring a Rack
Going back to the Racks table, click on ```sf01_01_1524```. You will see the rack vitals on the left and a drawing of the rack elevation on the right. Hovering over any of the equipment will display a few tidbits but it's not the fastest way to dig deeper. For details, click on details in the center of the nav bar, you will see a report for all of the gear in this rack.
You are now looking at the report format for most of DCIT with Location, System and Equipment information.

###A System
Go ahead and click on ```con-sf01-1524-01``` and the System Details page for this console server will open.

The System in what makes our Equipment unique. No other System will have the same name and port configuration.

This page contains just about everything you might want to know about this System as the text for the change management port config ticket, serial console server setup and in this case, a custom bare metal configuration for this console server. This is where that network data we entered earlier comes in handy.

Scroll back up and click ```Show connected ports``` and you will see all of the devices plugged into this console server and the port configuration scripts that can be used to configure this console for those ports.

From here, lets click on ```sf01-db1022``` (should be the last one on the list). Again we have the same format, although instead of a bare metal config, we have the ILOM config at the bottom of the page. We can also quickly reference all of the port data and software.

The thing is, Systems are only half of the story, we also have Equipment. Lets look at that next.

###Equipment
Click on the Equipment SN ```XPREE97341``` found in the top center of the details area of the page. This will take you to the Equipment page for this System. Notice they are separate entities. This is because often times, Equipment are exchanged out from under Systems. So the key to this is: **Equipment are placed in Locations, and Systems are placed on Equipment**.

You will notice our equipment is where we track the hardware. Most of this stuff will not change for the life of the server although we can edit it at any time. I intentionally did not go into inventorying every stick of ram etc, because there is a limit to how much can be successfully inventoried. At some point you spend more time counting it than you do installing it and keeping it running.






