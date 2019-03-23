# NCIENNFS01 NFS Server

## Top Level Directories

### admin

### r-libs
Location of the shared directories

### r-libs-readonly
This directory is simply a second mount of the r-libs directory which is set as the primary shared library.  The directory is set as rad-only so that Energy-R-Admins don't accidentally install packages when not intending.

### vaults
This is a folder for storing "vaults" for the NAVsecret package developed by Vergil Weatherford and Chris Newton.  It provides a way to securely store credentials and even share those credentials (without revealing them) to other R users.  This has usefulness for both easy authentication (for things like the sharepoint API) but also for 

Permissions for this directory are set to be r/w/x for all users. In the future it may be preferrable to have the files only be writable by the user that created the file, and read-only for all other users.
In a way, NAVsecret is like a Navigant-internal password manager for R users.

### web