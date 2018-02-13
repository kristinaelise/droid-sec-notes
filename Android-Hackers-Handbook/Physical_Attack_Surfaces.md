## Physical Attack Surfaces

- attacks that require physically _touching_ a device

### Dismantling Devices
- enables attacks against hardware
- manufacturers typically don't protect the hardware well, since dismantling requires some niche skills
- dismantling can reveal:
  - exposed serial ports (allow for receiving debug messages or shell access)
  - exposed JTAG debut ports (enable debugging, flashing, accessing the firmware of a device)
- possible to remove flash memory or core CPU (and therefore internal flash) and read boot loader, config and full flash file-system

### USB
- multiple modes: ADB, fastboot, download mode, mass storage, media device, tethering, MTP (Media Transfer Protocol)
- some devices don't support certain modes
- attack surfaces are largely dependent on the device mode
- for all modes, drivers in the boot loader or Linux kernel support the USB hardware and on top of those drivers, software handles the communication using the protocols specific to each type of functionality
- Android 4.0 < devices used mass storage mode by default
- support removed for later versions and opted for MTP mode as the default
- each USB device has 1+ configurations which have at least one _interface_
  - interface specifies collection of _endpoints_ that represents the means of communicating with a function 
  - each endpoint is unidirectional in terms of data sent or received
- **lsusb**: capable of displaying detailed info about interfaces and endpoints supported by a device
- **libusb**: allows for communication with individual endpoints using bindings in common libraries
- **Multifunction Composite Gadget**: support for multiple functions simultaneously on a single USB port; Android supports MCG
- **Gadget Framework**: software that supports MCG
- supported USB modes listed in _init_ configuration files

### ADB
- USB debugging enabled starts ADB daemon
- allows executing commands with special privileges
- Android 4.2.2 and <, no authN required to access ADB shell
- HTC One's T-Mobile version exposed ADB with no authN by default and didn't allow disabling it
- attacks demo'd: 
  - "Juice Jacking": Robert Rowley
    - attacker creates charging station that can download victim's data or install malicious software
  - "physical drive-by attack": Kyle Osborn, Michael Muller
    - downloaded victim's data using ADB
    - attacker connects deevice to victim's device when victim leaves theirs unattended
- later Android versions add ADB authN by default; mitigates but doesn't eliminate attack surface

### Other Physical Attack Surfaces
- SIM Cards, SD cards, HDMI, exposed test points, docking connectors

### Third-Party Modifications
- OEMs introducing changes as part of the Android integration process often ^ attack surfaces by a _huge_ margin
- generally determining full nature of changes requires manual process: compare a live device against a Nexus device and see which processes are running compared to vanilla Android

