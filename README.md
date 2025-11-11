# VMWare-Workstation-Twaeks
Bei Performanceproblemen mit VMWare Workstation kan man folgendes tun:

```
powercfg /powerthrottling disable /path "C:\Program Files (x86)\VMware\VMware Workstation\x64\vmware-vmx.exe"
```
und / oder die Verknüfung > Erweitert << Als Administrator ausführen.


```
fsutil behavior set disablelastaccess 3
```

## VMWare Workstation 25H2
Lustigerweise funktioniert VMWare Workstation 25H2 bei mir sehr performant wie die früheren Versionen. Scheiß Firma, klar steht aus der Frage, wieder gutes Produkt, seltsameweise ja.


## Die Ultimative Performance
Ich weiß nicht welcher von dennen der Perfomancebringer ist, ich denke `sched.mem.pshare.enable`. Da wird keine Speicherdatei auf der Fertplatte erstellt.

```
logging = "FALSE"
MemTrimRate = "0"
prefvmx.minVmMemPct = "100"
mainMem.useNamedFile = "FALSE"
prefvmx.useRecommendedLockedMemSize = "TRUE"
isolation.tools.unity.disable="TRUE"
unity.allowCompositingInGuest="FALSE"
unity.enableLaunchMenu = "FALSE"
unity.showBadges = "FALSE"
unity.showBorders = "FALSE"
unity.wasCapable = "FALSE"
sched.mem.pshare.enable = "FALSE"
snapshot.disabled = "TRUE"
MemAllowAutoScaleDown = "FALSE"
```

## Tastatur Lag
Bei Problemen mit Tastaturverzögerung kann man diese beiden Punkte aktivieren. Bei mir bringt das einen riesigen Performancevorteil.

```
mks.vk.syncPerEndFrame = "TRUE"
mks.dx12.syncPerEndFrame = "TRUE"
```
