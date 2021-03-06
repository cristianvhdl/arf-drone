First time quadcopter build
===========================

**Goal:** I wanted to go from knowing nothing about remote control vehicles to building a quadcopter that could complete a route autononmously, i.e. without human control from the ground. I wanted as few black box elements as possible in the system and so used open source software and hardware wherever reasonably possible.

TODO: include photo of final build here.

Having some experience with hobbyist electronics projects I initially thought that I'd really be able to make a quadcopter from scratch, 3D printing elements of the frame, sourcing most of the components, like motors, as generic parts from a big distributor like Digi-Key, and only having to buy a few drone-specific components like propellars.

I was quite disappointed when I found various pages (such as [this one](http://ardupilot.org/copter/docs/build-your-own-multicopter.html) from ArduPilot) making clear that this wasn't an option to consider when making ones first drone. Apparently I'd have to start with what's referred to as an ARF (almost ready to fly) kit, i.e. an unassembled frame and the parts for the propulsion system (propellars, motors etc.).

The ARF acronym makes it sound like all the interesting work has been taken care of and all that's left is to put things together lego style. But it turns out, if starting from scratch with no prior experience of drones, that there's quite enough additional complexity without also having to worry about the frame and the propulsion system.

Important: this build requires a small amount of soldering and it's assumed you've already got a soldering iron, solder etc.

TODO: add summary explaining that this page covers parts and that there are other pages - [`notes.md`](notes.md), [`stores.md`](stores.md), [`purchase-order.md`](purchase-order.md) and [`assembly.md`](assembly.md). Fill out [`assembly.md`](assembly.md) file properly.


Parts
-----

So what other parts do you need besides a frame and a propulsion system? The list of parts below makes clear that there's quite a bit more to this whole thing.

An approximate price in Euros has been given for every item (even though I bought most items in the UK or Switzerland). As you can see the most expensive items are the propulsion system, flight controller and transmitter. The batteries (especially if you buy two in order to have one in reserve) and charger also add a significant cost.

Each part is listed with one or more links to either a product page or a shop page that provides details about the part (in the case of shop pages I chose pages that provided the best description and not necessarily the shop from which I bought the given part).

I've put together a separate page - [`stores.md`](stores.md) - which includes links to sites that carry the parts shown here.

Various acronyms used in the parts list, like ESC and PDB, are explained later in this pages or on one of the other pages here.

### Major components

| Price | Description |
|-------|-------------|
| &euro;24 | <img width="128" src="images/f450-frame-3.jpg"> <img height="128" src="images/f450-frame-1.gif"> <img width="128" src="images/f450-frame-4.jpg"><br>F450 frame - the basic platform to which everything else is attached ([link 1](https://www.amainhobbies.com/dji-flame-wheel-f450-basic-quadcopter-drone-kit-dji-fw450bas/p235233), [link 2](http://www.builtdrones.com/dji-flamewheel-f450-basic-kit/)).
| &euro;150 | <img height="128" src="images/e305-quad-propulsion-system.jpg"><br>E305 propulsion system - propellars, motors and ESCs ([link](http://store.dji.com/product/e305-4)).
| &euro;175 | <img width="128" src="images/pixhawk-1.jpg"> <img height="128" src="images/pixhawk-3.jpg"><br>Pixhawk flight controller - the "brains" of the system ([link](https://pixhawk.org/modules/pixhawk)).
| &euro;41 | <img width="128" src="images/ublox-neo-m8n-gps-with-compass.jpg"><br>u-blox NEO-M8 GPS (and compass) module ([link](https://www.unmannedtechshop.co.uk/ublox-neo-m8n-gps-with-compass/)).
| &euro;35 | <img height="128" src="images/receiver-x8r.jpg"><br>X8R receiver - the drone's wireless receiver ([link](https://www.unmannedtechshop.co.uk/frsky-x8r-8-16ch-s-bus-accst-receiver-with-smart-port/)).
| &euro;108 | <img height="128" src="images/transmitter-taranis-q-x7.jpg"><br>Taranis Q X7 transmitter ([link](https://www.unmannedtechshop.co.uk/frsky-taranis-q-x7-2-4ghz-transmitter/)).
| &euro;17.50 | <img height="128" src="images/apm-power-module.jpg"><br>Power module - connects the battery to the flight controller and the PDB ([link](https://www.unmannedtechshop.co.uk/high-voltage-apm-power-module-with-3a-ubec/)).
| &euro;37 | <img width="128" src="images/lipo-3300mAh-4s1p-14.8v-25C.jpg"><br>LiPo 3300mAh 4S1P 14.8V 25C battery ([link](https://www.unmannedtechshop.co.uk/gens-ace-3300mah-14-8v-25c-4s1p-lipo-battery-pack/)). |

### Support components

| Price | Description |
|-------|-------------|
| &euro;5 | <img height="128" src="images/gps-mast.jpg"><br>GPS mast - separates the GPS unit from interference from the rest of the system ([link](https://www.unmannedtechshop.co.uk/foldable-gps-mast-mount/)).
| &euro;4 | <img width="128" src="images/ttl-to-rs232-converter-ful-1.jpg"><br>FUL-1 TTL to RS232 converter - connects the telemetry port of the flight controller to the receiver ([link](https://www.unmannedtechshop.co.uk/frsky-transmitter-receiver-upgrade-adapter-ful-1/)).
| &euro;9 | <img height="128" src="images/telemetry-upgrade-cable-1.jpg"><br>FUC-3 upgrade cable ([link](https://www.unmannedtechshop.co.uk/frusb-3-frsky-upgrade-cable-fuc-3/)).
| &euro;2.50 | <img width="128" src="images/telemetry-upgrade-cable-adapter.jpg"><br>SPC (smart port converter) ([link](https://www.unmannedtechshop.co.uk/frsky-smart-port-converter-spc/)).
| &euro;8 | <img height="128" src="images/pixhawk-external-led-and-usb.jpg"><br>External LED and USB connector ([link](https://www.unmannedtechshop.co.uk/all-in-one-led-and-usb-module-for-pixhawk/)).
| &euro;2.50 | <img width="128" src="images/i2c-splitter.jpg"><br>I2C splitter - share the Pixhawk I2C connector between the GPS module's compass connector and the external LED and USB connector ([link](https://www.unmannedtechshop.co.uk/i2c-board/)).
| &euro;7.50 | <img width="128" src="images/spare-propellars.jpg"><br>Spare propellars ([link](https://store.dji.com/product/9450-self-tightening-rotor-white-silver-stripes)).
| &euro;5 | <img width="128" src="images/f450-f550-landing-gear.jpg"><br>F450/F550 landing gear ([link](http://www.helipal.com/dji-landing-gear-for-f450-f550.html)).
| &euro;4.50 | <img height="128" src="images/battery-monitor-alarm.jpg"><br>Battery monitor alarm ([link](https://www.unmannedtechshop.co.uk/battery-monitor-alarm-1-8s/)).
| &euro;40 | <img width="128" src="images/s60-lipo-charger.jpg"><br>S60 LiPo charger ([link](https://www.unmannedtechshop.co.uk/skyrc-s60-ac-balance-charger-discharger/)).
| &euro;7.50 | <img width="128" src="images/t-plug-charger-cable.jpg"><br>T-plug charger cable - connects battery to charger ([link](https://www.unmannedtechshop.co.uk/skyrc-s60-ac-balance-charger-discharger/)).

### Additional physical components

| Price | Description |
|-------|-------------|
| &euro;2 | <img width="128" src="images/t-plug-male-power-connector.jpg"><br>T-plug male power connector - connects the PDB to the power module ([link](https://www.unmannedtechshop.co.uk/male-deans-t-plug-wire-10cm/)).
| &euro;3 | <img width="128" src="images/vibration-damping-mounting-set.jpg"><br>Vibration damping mounting set - isolates the flight controller from the vibration of the frame ([link](https://www.unmannedtechshop.co.uk/vibration-damping-mounting-set/)).
| &euro;3 | <img height="128" src="images/hook-and-loop-velcro-straps.jpg"><br>Hook and loop velcro straps - attach battery to frame ([link](https://www.unmannedtechshop.co.uk/hook-loop-battery-strap-pack-of-5/)).
| &euro;2 | <img width="128" src="images/mounting-foam.jpg"><br>Mounting foam - attach ESCs and other components to the frame ([link](https://www.unmannedtechshop.co.uk/3m-double-sided-mounting-foam/)).
| &euro;5 | <img width="128" src="images/lipo-safety-bag.jpg"><br>LiPo safety bag - keep LiPos safely contained when charging or not in use ([link](https://www.unmannedtechshop.co.uk/lipo-safety-bag/)).

As already noted some minor soldering is required - it's assumed you already have a soldering iron and solder and know how to use them.

The [F450 user manual](http://dl.djicdn.com/downloads/flamewheel/en/F450_User_Manual_v2.2_en.pdf) additionally notes that you'll need threadlocker, a 2mm hex key, [nylon cable ties](https://www.amazon.co.uk/Green-Cable-100Mm-2-5Mm-All/dp/B00904S2DE), scissors and [flush cutters](https://www.sparkfun.com/products/11952). The hex key and the threadlocker (which is something I'd never heard of before) are covered in the [miscellaneous parts](notes.md#miscellaneous-parts) note.

Websites
--------

When putting together this page the most useful sites I found were:

* ArduPilot - in particular its [assembly](http://ardupilot.org/copter/docs/common-pixhawk-wiring-and-quick-start.html) and related sections.
* [Pixhawk.org](https://pixhawk.org/)
* RCGroups - in particualr the [multicopter drone forums](https://www.rcgroups.com/aircraft-electric-multirotor-drones-790/).

The [ArduPilot forums](http://discuss.ardupilot.org/) and [PX4 forums](http://discuss.px4.io/) were also useful.

Note: the terms Pixhawk and PX4 are often used interchangeably - though Pixhawk generally refers to the flight controller hardware while PX4 generally refers to the flight controller software stack.

---

The following sections cover the major components of the quadcopter. In writing this page I started including so many side notes that they started clogging up the whole thing, so I've moved these notes out into [`notes.md`](notes.md). They're worth scanning over quickly. They cover:

* [Brief notes](notes.md#brief-notes) on clockwise and counterclockwise motors and the external LED and USB connector.
* The [F450 ARF kit](notes.md#f450-arf-kit) and why I choose to buy the F450 frame and propulsion system as separate components rather than bundled as an ARF kit.
* The [E300 vs E305 vs E310](notes.md#e300-vs-e305-vs-e310) propulsion systems.
* The [LiPo batteries](notes.md#batteries), the T-plug battery connector, the charger, the battery alarm and the battery safety bag.
* The [IMU and MCU](notes.md#imu-and-mcu) - the core parts of the flight controller and how you can experiment with them.
* [Vibration](notes.md#vibration) and why a vibration damping kit might improve the performance of the sensors in the flight controller.
* Predefined [waypoints](notes.md#waypoints) and in-flight drone-to-computer communication (as opposed to using the hand-held transmitter).
* The [Pixhawk 2.1](notes.md#pixhawk-21) and some background leading to my choice of the classic Pixhawk flight controller.
* [Pixhawk.org vs the ArduPilot site](notes.md#pixhawkorg-vs-ardupilotorg).
* [Bags and cases](notes.md#bag--case) and why the size of the F450 makes it hard to find a good bag for it.
* [Chinese copies](notes.md#chinese-copies) and how buying drone parts is a case of caveat emptor.

Now that's out of the way let's get onto the sections covering the major components...

Frame
-----

The frame is the basic physical platform to which all other components are attached. While most of the other components are updated on a regular basis, frame design seems to evolve at a slower pace.

The [DJI Flame Wheel](https://www.dji.com/flame-wheel-arf/feature) F450 frame came out in early 2012 and still seems to be one of the most popular non-race quadcopter frames.

I choose it because it's recommended on many first time build page (such as the ArduPilot [build your own multicopter](http://ardupilot.org/copter/docs/build-your-own-multicopter.html)) and it has more available space in its central section than it's little brother - the F350 - without the extra complexity and expense of its six armed big brother - the F550.

It consists of four arms and a top and bottom central plate. The bottom plate also serves as the PDB (power distribution board), i.e. the board that connects the motors (via ESCs) to the battery (via the power module).

The ESCs (covered later) are soldered directly to the PDB, as is a cable for connecting the PDB to the power module.

Note: if you buy the E305 propulsion system separately from the frame then it will come with a small PDB so that the propulsion system can be used with any frame, this separate PDB is not needed when using the F450 frame.

Power module
------------

The power module is just a tiny circuit board that connects to the battery at one end and to the PDB (as described above) at the other end, it also has a 6-position connector that connects to the flight controller.

Flight controller
-----------------

The flight controller is the brains of the operation. It's one of the largest components in the system, essentially it's a small computer with its own internal sensors and connectors allowing it to take input from external components (such as the GPS and compass), interact with receivers and control the rest of the system.

It's internal set of sensors are together called an IMU ([inertial measurement unit](https://en.wikipedia.org/wiki/Inertial_measurement_unit)). For a drone the typical IMU covers 10 [degrees of freedom](https://en.wikipedia.org/wiki/Degrees_of_freedom_(mechanics)) that are provided by:

* A 3-axis gyroscope.
* A 3-axis accelerometer.
* A 3-axis magnetometer (compass).
* A barometric pressure (altitude) sensor.

It's fairly obvious how important such sensors must be for a drone - if you'd like to experiment with such sensors (and with the MCU) then see the [IMU and MCU section](notes.md#imc-and-mcu) on the notes page.

There are many flight controllers but as noted above I wanted an open source hardware implementation. I chose the Pixhawk flight controller which is covered in the next section.

Note: the flight controller is often also called the autopilot.

Pixhawk
-------

The [Pixhawk](https://pixhawk.org/modules/pixhawk) is an [open source hardware](http://freedomdefined.org/OSHW) flight controller that originated at [ETH Zurich](https://en.wikipedia.org/wiki/ETH_Zurich) and is the de-facto standard high end open source hardware flight controller.

It is the most commonly used flight controller when using the popular [ArduPilot flight stack](http://ardupilot.org/dev/docs/apmcopter-code-overview.html) and the [PX4 flight stack](http://px4.io/docs/px4-basic-concepts/) - at least in the hobbyist community - though neither of these flight stacks is tied to the Pixhawk.

It is the most expensive component in the parts list above and there are certainly cheaper flight controllers - the most interesting of which seems to be the OpenPilot [CC3D Revolution](https://www.unmannedtechshop.co.uk/openpilot-cc3d-revolution-flight-controller/) which is a product of the [LibrePilot](https://www.librepilot.org/) project (a successor to the now defunct OpenPilot project).

However I chose the Pixhawk as I liked the flight stack projects that used it and liked the fact that it is popular in academic environments.

While the Pixhawk is open source hardware most discussions recommend the [3DR](https://3dr.com/) produced Pixhawk and warn against cheap chinese produced versions. However 3DR no longer produce the Pixhawk version you see covered by the [pixhawk.org](https://pixhawk.org/) and [px4.io](http://px4.io/) sites and instead seem to have gone down a more closed source route. They now sell what they refer to as the [Pixhawk Mini](https://store.3dr.com/products/3dr-pixhawk), however it is not branded as open source hardaware and they do not seem to have released schematics etc. for it.

So at the moment you have no choice but to go with a version produced by some other manufacturer. I did some searching and after excluding completely unknown knock-offs I came up with the following list:

* [Unmanned Pixhawk](https://www.unmannedtechshop.co.uk/unmanned-pixhawk-autopilot-kit/)
* [3DXR Pixhawk](https://www.3dxr.co.uk/product/pixhawk-1-v2-4-8-m8n-gps-power-brick/)
* [Holybro Pix32](http://www.holybro.com/product/11)
* [RadioLink Pixhawk](http://www.radiolink.com.cn/doce/product-detail-116.html)

The Unmanned and 3DXR Pixhawks are available directly from their producers, while the Holybro can be picked up e.g. from [Synosystems DE](https://synosystems.de/de/kategorien/315-pix32-px4-246-pixhawk-flight-controller.html) and the RadioLink from e.g. from the [RobotShop INT](http://www.robotshop.com/eu/en/radiolink-pixhawk-advanced-autopilot.html). There are no end of versions from anonymous manufacturers on sites like [AliExpress](https://www.aliexpress.com/) and [Banggood](http://www.banggood.com/).

I went with the Pixhawk version from Unmanned Tech UK as they seem more engaged in the whole scene than many other suppliers, they are linked to as a supplier on the pixhawk.org site and are mentioned favorably on other sites. I bought it bundled with a [Ublox Neo-M8N GPS module](https://www.unmannedtechshop.co.uk/ublox-neo-m8n-gps-with-compass/) and an [APM power module](https://www.unmannedtechshop.co.uk/high-voltage-apm-power-module-with-3a-ubec/).

Flight stack
------------

The flight stack is the software that runs on the flight controller hardaware and covers, among many other things, both basic direct remote control and fully autonomous autopilot operation.

As already mentioned the Pixhawk supports two flight stacks - PX4 and ArduPilot (the pixhawk.org site used to feature a page covering the choice between the two, it's now gone but you can still find [it on the Wayback Machine](https://web.archive.org/web/20150915080740/http://www.pixhawk.com/choice)).

Note: the ArduPilot stack, often abbreviated as APM (for ArduPilotMega), is rather misleadingly named. It comes from its early days when it originally ran on the [Arduino Mega](https://www.arduino.cc/en/Main/arduinoBoardMega). Those days are long gone and it now runs on ARM processors, like the one found in the Pixhawk, and various other platforms. This [code overview](http://ardupilot.org/dev/docs/apmcopter-code-overview.html) shows it can run on Linux and that when it runs on the Pixhawk it actually sits on top of the PX4 firmware.

When it comes to comparing the PX4 and ArduPilot flight stacks there's lots of confusing and often contradictory information out there. For some information see [this thread](http://discuss.ardupilot.org/t/apm-stack-question-apm-vs-px4/11497) and [this one](http://discuss.ardupilot.org/t/new-guy-here-trying-to-make-sense-of-it-all/9255) on the ArduPilot forums and [this thread](http://discuss.px4.io/t/px4-vs-ardupilot-when-to-choose-what/2214) and [this one](http://discuss.px4.io/t/px4-vs-ardupilot-arduplane-for-mapping-photogrammetry-using-fixed-wing/1766) on the the PX4 forums.

The [ArduPilot stack](https://github.com/ArduPilot/ardupilot) and the [PX4 one](https://github.com/PX4/Firmware/) can both be found on Github and both are clearly under active development.

PX4 appears to be more a product of the academic community while ArduPilot appears to a product of the hobbyist community with some resulting differences in focus, e.g. PX4 seems to focus more on autonomous flight while ArduPilot perhaps more on direct control.

Both though work with ground control software for autonomous operation, e.g. Mission Planner (for ArduPilot) and QGroundControl (originally developed to work with PX4 but now also compatible with ArduPilot). See the [ground station](http://ardupilot.org/copter/docs/common-choosing-a-ground-station.html) section of the ArduPilot site for some comparison of ground control applications.

**Important:** the pixhawk.org and ardupilot.org sites cover much more than just flight stacks, most of the content on both is useful irrespective of which flight stack one uses.

ESC
---

The propulsion systems constists of the propellars, motors and ESCs (electronic speed control). [ESCs](https://en.wikipedia.org/wiki/Electronic_speed_control) are responsible for spinning the motors at the speed requested by the flight controller. An ESC contains its own microcontroller (generally an Atmel ATmega or a Silabs 8051). For more information on ESCs see the DroneTrest [guide](http://www.dronetrest.com/t/what-to-consider-when-buying-a-esc-for-your-multirotor/1305).

I chose the E305 propulsion system as it's the standard system sold with the F450 frame (and can be bought bundled together with it as a kit). The ESCs are the most expensive element in the E305 propulsion system (one ESC being just a little more expensive than its corresponding motor).

There are open source hardware ESC implementations and many commercial ESCs are flashable with open source firmware (the main open source firmwares being [BLHeli](https://github.com/bitdump/BLHeli) and [SimonK](https://github.com/sim-/tgy)). However there seem to be no really popular open source hardware implementations and configuring the open source firmwares for your particular ESCs (whether commercial or open source) is non-trivial.

So for this piece of hardware it seemed easiest to stick with the commercial ones from DJI and consider them non-upgradable black boxes.

Many closed source hardware manufacturers produce ESCs that come with the BLHeli firmware as standard, e.g. the [Turingy Multistar 20A](https://hobbyking.com/en_us/turnigy-multistar-20a-v2-esc-with-blheli-and-4a-lbec-2-6s.html) or the [DYS XM20A](https://hobbyking.com/en_us/xm20a-mini-esc.html).

DJI make a big deal of the fact that their propulsion systems, including the E305, are "tuned" propulsion systems - that the ESCs rather than being sold for use with arbitrary motors have been specifically tuned to work very well with the motors sold as part of the same system. This seems to have been well received by reviewers.

Note: for earlier DJI propulsion systems the system and the ESCs had the same name, e.g. E300. For the E305 system that's no longer the case and the ESCs are named 420 LITE.

Transmitter and receiver
------------------------

The transmitter is the handheld control unit while the receiver is the corresponding component in the drone that receives instructions from the ground and communicates them to the flight controller. The names transmitter and receiver reflect their primary/historical function - these days communication between the two is now two way.

The transmitters and receivers from the manufacturers FrSKY and Futaba seem to be the most popular choices for pairing with the Pixhawk.

I went with FrSKY as there as the information relating to hooking FrSKY components up to the Pixhawk seemed easier to follow.

The Taranis X9D+ is a mid-spec transmitter that's a very popular choice for setups like the one here. However I'm not primarily interested in direct remote control so I chose the Q X7 which is a cut down cheaper version of the X9D+ but is very similar in many respects and runs the same [OpenTX](http://www.open-tx.org/downloads) firmware. See the DroneTrest blog for a [comparison of the two transmitters](http://blog.dronetrest.com/taranis-x9d-or-taranis-q-x7-which-is-better-to-buy/).

Depending on where you look the recommended corresponding receiver is either the FrSKY D4R-II or the X8R.

The FrSKY D4R-II is the recommended receiver on the pixhawk.org [FrSKY page](https://pixhawk.org/peripherals/radio-control/frsky) and as outlined on their [FrSKY telemetry page](https://pixhawk.org/peripherals/telemetry/frsky) you can use an [FrSKY FUL-1 converter](https://www.unmannedtechshop.co.uk/frsky-transmitter-receiver-upgrade-adapter-ful-1/) to connect the Pixhawk to the receiver so it can send telemetry data to the transmitter.

However the ArduPilot [FrSKY telemetry page](http://ardupilot.org/copter/docs/common-frsky-telemetry.html) describes the D4R-II as deprecated and recommends the [FrSKY X8R](https://www.unmannedtechshop.co.uk/frsky-x8r-8-16ch-s-bus-accst-receiver-with-smart-port/), again with the FUL-1 but with an additional [smart port converter](https://www.unmannedtechshop.co.uk/frsky-smart-port-converter-spc/) (the same converter as bundled with the FrSKY USB upgrade cable above).

In the parts list you'll see a number of additional components related to the receiver:

* FUL-1 - needed for connecting the telemetry port of the flight controller to the receiver.
* FUC-3 - upgrade cable.
* SPC (smart port converter).

It's always good to be able update the firmware of any given component and the FUC-3 is needed for doing this with FrSKY products. Upgrading the receiver isn't just a good idea - it may be required, see the [warning](https://pixhawk.org/peripherals/radio-control/frsky#receivers) in the pixhawk.org section covering FrSKY receivers.

The SPC is needed in two quite different situations - it's needed to connect the upgrade cable to the older style connector of the D4R-II and when using the X8R receiver it's needed for adapting the FUL-1 to connect the receiver to the flight controller.

Connecting the telemetry output of the flight controller to the receiver is optional - the receiver simply forwards the telemetry information to the receiver which can then display it to the user on its small LCD screen.

Note: the FUL-1 is not a special purpose component, it's completely generic and many other manufacturers produce something similar - it just performs the task of converting TTL to RS232 (see [here](https://www.sparkfun.com/tutorials/215) for more information), something that's needed in many situations.

Telemetry kit
-------------

TODO: install the [telemetry kit](https://www.unmannedtechshop.co.uk/100mw-ardupilot-unmanned-telemetry-kit-v2-433mhz/) and see if it simply relays telemetry information or if it allows direct control from the ground station. If it's interesting add it into the parts list.
