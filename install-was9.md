# WAS 9 for Developer Installation

## Step

1. Download setup files
2. Setup IBM Installation Manager
3. Setup WebSphere for Developer
4. Setup Eclipse
5. Install WAS Dev Tools plugin for Eclipse
6. Setup WAS Server for Eclipse
7. Test run WAS on Eclipse

---

## 1\. Download setup files

1. [IBM Installation Manager](https://www.ibm.com/support/pages/installation-manager-and-packaging-utility-download-documents)
2. [Eclipse IDE for Enterprise Java and Web Developers](https://www.eclipse.org/downloads/packages/release/2020-06/r) (version Eclipse 2020-06 - 4.16)
3. [IBM WebSphere Application Server V9.x Developer Tools](https://public.dhe.ibm.com/ibmdl/export/pub/software/websphere/wasdev/downloads/wdt/2020-09/wdt-update-site_20.0.0.9.v20200826_1754.zip)




## 2\. Setup IBM Installation Manager

IBM Installation Manager: File > Preferences... [ Repositories ]

<img src="./images/IBMIM01.png" style="zoom:80%;" />

Add Repositories Location as URL below, then click [ OK ] button.

```
http://www.ibm.com/software/repositorymanager/com.ibm.websphere.BASE.v90
```

See more: [Traditional WebSphere repository](https://www.ibm.com/support/knowledgecenter/en/SSEQTP_9.0.5/com.ibm.websphere.installation.base.doc/ae/cins_repositories.html) > WebSphere Application Server

<img src="./images/IBMIM02.png" style="zoom:80%;" />

Click Install and follow steps.

## 3\. Setup WebSphere for Developer

[How and Where to Download WebSphere Application Server](https://www.ibm.com/cloud/blog/websphere-trial-options-and-downloads)

__WebSphere Single-developer use__

>All editions of WebSphere are free for development use, which is defined in the license as “a physical or virtual desktop environment, running WebSphere and used by no more than one developer.” It’s intended for coding, building, and testing of a single developer’s efforts. In the License document, look for the section entitled "Use of the Program on a Developer Machine for development and unit test purposes."

Note: You can get IBM Support for development use through your production-use WebSphere support; you don’t need separate paid support for single-developer use.

<img src="./images/PATH01.png" style="zoom: 80%;" />

Shared Resource Directory: `D:\IBM\IMShared`

<img src="./images/PATH02.png" style="zoom: 80%;" />

Installation Directory: `D:\IBM\WAS9\AppServer`

<img src="./images/PATH03.png" style="zoom: 80%;" />

Press Install button, then wait until downloads finished.



### Setup WAS Profiles

<img src="./images/PMT01.png" style="zoom: 80%;" />

<img src="./images/PMT02.png" style="zoom: 80%;" />

<img src="./images/PMT03.png" style="zoom:80%;" />

<img src="./images/PMT04.png" style="zoom:80%;" />

<img src="./images/PMT05.png" style="zoom:80%;" />

<img src="./images/PMT06.png" style="zoom:80%;" />

<img src="./images/PMT07.png" style="zoom:80%;" />

<img src="./images/PMT08.png" style="zoom:80%;" />

<img src="./images/PMT09.png" style="zoom:80%;" />

<img src="./images/PMT10.png" style="zoom:80%;" />

<img src="./images/PMT11.png" style="zoom:80%;" />

<img src="./images/PMT12.png" style="zoom:80%;" />

<img src="./images/PMT13.png" style="zoom:80%;" />

<img src="./images/PMT14.png" style="zoom:80%;" />

<img src="./images/PMT15.png" style="zoom:80%;" />

<img src="./images/PMT16.png" style="zoom:80%;" />

<img src="./images/PMT17.png" style="zoom: 67%;" />

<img src="./images/PMT18.png" style="zoom: 67%;" />

---

### Profile Management

[Administering profiles](https://offf.to/307n)

#### List profiles

```
D:\IBM\WAS9\AppServer\bin\manageprofiles.bat -listProfiles
[EPAY01]
```

```
> manageprofiles.bat –getPath –profileName EPAY01
D:\IBM\WAS9\AppServer\profiles\EPAY01
```

#### Remove profile:

1. Delete the profile using one of these commands:
   - **On Windows:** was_install_dir**\bin\manageprofiles.bat –delete –profileName** profile
   - **On UNIX/Linux:** was_install_dir**/bin/manageprofiles.sh –delete –profileName** profile
2. Ensure that references to the deleted profile are removed from the profile registry by running the following command:
   - **On Windows:** was_install_dir**\bin\manageprofiles.bat –validateAndUpdateRegistry**
   - **On UNIX/Linux:** was_install_dir**/bin/manageprofiles.sh –validateAndUpdateRegistry**
3. Delete the profile directory tree (if it was not deleted by the previous action) starting at profile_dir.

```
manageprofiles.bat –delete –profileName EPAY01
manageprofiles.bat –validateAndUpdateRegistry
```



## 4\. Setup Eclipse

1. Download [Eclipse IDE for Enterprise Java and Web Developers](https://www.eclipse.org/downloads/packages/release/2020-06/r) (version Eclipse 2020-06 - 4.16), Ref: [Eclipse Release](https://en.wikipedia.org/wiki/Eclipse_(software)#Releases)
2. Create Eclipse shortcut to Desktop
3. Setup shortcut properties
   Target: `D:\Dev\Java\eclipse-jee-2020-06-R-win32-x86_64\eclipse\eclipse.exe -data "D:\Workspace" -vm "D:\IBM\WAS9\AppServer\java\8.0\jre\bin\javaw.exe"`

<img src="./images/ECLIPSE01.png" style="zoom: 80%;" />

4. Run Eclipse from shortcut
5. Eclipse: Window > Preferences > Java > Compilers
   Set JDK Compliance > Compiler compliance level: `1.8` then press Apply button
6. Setup Installed JREs, Add WAS9-JDK8
   - JRE home: `D:\IBM\WAS9\AppServer\java\8.0\jre`
   - JRE name: `WAS9-JDK8`

<img src="./images/ECLIPSE02.png" style="zoom: 80%;" />



## 5\. Install WAS Dev Tools plugin for Eclipse



## 6\. Setup WAS Server for Eclipse

1. Eclipse: Window > Show View > Other... > Server > Servers

2. On Server View: Right Click > New > Server > ...

3. Define a New Server
   - Select the server type: IBM > WebSphere Application Server ...
   - Server's host name: localhost
   - Server name: WAS9-EPAY01
   - Server runtime environment: WAS9 *

<img src="./images/WAS901.png" style="zoom:80%;" />

4. Configuration runtime environments

<img src="./images/WAS902.png" style="zoom:80%;" />

5. Summary

<img src="./images/WAS903.png" style="zoom:80%;" />

---

