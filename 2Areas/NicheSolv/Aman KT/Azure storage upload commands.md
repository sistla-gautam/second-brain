## adding files to azure storage
- this is to add the unit conversion file to azure storage
```bash
az storage blob upload --account-name dv1dxpdevsa189 -f unitconversion.csv -c ydxvisualization -n "data-config/source-def/unitconversion.csv" --sas-token "se=2025-05-28T13%3A40Z&sp=rwdl&spr=https&sv=2022-11-02&sr=c&sig=I9xIfo0DxAROMulZHh6eDGud1%2B7Okayz0WhrWZHFoB8%3D" --overwrite
```
> Make sure the file is only named as `unitconversion.csv` and nothing else

- this is to add the DataSourceDef file to azure storage
```bash
az storage blob upload --account-name dv1dxpdevsa189 -f DataSourceDef.csv -c ydxvisualization -n "data-config/source-def/DataSourceDef.csv" --sas-token "se=2025-05-28T13%3A40Z&sp=rwdl&spr=https&sv=2022-11-02&sr=c&sig=I9xIfo0DxAROMulZHh6eDGud1%2B7Okayz0WhrWZHFoB8%3D" --overwrite
```
> Make sure the file is only named as `DataSourceDef.csv` and nothing else

---
## Final files
- DataSourceDef csv
![[Second Brain/5Files/DataSourceDef 2.csv]]

- Unit conversion csv
![[unitconversion.csv]]