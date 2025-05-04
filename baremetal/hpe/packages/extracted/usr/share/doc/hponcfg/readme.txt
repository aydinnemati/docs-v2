
HPE Lights-Out Online Configuration Utility (HPONCFG)
Version 6.0.0-0


Description
-----------

HPE Lights-Out Online Configuration utility is a command line utility used
to configure ProLiant Management Processors from within the Linux operating 
systems without requiring a reboot of the server.  
 
 
Support
-------

Supported Operating Systems

  SUSE LINUX Enterprise Server 
  Red Hat Enterprise Linux Server 	


Supported Hardware 

  Integrated Lights-Out 4 (iLO 4) or later


Pre-Requisites
--------------

  For Integrated Lights-Out 5, this utility requires minimum firmware revision 1.20 or later.

  The management interface driver and management agents must be
  installed on the server.

  For iLO 5 or later, openssl v1.0.x or later is required in addition to above packages.
  Customers who manually compile and install openssl or intentionally relocate
  /usr/bin/openssl, need to set PATH environment variable to direct HPONCFG to
  the right/intended openssl.

Installing & Using HPE Online Configuration Utility
--------------------------------------------------

HOW TO INSTALL:

  If a previous version of the Hponcfg utility has been installed, 
  it must be removed before this package can be installed. 
 
  To remove the previous version of the package, type the following :

    $ rpm -e hponcfg
  
  To install the HPONCFG component Run the command "rpm -ivh" along with
  hponcfg package.

	$ rpm -ivh hponcfg-x.x.x.x86_64.rpm 

  After component installation, the binary executable will be placed under the
  directory /sbin.
  

  
HOW TO USE :

  Invoke the HPE Lights-Out Online Configuration (HPONCFG) Command Line utility 
  from the command line, using the  command "hponcfg".  HPONCFG will display 
  the usage information if it is executed without any command line parameters. 


  The HPONCFG command line utility reads an XML input file, formatted according
  to the rules of the RIBCL language, and produces a log file containing the
  requested output.

  Information about RIBCL language is documented in the "User's guide" and 
  "Scripting Guide" of the Management Processor.

  A package containing various and comprehensive sample scripts is available
  for download at the iLO Support and Downloads section of:

  www.hpe.com/info/ilo

  Typical usage is to select a script that is similar to the desired
  functionality and modify it for the exact desired functionality.
  Note that, although no authentication to the iLO is required, the XML syntax 
  requires that the USER_LOGIN and PASSWORD tags be present in the LOGIN tag,
  and that these fields contain data. Any data will be accepted in these fields.


  In order to successfully execute HPONCFG, the utility must be invoked as
  "Administrator" on Windows servers and as "root" on Linux servers. An error
  message will be returned by HPONCFG if the user does not possess sufficient
  privileges.

  More information on the command line options are available in the 
  "Scripting and Command Line Guide".


Copyright 2004,2022 Hewlett Packard Enterprise Development LP.
