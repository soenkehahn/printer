Mac
==========

We have a networked printer Fuji Xerox DocuPrint 3055. Based on experimentation, the only driver that works well is **FX DocuPrint 3055 3.5**

Installing the official [drivers](http://onlinesupport.fujixerox.com/processDriverForm.do;jsessionid=283ED4E2B1ABE181330C4BD499B147C4?ctry_code=SG&lang_code=en&d_lang=en&corp_pid=DP3055&rts=null&model=DocuPrint+3055&type_id=2&oslist=Windows+2000&lang_list=en) does not install the drivers properly. This additional hack is unfortunately required. We have no idea why but hey it just works.

In `/Library/Printers/PPDs/Contents/Resources`, confirm that the following files are missing and add the :
* `FX DocuPrint 3055-PDF.gz`
* `FX DocuPrint C3055 DX-PDF.gz`
* `FX DocuPrint C3055-PDF.gz`

In `/Library/Printers/FujiXerox/Filter`, unzip `fxnpdftopdf.gz` and add the folder
* `fxnpdftopdf.bundle`

FWIW, you should also be abled to see a shared printer, 192.168.6.2 and use that to print.


Windows
==========

* [Windows 10](https://github.com/hackerspacesg/hackerspace.sg/issues/128)
* For Windows 8 and 8.1: download x64 PCL Driver and select a PCL B/W driver during installation.

Linux
=====

The printer showed up (by ip address) automatically, but using that printer didn't work properly.

Adding the `FUJI_XEROX_DocuPrint_3055` printer through the cups web interface (using default options) resulted in a working printer. (On ubuntu wily, see https://help.ubuntu.com/12.04/serverguide/cups.html)
