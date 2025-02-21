# VMWare-Workstation-Twaeks
Bei Performanceproblemen mit VMWare Workstation kan man folgendes tun:

```
powercfg /powerthrottling disable /path "C:\Program Files (x86)\VMware\VMware Workstation\x64\vmware-vmx.exe"
```
und / oder die Verknüfung > Erweitert << Als Administrator ausführen.


```
fsutil behavior set disablelastaccess 3
```
