# USRP B210 Overclock
### This is a fork of the official USRP Hardware Driver (UHD™) Software

## Functionality
This build exposes profiles for the USRP B210 FPGA SDR to request up to 122.88msps. Testing has been done with a LibreSDR clone and are not 1:1 - The same packing issue that was originally present above 104msps has yet to be resolved for the Genuine Ettus B210 SDRs. The limit for the genuine model is about 75msps for stable demodulation; this is currently being being worked on with limited access to genuine boards. 

## Warnings and issues!
Overclocking your SDR will void your warranty, Ettus and AnalogDevices warn that overclocking the AD9361 can lead to degraded performance and possible damage to your device, proceed with caution.

### To install the host firmware:
```
mkdir host/build && cd host/build
cmake ../
make -j4 && sudo make install
sudo ldconfig #reload libraries
```
If you need help installing, see [Seler1500's Guide](https://github.com/seler1500/LibreSDR-B210-setup) on setting up.

t/n: Thanks to the developers at UHD for the wonderful commentary :3 
and the rest of their readme I will leave here:

# USRP Hardware Driver (UHD™) Software
Welcome to the UHD™ software distribution! UHD is the free & open-source
software driver and API for the Universal Software Radio Peripheral (USRP™) SDR
platform, created and sold by Ettus Research.

UHD supports all Ettus Research USRP™ hardware, including all motherboards and
daughterboards, and the combinations thereof.

## Documentation

For technical documentation related to USRP™ hardware or UHD system
design, check out the [UHD and USRP Manual](http://files.ettus.com/manual/).
That is where you can find
[Installation Instructions](http://files.ettus.com/manual/page_install.html),
help on how to
[build UHD from source](http://files.ettus.com/manual/page_build_guide.html) on
different platforms, development guidelines and reference documentation as well
as device usage guidance.

Additionally, be sure to check out the Ettus Research
[FAQ](https://kb.ettus.com/Technical_FAQ), and the
[Knowledge Base](http://kb.ettus.com) for useful application notes and
tutorials.

## OS Support

UHD is primarily developed on Linux, but we also test and support the following
operating systems.

* Linux (Fedora and Ubuntu)
* Mac OS X (Intel)
* Windows 10

Other operating systems will most likely work, too, but are not officially
supported.

## Applications

UHD can be used to build stand-alone applications with USRP™ hardware, or with
third-party applications. Some common toolkits / frameworks are:

* [GNU Radio](http://gnuradio.org/)
* [RFNoC OOT Blocks](https://github.com/EttusResearch/rfnoc-oot-blocks)
* [NI LabVIEW - UHD RFNoC](https://github.com/ni/labview-usrp-examples)
* [NI LabVIEW](https://www.ni.com/download/ni-usrp-1.3/4711/en/)
* [MathWorks Matlab and Simulink](https://www.mathworks.com/discovery/sdr/usrp.html)
* [REDHAWK](https://redhawksdr.org/)
* [OpenBTS GSM](http://openbts.org)
* [Osmocom GSM](https://osmocom.org)
* [Amarisoft LTE](https://www.amarisoft.com/products-lte-ue-ots-sdr-pcie)
* [Software Radio Systems srsRAN](https://www.srsran.com/)
* [Eurecom OpenAirInterface](https://gitlab.eurecom.fr/oai/openairinterface5g)

## Directories

__host/__

The source code for the user-space driver.

__mpm/__

The source code for the module peripheral manager (MPM). This is code that is
run on embedded devices.

__firmware/__

The source code for all microprocessors in USRP hardware.

__fpga/__

The source code for the UHD FPGA images.

__images/__

This contains the package builder for FPGA and firmware images.
We provide other tools to download image packages, the scripts in here
are mainly relevant for UHD maintainers and -developers.

__tools/__

Additional tools, mainly for debugging purposes. See the readme-file
in that directory for more details on the individual tools.

