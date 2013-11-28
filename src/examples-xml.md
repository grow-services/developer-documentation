# XML POST examples

## registerPregnancy

### Input

    <pregnancy>
        <!-- growchartid is optional -->
        <growchartid>0000001</growchartid>
        <maternalheight>163</maternalheight>
        <maternalweight>62</maternalweight>
        <edd>20140115</edd>
        <parity>0</parity>
        <ethnicity>0</ethnicity>
        <growchartversion>NL2012</growchartversion> 
        <requestdate>20131125</requestdate>
    </pregnancy>

### Output

    <growchart>
        <growchartid>0000001</growchartid>
        <growversion>NL2012</growversion>
    </growchart>

## addMeasurement

### Input

    <measurements growchartid="0000001">
        <measurement>
            <type>birthweight</type>
            <date>20121011</date>
            <value>2600</value>
        </measurement>
        <measurement>
            <type>fundalheight</type>
            <date>20121111</date>
            <value>30</value>
        </measurement>
        <measurement>
            <type>efw</type>
            <date>20121111</date>
            <value>1700</value>
        </measurement>
        ...
    </measurements>

## getChartImage

### Input:

    <chart growchartid="0000001">
        <growchartid>0000001</growchartid>
        <width>750</width>
        <height>450</height>
        <language>en_UK</language>
        <format>png</format><!- MUST be png-->
        <firstname>Luo</firstname><!-- optional -->
        <lastname>Weimeng</lastname><!-- optional -->
        <maternaldob>19870222</maternaldob><!-- optional -->
    </chart>

### Output:

Image file in requested format.

## getData

### Input:

### Output:

    <datacentile>
        <growchartversion>NL2012</growchartversion>
        <tow>3571.235</tow>
        <bmi>24.32</bmi>
    </datacentile>


## registerBirth

### Input:

    <birth>
        <growchartid>0000001</growchartid>
        <babydob>20140115</babydob>
        <birthgestation>20140115</birthgestation>
        <birthweight>3500</birthweight><!-- gram -->
        <babygender>F</babygender><!--F or M-->
        <antenataliugrdetection>Y</antenataliugrdetection><!-- Y or N -->
    </birth>
