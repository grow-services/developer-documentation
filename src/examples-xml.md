# XML POST examples


**The `licensekey` and `token` can be passed attatched to the url or the request body node.**

```xml
<licensekey>myapikey</licensekey>
<token>demotoken</token>
```

## registerPregnancy

### URI
    
    /api/grow/v3/xml/registerpregnancy/?licensekey=myapikey&token=demotoken&growchartid=0000001

### Method: POST

### Input
```xml
    <pregnancy>
        <!-- growchartid is optional -->
        <growchartid>0000001</growchartid>
        <maternalheight>163</maternalheight>
        <maternalweight>62</maternalweight>
        <edd>20140115</edd>
        <parity>0</parity>
        <ethnicity>0</ethnicity>
        <growchartversion>NL2013</growchartversion>
        <requestdate>20131125</requestdate>
    </pregnancy>
```
#### The ethnicity 

When the grow version is NL2013 

    [1] => Netherlands
    [2] => Other Eurpean
    [3] => North African
    [4] => Other African
    [5] => Turkish
    [6] => Indian Subcontinent
    [7] => Asian (SE, FE)
    [8] => Asian (Nth, Cent); Middle East
    [9] => Western (US, Aust etc)
    [10] => Non-Western (SAmer etc)
    [11] => Mixed
    [12] => Other
    [UNK] => Unclassified (defaults to Netherlands)


When the grow version is UK2014 (MRX04b)

    [1]: British European
    [2]: East European
    [3]: Irish European
    [4] : North European
    [5]: South European
    [6]: West European
    [7]: North African
    [8]: Sub-Sahara African
    [9]: Middle Eastern
    [10]: Bangladeshi
    [11]: Indian
    [12]: Pakistani
    [13]: Chinese
    [14]: Other Far East
    [15]: South East Asian
    [16]: Caribbean
    [17]: Mixed African-European
    [18]: Mixed Asian-European
    [19]: Mixed Caribbean-European
    [20]: Other
    [21]: Unclassified

NZ2014 (New Zealand NAnd)

    [1]: NZ European
    [2]: Maori
    [3]: Tongan
    [4]: Chinese
    [5]: Indian
    [6]: African
    [7]: Other Asianc
    [8]: Cook Island Maori
    [9]: Fijian
    [10]: Middle Eastern
    [11]: Niuean
    [12]: Other European
    [13]: Other Pacific Islander
    [14]: South East Asian
    [15]: Samoan
    [16]: Latin American
    [17]: Other
    [18]: Unclassified
    
    
### Output
```xml
    <growchart>
        <growchartid>0000001</growchartid>
        <growversion>NL2013</growversion>
        <language>en_UK</language>
        <format>png</format>
        <display_p95_line>false</display_p95_line>
        <grid_line_by_weight>false</grid_line_by_weight>
        <gray_scale>false</gray_scale>
    </growchart>
```

## addMeasurement

### URI
    
    /api/grow/v3/xml/addmeasurement/?licensekey=myapikey&token=demotoken

### Method: POST

### Input
```xml
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
```

## Remove measurement

### URI

    /api/grow/v3/xml/pregnancy/{growchartid}/measurement/{measurementuuid}?licensekey=myapikey&token=demotoken

### Method: DELETE

## Update measurement

### URI

    /api/grow/v3/xml/pregnancy/{growchartid}/measurement/{measurementuuid}?licensekey=myapikey&token=demotoken
   
### Method: PUT

### Input

```xml
    <measurements>
        <measurement>
            <type>birthweight</type>
            <date>20121011</date>
            <value>2600</value>
        </measurement>
    </measurements>
```

## getChartImage

### URI
    
    /api/grow/v3/xml/getchartimage/?licensekey=myapikey&token=demotoken

### Input:
```xml
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
```

### Output:
```xml
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
            <![CDATA[https://www.grow-services.net/api/grow/v3/getchartimage/?licensekey=myapikey&.....&format=png]]>
        </url>
    </growchart>
```

## getData

### URI
    
    /api/grow/v3/xml/getdata/[?licensekey=myapikey&token=demotoken&growchartid=0000001]
    
