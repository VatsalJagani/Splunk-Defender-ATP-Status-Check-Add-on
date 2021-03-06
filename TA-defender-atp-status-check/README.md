# Microsoft Windows Defender ATP Status Check Add-on for Splunk

### Download from Splunkbase
https://splunkbase.splunk.com/app/5691


OVERVIEW
--------
The Microsoft Windows Defender Status Check Add-on for Splunk allows users to check their Defender ATP configuration status for Windows machines. It uses the Windows Registry to find the configuration status for Defender ATP. The Add-on does not contain any dashboards or savedsearches.

Install the Cyences App for Splunk (https://splunkbase.splunk.com/app/5351/) to easily audit the configuration status check for Office 365 Defender ATP on endpoints by using the Microsoft 365 Defender ATP Audit dashboard.


* Author - CrossRealms International Inc.
* Version - 1.0.0
* Build - 1
* Creates Index - False
* Compatible with:
   * Splunk Enterprise version: 8.2, 8.1, 8.0, 7.3, 7.2, 7.1
   * OS: Platform Independent
   * Browser: Does not have UI.



TOPOLOGY AND SETTING UP SPLUNK ENVIRONMENT
------------------------------------------
There are two ways to setup this app:
  1. Standalone Mode: 
     * Install the `Defender ATP Status Check Add-on`.
  2. Distributed Mode:
     * The Add-on is not required on search head.
     * Install the `Defender ATP Status Check Add-on` on the universal forwarders on Windows and configure it.
     * Install the Add-on on a heavy forwarder. Otherwise, install it on an indexer. Input configuration is not required for both indexers and heavy forwarders.


DEPENDENCIES
------------------------------------------------------------
* There are no external dependencies for this Add-on.


INSTALLATION
------------------------------------------------------------
* From the Splunk Home page, click the gear icon next to Apps.
* Click `Browse more apps`.
* Search for `Defender ATP Status Check Add-on`.
* Click `Install`.
* If prompted, restart Splunk.


DATA COLLECTION & CONFIGURATION
------------------------------------------------------------
### Enable Data Inputs ###
* Add the following stanzas in `TA-defender-atp-status-check/local/inputs.conf` file and deploy it for all required Windows hosts.
```
[powershell://generate_defender_atp_status_logs]
disabled = 0

[monitor://$SPLUNK_HOME\var\log\TA-defender-atp-status-check\DefenderATPStatus.log]
disabled = 0
```



UNINSTALL ADD-ON
-------------
1. SSH to the Splunk instance.
2. Navigate to apps ($SPLUNK_HOME/etc/apps).
3. Remove the `TA-defender-atp-status-check` folder from the `apps` directory.
4. Restart Splunk.


RELEASE NOTES
-------------
Version 1.0.0 (Aug 2021)
* Created Add-on with Powershell script and inputs.conf.



OPEN SOURCE COMPONENTS AND LICENSES
------------------------------
* N/A


CONTRIBUTORS
------------
* Vatsal Jagani
* Bhavik Bhalodia
* Ahad Ghani



SUPPORT
-------
* Contact - CrossRealms International Inc.
  * US: +1-312-2784445
* License Agreement - https://d38o4gzaohghws.cloudfront.net/static/misc/eula.html
* Copyright - Copyright CrossRealms Internationals, 2021
