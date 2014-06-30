# XML POST examples

**The `licensekey` and `token` can be passed attatched to the url or the request body node.**

    <licensekey>myapikey</licensekey>
    <token>demotoken</token>

## registerPregnancy

### URI
    
    /api/grow/xml/registerpregnancy/?licensekey=myapikey&token=demotoken&growchartid=0000001

### Input

    <pregnancy>
        <!-- growchartid is optional -->
        <growchartid>0000001</growchartid>
        <maternalheight>163</maternalheight>
        <maternalweight>62</maternalweight>
        <edd>20140115</edd>
        <parity>0</parity>
        <ethnicity>0</ethnicity>
        <growversion>NL2013</growchartversion> 
        <requestdate>20131125</requestdate>
    </pregnancy>

### Output

    <growchart>
        <growchartid>0000001</growchartid>
        <growversion>NL2013</growversion>
        <language>en_UK</language>
        <format>png</format>
        <display_p95_line>false</display_p95_line>
        <grid_line_by_weight>false</grid_line_by_weight>
        <gray_scale>false</gray_scale>
    </growchart>

## addMeasurement

### URI
    
    /api/grow/xml/addmeasurement/?licensekey=myapikey&token=demotoken

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

### URI
    
    /api/grow/xml/getchartimage/?licensekey=myapikey&token=demotoken

### Input:

    <chart growchartid="0000001">
        <growchartid>0000001</growchartid>
        <reference>0000001</reference>
        <height>600</height>
        <width>800</width>
        <language>en-US</language>
        <firstname>Luo</firstname><!-- optional -->
        <lastname>Weimeng</lastname><!-- optional -->
        <maternaldob>19870222</maternaldob><!-- optional -->
        <displayp95line>false</displayp95line>
        <gridlinebyweight>false</gridlinebyweight>
        <grayscale>false</grayscale>
    </chart>

### Output:

    <growchart>
        <growchartid>0000001</growchartid>
        <growversion>NL2013</growversion>
        <width>800</width>
        <height>600</height>
        <language>en-US</language>
        <format>png</format>
        <firstname>Luo</firstname>
        <lastname>Weimeng</addMeasurementlastname>
        <maternaldob>19870222</maternaldob>
        <reference>0000001</reference>
        <display_p95_line>false</display_p95_line>
        <grid_line_by_weight>false</grid_line_by_weight>
        <gray_scale>false</gray_scale>
        <url>
            <![CDATA[https://www.grow-services.net/api/grow/getchartimage/?licensekey=myapikey&.....&format=png]]>
        </url>
    </growchart>

## getData

### URI
    
    /api/grow/xml/getdata/[?licensekey=myapikey&token=demotoken&growchartid=0000001]
    
### Input:

    <datacentile>
        <licensekey>myapikey</licensekey>
        <token>demotoken</token>
        <growchartid>0000001</growchartid>
        <weight>60</weight>
        <requestdate>20131130</requestdate><!-- Optional, if not set use the request date-->
    </datacentile>

### Output:

    <datacentile>
        <growchartversion>NL2013</growchartversion>
        <tow>3596</tow>
        <bmi>24.24</bmi>
        <custombirthweightcentile>0</custombirthweightcentile>
    </datacentile>


## registerBirth

### URI
    
    /api/grow/xml/registerbirth/?licensekey=myapikey&token=demotoken


### Input:

    <birth>
        <growchartid>0000001</growchartid>
        <babydob>20140115</babydob>
        <birthweight>40</birthweight>
        <babygender>M</babygender><!--F or M-->
        <antenataliugrdetection>N</antenataliugrdetection><!-- Y or N -->
    </birth>

## registerBaby

### URI
    
    /api/grow/xml/registerbaby/?licensekey=myapikey&token=demotoken

### Input:

    <baby>
        <growchartid>0000021</growchartid>
        <babynr>0</babynr>
        <babydob>20120115</babydob>
        <birthgestation>41</birthgestation>
        <birthweight>4000</birthweight>
        <babygender>M</babygender>
        <babyname>Tom</babyname>
        <previousgrowchartid>0000014</previousgrowchartid>
    <baby>

## get pdf

### URI

    /api/grow/xml/getpdf/?licensekey=myapikey&token=demotoken
    
### Input:

    <pdf>
        <growchartid>0000021</growchartid>
        <firstname>Luo</firstname>
        <lastname>Weimeng</lastname>
        <maternaldob>19870222</maternaldob>
        <reference>0000001</reference>
        <babyname>Richeng</babyname>
        <babygender>M</babygender>
        <babygestation>41</babygestation>
        <babybirthweight>4000</babybirthweight>
        <displayp95line>false</displayp95line>
        <gridlinebyweight>false</gridlinebyweight>
        <grayscale>false</grayscale>
    </pdf>

### Output:

    <growchart>
        <growchartid>0000021</growchartid>
        <growversion>NL2013</growversion>
        <language>en_UK</language>
        <firstname>Luo</firstname>
        <lastname>Weimeng</lastname>
        <maternaldob>19870222</maternaldob>
        <reference>0000001</reference>
        <display_p95_line>false</display_p95_line>
        <grid_line_by_weight>false</grid_line_by_weight>
        <gray_scale>false</gray_scale>
        <babyname>Richeng</babyname>
        <babygender>M</babygender>
        <babygestation>41</babygestation>
        <babybirthweight>4000</babybirthweight>
        <url><![CDATA[https://www.grow-services.net/api/grow/getchartimage/?licensekey=myapikey.....]]></url>
    </growchart>


## clear data

### URI

    /api/grow/xml/cleardata/

### Input:

    <cleardata>
        <growchartid>0000021</growchartid>
    </cleardata>