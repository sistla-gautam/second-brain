## jump server access
for deployment related stuff
```bash
sshpass -p YokoYoko@2025 ssh ydxuser@20.6.35.2
```
**Mongo access**
can only  be access from the jump server 
```bash
ssh ydxyokogawa@10.202.64.14
3Aa4Eh6v*9 
```
---
### restarting the pod once the STS is edited 
- edit the STS
```bash
kubectl edit sts appsmith-helm -n appsmith-helm
```
- once this is done, do a rollout restart of the pod
```bash
kubectl rollout restart sts <> stsname -n namespace
```
- once this is done, delete the pod
- the STS will allow it to restart the pod once this is done automatically 

---
```
 BACKEND_PORT: "8080"
  RTS_PORT: "8091"
  SUPERVISOR_PORT: "9001"
```