# Fujitsu Celsius J550n opencore hackintosh
This is my "living" backup of working EFI i use for J550n hackintosh. It's pretty powerful little machine that you can get refurbished for about 250eur (what i payed).

Overall this hackintosh was a bit hustle to get together it took me multiple days but now its pretty solid i think everything works as it should. With this EFI you should be able to get it going very fast. I use FileVault no problem. I am not 100% about apple services, handoff, imessages etc because i don't use any of it. Not yet a signle crash/panic. Performance is awesome.

I use Catalina. I think Big Sur should be OK but it seems the OS has issues with low-dpi multiple screen rendering of type so i am avoiding it until its settled.

# Specs
Model: FUJITSU D3427-A1 - Serialnumber: YM5S001663
CPU: Intel Xeon E3-1275 v5 @ 3.60GHz
HDD: Micron 1100 MTFD 256GB
GPU: Nvidia Quatro K2000

Except the Quadro it should be all standard setup.

# Notes
I have updated the BIOS to latest using freedos and firmware from FUJITSU support site.

Overall i just followed the [opencore install guide](https://dortania.github.io/OpenCore-Install-Guide/) and post-instal at Dortania.

## GPU
By default the machine uses intel iGPU and it worked for me to install everything. I had issues with multiple monitors with it though. The igpu in there is Intel P530 its even mentioned in [Opencore Skylake guide](https://dortania.github.io/OpenCore-Install-Guide/config.plist/skylake.html#deviceproperties) that it's not natively supported by OSX but you can get it working with some work.

I had Quadro lying around and that is just natively supported. It fits there perfectly but watch out for bigger cards they will be too long.

## EFI Drives not showing in BIOS
For some reason the USB drive would show up but internal drives wont. I followed [this guide](https://www.reddit.com/r/hackintosh/comments/fj3zrj/booting_opencore_without_the_usb_on_an_asrock/) ive also copied same guide into `efi-fix-guide-backup.md` in this repo.
It's pretty easy you just create some boot records on the drives manually with linux. Ubuntu live usb has required tools included.

## XHCI-unsupported
in opencore guide it says this kext is not required for Skylake but it was required for me.
