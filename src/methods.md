# Methods

This section of the document describes the available methods in the API. This information is valid regardless of the protocol used (REST, XML, SOAP, etc)

* `registerPregnancy`
* `addMeasurement`
* `getPdf`
* `getChartImage`
* `getData`
* `registerBirth`

## registerPregnancy

This method is used to register a new pregnancy, set the basic details, and establish a unique `growchartid`. `registerPregnancy` is usually followed up by other methods such as `getPdf`, `getData` and/or `getChartImage`

If the MIS can generate a unique reference for this pregnancy, it can be passed in the `growchartid` field. The service will use that reference to identify the chart in other calls. 

If the MIS does not provide a unique reference, you can leave the `growchartid` field empty. The service will generate a unique id, and return it in the response for the MIS to store for future methods.

The growchartversion identifies the set of co-efficients used for this pregnancy, i.e. `UK2013`, `NL2012` or `NL2013`. The field is optional, and if omitted uses the default *current* growchartversion for the country of the caller. It is recommended to omit this field, and let the service automatically select the current growversion. The field is only intended for re-creating legacy charts.

The `ethnicity` is specified in the scope of the growchartversion.

For any given license owner and reference combination, the API will return the same `growchartid`. In other words, the pregnancy is only registered once. If the `growchartid` got lost, it can be retrieved by calling this method again.

If any changes are made to the data items that help produce the customised growth chart, the MIS can call this method again to update the information. The same `growchartid` will be returned.

### Input:

* `apikey`: (see section ‘api keys’)
* `token`: (see section ‘api keys’)
* `growchartid` (optional)
* `growchartversion` (optional)
* `maternalheight`
* `maternalweight`
* `ethnicity`
* `parity`
* `edd`
* `requestdate`

### Output:

* `growchartid`: Unique identifier used as input in all other API methods
* `growversion`

NB The GROW co-efficients version number (growchartversion) will remain the same for the duration of the pregnancy.

## getData

This method is used in combination with `registerPregnancy` when the application needs to retrieve structured data about the pregnancy and/or chart.

### Input

* `apikey`: (see section ‘api keys’)
* `token`: (see section ‘api keys’)
* `growchartid`
* `requestdate`

### Output:

* `growchartversion`
* `bmi`
* `tow`

## getPdf

This method is used by the application to generate a printable version of the customised growth chart along with the referral process in PDF format (Appendix 1 for example). These data items are only required for the PDF image, therefore once embedded in the generated image they are then discarded.

### Input (in addition to registerPregnancy input fields)

* `apikey`: (see section ‘api keys’)
* `token`: (see section ‘api keys’)
* `firstname`
* `surname`
* `maternaldob`
* `maternalreference`
* `babyname`
* `babygender`
* `babygestation`
* `babybirthweight`

### Output:

* `URL` url containing a generated PDF file. The PDF contains a customised growth chart image and referral criteria document

## getChartImage

This method is used in combination with `registerPregnancy` when a Trust needs to integrate the GROW Chart image into the MIS. It will include any previously reported measurements (efw, fundalheight, birthweight) as plot points

The `firstname`, `lastname`, `maternaldob` fields is personally identifiable data, and is therefore optional. If provided, it will be embedded in the generated image after which it will be discarded. 

### Input:

* `apikey`: (see section ‘api keys’)
* `token`: (see section ‘api keys’)
* `growchartid`
* `width`: Range: 320px - 1024px
* `height`: Range: 240px - 768px
* `format`: (must be `.png`)
* `language`: Default: `en_UK`
* `firstname` (optional)
* `lastname` (optional)
* `maternaldob` (optional)
* `maternalreference` (optional)

### Output:

* `url`: URL containing a generated PNG file. The PNG contains a customised growth chart image

## registerBirth

This method is used in combination with `registerPregnancy` to register birth details of the pregnancy related to the requested `growchartid`. It is used to determine a customised birthweight centile, and keep track of antenataliugrdetection rates.

### Input:

* `apikey`: (see section ‘api keys’)
* `token`: (see section ‘api keys’)
* `growchartid`
* `babydob`
* `babygender`
* `babyweight`
* `antenataliugrdetection` : SGA/FGR detected/diagnosed antenatally (based on one or serial ultrasound EFWs or abnormal doppler, OR clinically assessed at term leading to delivery)
* `suspected` : Referred for suspected SGA/FGR antenatally (referred for further investigation on basis of fundal height measurements)

### Output:

* nothing

## registerBaby

This method is used in combination with `registerPregnancy` to register previous baby details, related to the requested `growchartid`. Note that it should explicitly exclude the baby details of the current pregnancy. Those details should be sent through the `registerBirth` method. These previous baby details will be embedded in the image returned by `getChartImage`.

### Input:

* `apikey`: (see section ‘api keys’)
* `token`: (see section ‘api keys’)
* `growchartid`
* `babynr`
* `babydob`
* `babygestation`
* `birthweight`
* `babygender`
* `antenataliugrdetection`: SGA/FGR detected/diagnosed antenatally (based on one or serial ultrasound EFWs or abnormal doppler, OR clinically assessed at term leading to delivery) Optional
* `suspected` : Referred for suspected SGA/FGR antenatally (referred for further investigation on basis of fundal height measurements) Optional

### Output:

* nothing

## addMeasurement

The MIS uses this method to add measurements to the chart. If plotting is enabled, these will be displayed to the image.

### Input:

* `apikey`: (see section ‘api keys’)
* `token`: (see section ‘api keys’)
* `growchartid`
* `date`: Format: YYYYMMDD
* `type`: `efw`, `fundalheight`, `birthweight`
* `measurement`: EFW (g), fundal height (cm) or birthweight (g)

### Output:

* `growchartid` The grow chart id
* `date`: The measurement date.
* `type`: `efw`, `fundalheight`, `birthweight`
* `measurement`: EFW (g), fundal height (cm) or birthweight (g)
* `uuid` The measurement uuid, it is used to remove or update this measurement.

## Remove measurement

### Input:

* `apikey`: (see section ‘api keys’)
* `token`: (see section ‘api keys’)
* `growchartid` Grow chart id
* `uuid` The measurement uuid
