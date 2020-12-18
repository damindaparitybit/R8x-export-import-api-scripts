# R8x-export-import-api-scripts
Check Point R8x Export, Import, Set/Update, and Delete mgmt_cli API scripts for bash on Check Point Gaia OS

CLI API Example for exporting, importing, setting/updating, and deleting different objects using CSV files (v00.60.00)

For a complete overview, review the PDF - TBD

As of v00.60.00.045 the approach to shared scripts has changed to focus only on the current work in progress under devops.dev folder.

Well functioning sets of scripts shall be packaged into releases that can be downloaded as a set for quick deployment and implementation.  Future effort to create an installation and update solution, similar to other scripting solutions targetting Check Point Software Technologies will be analyzed, pending method of providing sustainable locations for such downloads.


# Overview

The export, import, set, and delete using CSV files scripts in this post, currently version 00.60.00 dated 2020-12-17, are intended to allow operations on an existing R80, R80.10, R80.20[|.M1|.M2], R80.30, R80.40, and R81 Check Point management server (SMS or MDM) from bash on the management server or another API enabled management server instance (Check Point Gaia OS R8X) able to authenticate and reach the target management server.


These scripts show examples of:

- an export of objects and services with full and standard json output, and export of hosts, networks, groups, groups-with-exclusion, address-ranges, dns-domains, hosts interfaces, and group members to csv output [future services dump to csv is pending further research]
- an export of hosts, networks, groups, groups-with-exclusion, address-ranges, dns-domains, hosts interfaces, and group members to csv output [future services dump to csv is pending further research]
- an import of hosts, networks, groups, groups-with-exclusion, address-ranges, dns-domains, hosts interfaces, and group members from csv output generated by the export to csv operations above.
- a set of different objects, similar to the generic import operation, based on standard file names generated by export operation
- a script to delete groups-with-exclusion, groups, address-ranges, dns-domains, networks, hosts, using csv files created by an object name export to csv for the respective items deleted.  NOTE:  DANGER!, DANGER!, DANGER!  Use at own risk with extreme care!
- MDM script to document domains and output to a domains_list.txt file for reference in calls to other scripts
- Session Cleanup scripts to show and also remove zero lock sessions that may accumulate.

For direct questions, hit me up at ericb(at)checkpoint.com 
    or lookup information on https://community.checkpoint.com CheckMates community.

NOTE:  As of version 00.60.00.000 all scripts require the "_api_subscripts" folder in the parent folder of the script's operating folder!  Don't forget to copy this folder also.
NOTE:  For versions prior to 00.60.00.000, so 00.50.00 and older all cli_api*.sh scripts require "common" folder with script to handle command line parameters!  Don't forget to copy this folder also.

Description

This post includes a set of script packages, which can be used independently combined.  All script files end with .sh for shell and are intended for Check Point Software Technologies Gaia bash implementation on R80, R80.10, R80.20, R80.30, R80.40, and R81; potentially later versions.  Scripts in the packages have specific purposes and some scripts call sub-scripts for extensive repeated or common operations (e.g. CLI parameter handling, mgmt_cli authentication and basic operations, etc.).  The packages also include specific expected default directory folders that are not created by the script action.  A set script templates is also provided to generate other scripts.

Releases have packages for the key script folders:

The script packages are:

- Common operations handlers         :  common.v00.50.00.055.tgz
- Export, Import, Set, Delete Object :  export_import.all.v00.50.00.055.tgz
- session cleanup handlers           :  Session_Cleanup.v04.50.00.templatev00.50.00.055.tgz
- template for script development    :  _templates.v00.50.00.055tgz
    - script templates with command line parameter handling for the API from bash 
 
The approach to provided compressed packages was changed to facilitate quicker implementation on the management hosts.

Packages contain the Operations folder structure, where the key working folders are not "*.wip" incarnations.

