### Resources

1. denodo-install-solutionmanager-9-ga-linux64.zip
2. denodo-update-9.1.2.jar
3. denodo-install-9-ga-linux64.zip
4. denodo-update-9.1.2.jar

```
PS: 
- Make sure update to same version both Denodo Solution Manager and Denodo Platform 
- Make sure keystore is same both Denodo Solution Manager and Denodo Platform (this will do after install the Denodo Platform)
```

### VM to Install
```
$ssh denodo@10.10.8.60
pass: denodovm2
```

### Install Denodo Solution Manager 9.0.0
```
$cd /home/denodo/download
$unzip denodo-install-solutionmanager-9-ga-linux64.zip
$unset DISPLAY
$cd denodo-install-solutionmanager-9/
$chmod +x installer_cli.sh
$./installer_cli.sh install
```
- Accept terms: Y
- Setup type: Custom
- Installer path: /home/denodo/DenodoSolutionManager9
- Locale (default: us_pst): us_utc_iso
- PS: For another options just enter and enter again

### Update Denodo Solution Manager to 9.1.2 then Activate License
```
$cd /home/denodo/DenodoSolutionManager9
$./jre/bin/java -jar /home/denodo/download/denodo-update-9.1.2.jar "$PWD" -c
```

Activate License :
```
$ll /home/denodo/download/*lic
- SA Lic : Stand Alone License
- SOL Lic : Solution Manager License

$cp DTUS-TL-PSK-250026-047-SOL-PA.lic /home/denodo/DenodoSolutionManager9/conf/denodo.lic
$cd /home/denodo/DenodoSolutionManager9/bin
$./licensemanager_startup.sh
$cd /home/denodo/DenodoSolutionManager9/logs/license-manager
$tail license-manager.log
``` 

Start Solution Manager :
```
$cd /home/denodo/DenodoSolutionManager9/bin
$./solutionmanager_startup.sh
$cd /home/denodo/DenodoSolutionManager9/logs/solution-manager
$tail solution-manager.log
```

Start Web Tool :
```
$cd /home/denodo/DenodoSolutionManager9/bin
$./solutionmanagerwebtool_startup.sh
$cd /home/denodo/DenodoSolutionManager9/logs/solution-manager-web-tool
$tail solution-manager-web-tool.log
```

Copy License Key to Local Backup :
```
$cd /home/denodo/DenodoSolutionManager9/conf/
$cp denodo-key.keystore /home/denodo
$cp denodo-keystore.json /home/denodo
```

Open Web Browser :

1. http://10.10.8.60:19090/solution-manager-web-tool/
2. Enter User: admin Pass: admin
3. Go to Licenses. Check License.
4. Go to Environments. Name : Sibernetik-Denodo-lab. License scenario: DEVELOPMENT/9.0. Then Save.
5. Go to New Cluster. Name: Sibernetik-Denodo-Lab. Then Save.
6. Go to New Server. Name: Sibernetik-Denodo-VDP-Server1. Host: 10.10.8.50. Port: 9999. Type: VDP. User:admin Password:admin. Use default providers: On Premise. Region: Use custom regions > Jakarta. Then Save.
7. Go to New Cluster. Name: Sibernetik-Denodo-Data-Catalog-Cluster. Then Save.
8. Go to New Server. Name: Sibernetik-Denodo-Data-Catalog-Server1. Host: 10.10.8.50. Port: 9090. Type: Data Catalog. User:admin Password:admin. Use default providers: On Premise. Region: Use custom regions > Jakarta. Then Save.

### Install and Update Denodo Platform 9.0.0
```
$ssh denodo@10.10.8.50
pass: denodovm1
```

1. Make sure owner and access granted | chown and chmod.
2. Unzip installer
3. ```$unset DISPLAY```
4. Run installer_cli.sh
5. Setup type: Custom. Directory installer: /home/denodo/DenodoPlatform9. VDP: full. Scheduler: full. License Manager Server Host: 10.10.8.60. For another options just enter and enter again.
6. ```$cd /home/denodo/DenodoPlatform9```
7. ```$./jre/bin/java -jar /home/denodo/download/denodo-update-9.1.2.jar "$PWD" -c```
8. Copy License Key from Solution Manager what we backup before (denodo-key.keystore & denodo-keystore.json).
9. ```$./home/denodo/DenodoPlatform9/bin/vqlserver_startup.sh```
10. ```$tail /home/denodo/DenodoPlatform9/logs/vdp/vdp.log```
11. ```$./home/denodo/DenodoPlatform9/bin/datacatalog_startup.sh ```

Open Web Browser :

1. http://10.10.8.60:19090/solution-manager-web-tool/
2. User Pass, admin:admin
3. Open VDP Server dashboard (Design Studio)
4. Do not go directly to Design Studio at 10.10.8.50:9090 because if we get bigger/more node server it will be rough.

### Refference:

1. https://community.denodo.com/docs/html/browse/9.1/en/solution_manager/installation/using_the_command_line_installer/using_the_command_line_installer
2. https://community.denodo.com/docs/html/browse/9.1/en/platform/installation/installing_updates_and_hotfixes/installing_updates_and_hotfixes#installing-an-update-from-the-command-line
3. https://community.denodo.com/docs/html/browse/9.1/en/solution_manager/installation/postinstallation_tasks/replicate_the_encryption_key_across_all_the_installations/replicate_the_encryption_key_across_all_the_installations
4. https://community.denodo.com/docs/html/browse/9.1/en/platform/installation/using_the_command_line_installer/using_the_command_line_installer
5. https://community.denodo.com/docs/html/document/denodoconnects/latest/en/Denodo%20AI%20SDK%20-%20User%20Manual