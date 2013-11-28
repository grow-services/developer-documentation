# Workflow examples

## Create PDF customised growth chart

1. User enters relevant data items as part of their routine care at booking or following the dating scan and clicks on "Download PDF" button
2. MIS calls `registerPregnancy` and sends data items - `apikey`, `token`, `growchartid` [optional], `growchartversion` [optional], `maternalheight`, `maternalweight`, `ethnicity`, `parity`, `edd` and `requestdate` to web service. The web service stores all items and returns the `growchartid` to the calling application.
3. MIS calls `getPDF` and sends data items - `apikey`, `token`, `growchartid`, `firstname`, `surname`, `maternaldob`, `maternalreference`, `babyname`, `babygender`, `babygestation`, `babybirthweight`. No items are stored. The web service generates the customised `PDF` file and returns it to the application.
4. If parity >0 but no previous baby details entered; PDF to display "No details" against each missing baby details.
5. MIS calls `getData` and sends data items - `apikey`, `token`, `growchartid`. The web service returns the `bmi`, `babybirthcentile` and `tow`.
6. If any changes are made to the data items that help produce the customised growth chart PDF, the MIS will call `registerPregnancy` again, with the same `growchartid` to update the data stored at the web service which will return the same unique chart identifier.

## Create customised growth chart (image) for MIS

1. User enters relevant data items as part of their routine care at booking or following the dating scan and clicks on "View chart" button
2. MIS calls `registerPregnancy` and sends data items - `apikey`, `token`, `growchartid` [optional], `growchartversion` [optional], `maternalheight`, `maternalweight`, `ethnicity`, `parity`, `edd`and `requestdate`, to web service. The web service stores all items and returns the `growchartid` to the calling application.
3. MIS calls `getImage` and sends data items - `apikey`, `token`, `growchartid`, `firstname`, `lastname`, `date of birth`. No items are stored. The web service generates the customised image (PNG) file and returns it to the application.
4. If any changes are made to the data items that help produce the customised growth chart image, the MIS will call `registerPregnancy` again, with the same chartid to update the data stored at the web service which will return the same unique chart identifier.

## Previous children's birthweight centiles

1. User enters previous baby details as part of routine care at booking and clicks on "Get centile" button 
2. MIS calls `registerBirth` and sends data items - `apikey`, `token`, `growchartid`, `birthorder`, `babyname`, `babygender`, `babygestation`, `babybirthweight`; to web service and returns the `babybirthcentile`.
3. No data is saved in the web service


## Plot fundal height measurement

1. User enters fundal height measurement (cm) as part of routine care during an antenatal appointment and clicks on "Save" button
2. MIS calls `addMeasurement` and sends data items - `apikey`, `token`, `growchartid`, `date`, `type` and `measurement` to web service. The items will be stored.
3. MIS calls `getPDF` or `getImage`, all measurements will be plotted onto the chart.

## Plot estimated fetal weight

1. User enters estimated fetal weight measurement (g) as part of routine care during an antenatal appointment and clicks on "Save" button
2. MIS calls `addMeasurement` and sends data items - `apikey`, `token`, `growchartid`, `date`, `type` and `measurement` to web service. The items will be stored.
3. MIS calls `getPDF` and/or `getImage`, all measurements will be plotted onto the chart.

## Create customised birthweight centile

1. User enters baby birth details as part of routine care following birth of the baby and clicks on "Get centile".
2. MIS calls `registerBirth` and sends data items - `apikey`, `token`, `growchartid`, `babydob`, `birthgestation` (derived from date of birth and EDD), `birthweight`, `babygender` and `antenataliugrdetection` to web service. The items non-identifiable data items are stored.
3. MIS calls `getData` and sends data items - `apikey`, `token`, `growchartid`
4. The web service returns structured data containing the `custombirthweightcentile` 
