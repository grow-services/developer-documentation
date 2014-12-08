# SOAP request/response examples

## The grow soap wsdl location

https://www.grow-services.net/api/grow/soap/?wsdl

## The request/response examples

### registerPregnancy

* Request

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:soap="https://www.grow-services.net/api/grow/soap/">
   <soapenv:Header>
      <soap:authenticate>
         <licensekey>apikey</licensekey>
         <token>apitoken</token>
      </soap:authenticate>
   </soapenv:Header>
   <soapenv:Body>
      <soap:registerPregnancy>
         <maternalheight>165</maternalheight>
         <maternalweight>66</maternalweight>
         <ethnicity>1</ethnicity>
         <parity>1</parity>
         <edd>20140320</edd>
         <growversion>NL2013</growversion>
         <growchartid>0000021</growchartid>
         <requestdate xsi:nil="true"/>
      </soap:registerPregnancy>
   </soapenv:Body>
</soapenv:Envelope>
```


* Response

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="https://www.grow-services.net/api/grow/soap/">
<SOAP-ENV:Header>
   <authenticate>
    <item>
       <key>authenticateResult</key>
       <value>Authenticate passed</value>
    </item>
   </authenticate>
</SOAP-ENV:Header>
<SOAP-ENV:Body>
<ns1:registerPregnancyResponse>
 <registerPregnancyResult>
    <growchartid>0000021</growchartid>
    <growversion>NL2013</growversion>
    <language>en_UK</language>
    <format>png</format>
    <display_p95_line>false</display_p95_line>
    <grid_line_by_weight>false</grid_line_by_weight>
    <gray_scale>false</gray_scale>
 </registerPregnancyResult>
</ns1:registerPregnancyResponse>
</SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### registerBirth

* Request

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:soap="https://www.grow-services.net/api/grow/soap/">
   <soapenv:Header>
      <soap:authenticate>
         <licensekey>apikey</licensekey>
         <token>apitoken</token>
      </soap:authenticate>
   </soapenv:Header>
   <soapenv:Body>
      <soap:registerBirth>
         <growchartid>0000021</growchartid>
         <babydob>20140115</babydob>
         <birthweight>40</birthweight>
         <babygender>M</babygender>
         <antenataliugrdetection>N</antenataliugrdetection>
         <suspected>N</suspected>
      </soap:registerBirth>
   </soapenv:Body>
</soapenv:Envelope>
```

* Response

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="https://www.grow-services.net/api/grow/soap/">
   <SOAP-ENV:Header>
      <authenticate>
         <item>
            <key>authenticateResult</key>
            <value>Authenticate passed</value>
         </item>
      </authenticate>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:registerBirthResponse>
         <registerBirthResult>ok</registerBirthResult>
      </ns1:registerBirthResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### registerBaby

* Request

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:soap="https://www.grow-services.net/api/grow/soap/">
   <soapenv:Header>
      <soap:authenticate>
         <licensekey>apikey</licensekey>
         <token>apitoken</token>
      </soap:authenticate>
   </soapenv:Header>
   <soapenv:Body>
      <soap:registerBaby>
         <growchartid>0000021</growchartid>
         <babynr>0</babynr><!-- This is the baby No. you can set it for order the baby -->
         <babydob>20120115</babydob><!-- The babydob should be the yyyyMMdd format -->
         <birthgestation>41</birthgestation>
         <birthweight>4000</birthweight>
         <babygender>M</babygender>
         <babyname>Tom</babyname>
         <previousgrowchartid>0000014</previousgrowchartid>
      </soap:registerBaby>
   </soapenv:Body>
</soapenv:Envelope>
```

* Response

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="https://www.grow-services.net/api/grow/soap/">
   <SOAP-ENV:Header>
      <authenticate>
         <item>
            <key>authenticateResult</key>
            <value>Authenticate passed</value>
         </item>
      </authenticate>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:registerBabyResponse>
         <registerBabyResult>ok</registerBabyResult>
      </ns1:registerBabyResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### getPdf

* Request

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:soap="https://www.grow-services.net/api/grow/soap/">
   <soapenv:Header>
      <soap:authenticate>
         <licensekey>apikey</licensekey>
         <token>apitoken</token>
      </soap:authenticate>
   </soapenv:Header>
   <soapenv:Body>
      <soap:getPdf>
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
      </soap:getPdf>
   </soapenv:Body>
</soapenv:Envelope>
```

