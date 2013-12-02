# Data items

The following data items are used by this service:

## Input pregnancy data (registerPregnancy)

* **growchartid**: [optional] Unique ID for a chart / pregnancy
* **growchartversion**: [optional] GROW version of co-efficients
* **maternalheight**: Maternal height (at booking/dating scan)
* **maternalweight**: Maternal weight (at booking/dating scan)
* **ethnicity**: Ethnicity code in the scope of the `growchartversion`
* **parity**: Parity (at booking/dating scan)
* **edd**: EDD (at booking/dating scan)
* **requestdate**: [optional] Current date for calculations. If left blank, today’s date is used. (at booking/dating scan so gestation can be calculated)

## Input measurements (addMeasurement: optional)

* **type**: Type of measurement - fundal height, estimated fetal weight or birth weight (during pregnancy or at birth)
* **value**: Measured value (during pregnancy or at birth)
* **measurementdate**: date of fundal height measurement / estimated fetal weight / birth weight (during pregnancy or at birth)

## Input birthweight centile (registerBirth)

* **growchartid**: Grow chart id.
* **babydob**: Date of birth (at birth – used to calculate gestation only and not stored)
* **birthgestation**: Gestation (at birth) [derived from date of birth and EDD]
* **birthweight**: Birth weight (at birth)
* **babygender**: Sex (at birth)
* **antenataliugrdetection**: Antenatal detection of IUGR (at birth)

## Input temporary data for image or PDF (not stored)

* **firstname**: First name (at booking/dating scan)
* **surname**: Surname (at booking/dating scan)
* **maternaldob**: Maternal DOB (at booking/dating scan)
* **maternalreference**: Local maternal reference number (at booking/dating scan)
* **babyname**: Previous baby name [or birth order number] (at booking/dating scan)
* **babygender**: Previous baby gender (at booking/dating scan)
* **babygestation**: Previous baby gestation (at booking/dating scan)
* **babybirthweight**: Previous baby weight (at booking/dating scan)

## Output (getData)

* **bmi**: BMI (at booking/dating scan)
* **tow**: Term Optimal Weight (at booking/dating scan)
* **custombirthweightcentile**: Customised birth weight centile (at birth)
* **babycentile**: Previous baby centile (at booking/dating scan for each baby)

The web service saves relevant data items that produce or update the GROW chart and data items that will report back the organisation's IUGR rates and antenatal detection rates only. No patient-identifiable data items are stored.