### Input:
```xml
    <datacentile>
        <licensekey>myapikey</licensekey>
        <token>demotoken</token>
        <growchartid>0000001</growchartid>
        <weight>60</weight>
        <requestdate>20131130</requestdate><!-- Optional, if not set use the request date-->
    </datacentile>
```

### Output:

```xml
    <datacentile>
        <growchartversion>NL2013</growchartversion>
        <tow>3596</tow>
        <bmi>24.24</bmi>
        <custombirthweightcentile>0</custombirthweightcentile>
    </datacentile>
```

## registerBirth

### URI
    
    /api/grow/v3/xml/registerbirth/?licensekey=myapikey&token=demotoken


### Input:

```xml
    <birth>
        <growchartid>0000001</growchartid>
        <babydob>20140115</babydob>
        <birthweight>40</birthweight>
        <babygender>M</babygender><!--F or M-->
        <antenataliugrdetection>N</antenataliugrdetection><!-- Y or N -->
    </birth>
```

## registerBaby

### URI
    
    /api/grow/v3/xml/registerbaby/?licensekey=myapikey&token=demotoken

### Input:

```xml
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
```

## get pdf

### URI

    /api/grow/v3/xml/getpdf/?licensekey=myapikey&token=demotoken
    
### Input:

```xml
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
```

### Output:

```xml
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
        <url><![CDATA[https://www.grow-services.net/api/grow/v3/getchartimage/?licensekey=myapikey.....]]></url>
    </growchart>
```

## clear data

### URI

    /api/grow/v3/xml/cleardata/

### Input:

```xml
    <cleardata>
        <growchartid>0000021</growchartid>
    </cleardata>
```

## get pregnancy

### URI

    /api/grow/v3/xml/getpregnancy/0000021
    
### Output:

```xml
    <growchart>
        <growchartid>0000014</growchartid>
        <growversion>NL2013</growversion>
        <language>en_UK</language>
        <format>png</format>
        <display_p95_line>false</display_p95_line>
        <grid_line_by_weight>false</grid_line_by_weight>
        <gray_scale>false</gray_scale>
        <babygender>M</babygender>
        <babybirthweight>4000</babybirthweight>
        <maternalheight>165</maternalheight>
        <maternalweight>60</maternalweight>
        <ethnicity>12</ethnicity>
        <edd>1395381715</edd>
        <babydob>1395381715</babydob>
        <antenataliugrdetection>N</antenataliugrdetection>
    </growchart>
```

## Register pregnancies (New api for registering more pregnancies at once)

### URI

    /api/grow/v3/xml/registerpregnancies

### Input

```xml
<pregnancies>
    <pregnancy>
        <maternalheight>166</maternalheight>
        <maternalweight>66</maternalweight>
        <ethnicity>1</ethnicity>
        <parity>1</parity>
        <edd>20140320</edd>
        <growchartversion>NL2013</growchartversion>
        <growchartid>0000021</growchartid>
        <requestdate />
        <birth>
            <growchartid>0000021</growchartid>
            <babydob>20140724</babydob>
            <birthweight>4000</birthweight>
            <babygender>F</babygender>
            <antenataliugrdetection>N</antenataliugrdetection>
            <suspected />
        </birth>
        <previousbabies>
            <babynr>0</babynr>
            <babydob>20130701</babydob>
            <birthgestation>38.86</birthgestation>
            <birthweight>7800</birthweight>
            <babygender>F</babygender>
            <babyname>Jill</babyname>
            <previousgrowchartid>0000013</previousgrowchartid>
        </previousbabies>
        <measurements>
            <measurement>
                <date>20140206</date>
                <type>fundalheight</type>
                <value>32.43</value>
            </measurement>
            <measurement>
                <date>20140306</date>
                <type>efw</type>
                <value>121</value>
            </measurement>
            <measurement>
                <date>20140724</date>
                <type>birthweight</type>
                <value>4000</value>
            </measurement>
        </measurements>
        <chart>
            <reference>66458</reference>
            <height>750</height>
            <width>750</width>
            <language>en_US</language>
            <firstname>Jill</firstname>
            <lastname>Test</lastname>
            <maternaldob>20130701</maternaldob>
            <displayp95line>false</displayp95line>
            <gridlinebyweight>false</gridlinebyweight>
            <grayscale>false</grayscale>
        </chart>
    </pregnancy>
</pregnancies>
```
