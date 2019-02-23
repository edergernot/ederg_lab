# ederg_lab
My lab is build with GNS3 and the networkdevices I use, run on IOSv-Images from virl or I use Cisco CSR.
I use the Linux-Subsystem-Ubuntu18.04 on Windows10.
If some things dont work in Linuxsubsystem, I run a Ubuntu Workstation in GNS3 and here I can reache all nets over the virtual infrastructur.
Ansible 2.7 run on the subsystem with all my tested playbooks.

I also build a GNS3-LAB an on ESXi which I can reach from an Ubuntu-VM which runs on that ESXSi. Here Ansible is also installed.
Here I have more RAM and so I can run larger Labs.

###My virtual Lab on the ESX :
![ESX-LAB]{GNS3-LAB_ederg.png}
* Inventory for the beginning.
  * 4 Cisco IOSv-Routers
  * 4 Cisco IOSv-Switches
  * 4 Alpine Linux Hosts (for simulating clienttraffic)
  * 1 Ubuntu "Network Automation" Apliance from GNS3 Marketpalce

I use GNS3 because I'm useing it for years, when I learn new stuff. I like the possibility to take a packetcapture an every wire within the topology and simulate paketloss and jitter.
It's so easy to import new Devices into GNS3 with appliances from GNS3 marketplace. ... But now I'm going to stop advertising GNS3.

### My first simple Ansible Playbooks 
* **sh_ip_int_br.yml:**
    this will display the output of "show ip int brief"

* **get_serial.yml**
    with this palybook the serial-numbers of the devices get printed.
    ios_facts is used so I get structered data

* **copy_run_init.cfg.yml**
   saves running config on flash with the name init.cfg
   ***problems*** : run sometimes in timeouts..

* **cdp_nei.yml**
get cdp neighbores, but for switches print the error lines. (This is the banner)

* **enable_all_int.yml**
Enable all Interfaces on Device.
Uses Napalm-Facts to get Interfaces. loops over all interfaces and enable it with ios_config.
**Very Slow!**