* Response

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="https://www.grow-services.net/api/grow/soap/">
   <SOAP-ENV:Header>
      <authenticate>
         <item>
            <key>authenticateResult</key>
            <value>Authenticate passed</value>
         </item>
      </authenticate>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getPdfResponse>
         <getPdfResult>
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
            <url><![CDATA[http://127.0.0.1/api/grow/getchartpdf/?licensekey=apikey&token=apitoken&growchartid=0000021&language=en_UK&growversion=NL2013&firstname=Luo&lastname=Weimeng&maternaldob=19870222&babyname=Richeng&babygender=M&babybirthweight=4000&babygestation=41&reference=0000001&displayp95line=false&gridlinebyweight=false&grayscale=false]]></url>
         </getPdfResult>
      </ns1:getPdfResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### getData

* Request

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:soap="https://www.grow-services.net/api/grow/soap/">
   <soapenv:Header>
      <soap:authenticate>
         <licensekey>apikey</licensekey>
         <token>apitoken</token>
      </soap:authenticate>
   </soapenv:Header>
   <soapenv:Body>
      <soap:getData>
         <growchartid>0000021</growchartid>
         <requiredate/>
         <weight>60</weight>
      </soap:getData>
   </soapenv:Body>
</soapenv:Envelope>
```

* Response

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="https://www.grow-services.net/api/grow/soap/">
   <SOAP-ENV:Header>
      <authenticate>
         <item>
            <key>authenticateResult</key>
            <value>Authenticate passed</value>
         </item>
      </authenticate>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getDataResponse>
         <getDataResult>
            <growchartversion>NL2013</growchartversion>
            <tow>3596</tow>
            <bmi>24.24</bmi>
            <custombirthweightcentile>0</custombirthweightcentile>
         </getDataResult>
      </ns1:getDataResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### getChartImage

* Request

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:soap="https://www.grow-services.net/api/grow/soap/">
   <soapenv:Header>
      <soap:authenticate>
         <licensekey>apikey</licensekey>
         <token>apitoken</token>
      </soap:authenticate>
   </soapenv:Header>
   <soapenv:Body>
      <soap:getChartImage>
         <growchartid>0000021</growchartid>
         <reference>0000001</reference>
         <height>600</height>
         <width>800</width>
         <language>en-US</language>
         <firstname>Luo</firstname>
         <lastname>Weimeng</lastname>
         <maternaldob>19870222</maternaldob>
         <displayp95line>false</displayp95line>
         <gridlinebyweight>false</gridlinebyweight>
         <grayscale>false</grayscale>
      </soap:getChartImage>
   </soapenv:Body>
</soapenv:Envelope>
```

* Response

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="https://www.grow-services.net/api/grow/soap/">
   <SOAP-ENV:Header>
      <authenticate>
         <item>
            <key>authenticateResult</key>
            <value>Authenticate passed</value>
         </item>
      </authenticate>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getChartImageResponse>
         <getChartImageResult>
            <growchartid>0000021</growchartid>
            <growversion>NL2013</growversion>
            <width>800</width>
            <height>600</height>
            <language>en-US</language>
            <format>png</format>
            <firstname>Luo</firstname>
            <lastname>Weimeng</lastname>
            <maternaldob>19870222</maternaldob>
            <reference>0000001</reference>
            <display_p95_line>false</display_p95_line>
            <grid_line_by_weight>false</grid_line_by_weight>
            <gray_scale>false</gray_scale>
            <url><![CDATA[http://127.0.0.1/api/grow/getchartimage/?licensekey=apikey&token=apitoken&growchartid=0000021&width=800&height=600&language=en-US&growversion=NL2013&firstname=Luo&lastname=Weimeng&maternaldob=19870222&format=png&reference=0000001&displayp95line=false&gridlinebyweight=false&grayscale=false]]></url>
         </getChartImageResult>
      </ns1:getChartImageResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### addMeasurement

* Request

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:soap="https://www.grow-services.net/api/grow/soap/">
   <soapenv:Header>
      <soap:authenticate>
         <licensekey>apikey</licensekey>
         <token>apitoken</token>
      </soap:authenticate>
   </soapenv:Header>
   <soapenv:Body>
      <soap:addMeasurement>
         <growchartid>0000021</growchartid>
         <date>20140301</date>
         <type>birthweight</type>
         <value>2600</value>
      </soap:addMeasurement>
   </soapenv:Body>
</soapenv:Envelope>
```

* Response

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="https://www.grow-services.net/api/grow/soap/">
   <SOAP-ENV:Header>
      <authenticate>
         <item>
            <key>authenticateResult</key>
            <value>Authenticate passed</value>
         </item>
      </authenticate>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:addMeasurementResponse>
         <addMeasurementResult>ok</addMeasurementResult>
      </ns1:addMeasurementResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### clearData

* Request

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:soap="https://www.grow-services.net/api/grow/soap/">
   <soapenv:Header>
      <soap:authenticate>
         <licensekey>apikey</licensekey>
         <token>apitoken</token>
      </soap:authenticate>
   </soapenv:Header>
   <soapenv:Body>
      <soap:clearData>
         <growchartid>0000021</growchartid>
      </soap:clearData>
   </soapenv:Body>
</soapenv:Envelope>
```

* Response

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="https://www.grow-services.net/api/grow/soap/">
   <SOAP-ENV:Header>
      <authenticate>
         <item>
            <key>authenticateResult</key>
            <value>Authenticate passed</value>
         </item>
      </authenticate>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:clearDataResponse>
         <clearDataResult>ok</clearDataResult>
      </ns1:clearDataResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```


### Get pregnancy

* Request

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:soap="https://www.grow-services.net/api/grow/soap/">
   <soapenv:Header>
      <soap:authenticate>
         <licensekey>apikey</licensekey>
         <token>apitoken</token>
      </soap:authenticate>
   </soapenv:Header>
   <soapenv:Body>
      <soap:getpregnancy>
         <growchartid>0000021</growchartid>
      </soap:getpregnancy>
   </soapenv:Body>
</soapenv:Envelope>
```

* Response

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="https://www.grow-services.net/api/grow/soap/">
   <SOAP-ENV:Header>
      <authenticate>
         <item>
            <key>authenticateResult</key>
            <value>Authenticate passed</value>
         </item>
      </authenticate>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:getChartImageResponse>
         <getChartImageResult>
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
         </getChartImageResult>
      </ns1:getChartImageResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```


### Update measurement

* Request

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:soap="https://www.grow-services.net/api/grow/soap/">
   <soapenv:Header>
      <soap:authenticate>
         <licensekey>apikey</licensekey>
         <token>apitoken</token>
      </soap:authenticate>
   </soapenv:Header>
   <soapenv:Body>
      <soap:updateMeasurement>
         <growchartid>0000021</growchartid>
         <date>20140101</date>
         <type>efw</type>
         <value>2600</value>
         <uuid>8b1f07ba-00a2-4ddd-a39b-c5fd1a65f5ba</uuid>
      </soap:updateMeasurement>
   </soapenv:Body>
</soapenv:Envelope>

```

* Response

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="https://www.grow-services.net/api/grow/soap/">
   <SOAP-ENV:Header>
      <authenticate>
         <item>
            <key>authenticateResult</key>
            <value>Authenticate passed</value>
         </item>
      </authenticate>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:updateMeasurementResponse>
         <updateMeasurementResult>
            <uuid>8b1f07ba-00a2-4ddd-a39b-c5fd1a65f5ba</uuid>
            <type>efw</type>
            <date>1388564782</date>
            <value>2600</value>
         </updateMeasurementResult>
      </ns1:updateMeasurementResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

### Remove measurement

* Request

```xml
<soapenv:Envelope xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:soap="https://www.grow-services.net/api/grow/soap/">
   <soapenv:Header>
      <soap:authenticate>
         <licensekey>apikey</licensekey>
         <token>apitoken</token>
      </soap:authenticate>
   </soapenv:Header>
   <soapenv:Body>
      <soap:removeMeasurement>
         <growchartid>0000021</growchartid>
         <measurementuuid>b2b6c76b-5ea2-448a-8520-14bb56bf23c2</measurementuuid>
      </soap:removeMeasurement>
   </soapenv:Body>
</soapenv:Envelope>

```

* Response

```xml
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/" xmlns:ns1="https://www.grow-services.net/api/grow/soap/">
   <SOAP-ENV:Header>
      <authenticate>
         <item>
            <key>authenticateResult</key>
            <value>Authenticate passed</value>
         </item>
      </authenticate>
   </SOAP-ENV:Header>
   <SOAP-ENV:Body>
      <ns1:removeMeasurementResponse>
         <removeMeasurementResult>OK</removeMeasurementResult>
      </ns1:removeMeasurementResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
