# EqualAreaBufferGenerator
This repository is created for publishing a QGIS plugin: EqualAreaBufferGenerator(EABG).

This plugin can help generating equal area or multiple area Peripheral buffer for multi-polygon. 

Buffer for each polygon would be generated seperately. 

Be aware that the Peripheral buffer area doesn't take the polygon's own area into account.

![image](https://user-images.githubusercontent.com/47760513/120260743-0f8c4c80-c2c9-11eb-9e30-bff2e54155e1.png)
![image](https://user-images.githubusercontent.com/47760513/120261381-60e90b80-c2ca-11eb-92ba-9c4866efbe70.png)


## Test and use
This plugin is still in experimental version. 

***EABG_plugin.zip*** shoule be downloaded and saved in your **QGIS plugin directory** (e.g., C:\Users\UserName\AppData\Roaming\QGIS\QGIS3\profiles\default\python\plugins). Reload the QGIS, this plugin ***EqualAreaBufferGenerator*** can be open from the **Plugins** drop-down menu.

***EqualAreaBufferGenerator.py*** is for anyone who just want to check the core code and pull requests.

***Test.shp*** is a shapfile contains a multi-polygon layer. It is for testing this plugin as an input layer. 

If there is any problem, or any idea, please do not hesitate to contact me. E-mail: linkeouyang@163.com

## Input Data and Parameter Setting
### Import Layer (.shp)
The ComboBox would only show the vector layers which has been already imported in QGIS.

This layer should be MultiPolygon with CRS. Projection coordinates using **meters** as Unit is recommended. Unprojected Geographical coordinates is also workable, however, the ***Buffer range*** setting should change accordingly (See **Buffer range** setting part below). 

### Multiple factor
To generate equal area buffer, ***mutiple factor*** should be set to **1**.

Multiple area buffer can also be generated by setting corresponding **multiple factor**.

### Buffer range
The **Unit** of ***Min***, ***Max***, and ***Step*** are consistent with layer's CRS.

***Min*** should be set to be the **Minimum width** of buffer which make all polygons' buffer area smaller than its own area. 

***Max*** should be set to be the **Maximal width** of buffer which make all polygons' buffer area greater than its own area.

***Step*** is the precision value of buffer width defined by users.

If the ***Min*** and ***Max*** are unsuitable, an Error alert would show. A precise ***Min*** and ***Max***, along with a rough ***Step***, would reduce the computing time.
