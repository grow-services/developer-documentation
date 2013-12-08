# Introduction

## Purpose

The purpose of this document is help third-party software vendors to easily integrate GROW chart functionality into their software application. It offers technical documentation about the available APIs.

## Target audience

This document contains technical information, intended for software developers of Maternity Information Systems (MIS), primary and secondary obstetric EMRs, ultrasound applications, hospital systems, etc.

## Support Service

For any questions not covered in this document, feel free to contact us at [developer@grow-services.net](mailto:developer@grow-services.net). You can use this e-mail address for any questions you, as a software developer, may have about integrating your application with the web-service.

## Background 

Historically, the Perinatal Institute has provided tools for assessment of customised fetal growth and birth weight by defining each pregnancy's growth potential through the Gestation Related Optimal Weight (GROW) software, including

* GROW- customised antenatal charts for plotting fundal height and estimated fetal weight
* GROW-centile for calculation of customised birthweight centiles for each pregnancy, or a database of pregnancies (bulk centile calculator)

Both have been provided by a WebApp or WinApp.

However, as part of the new Growth Assessment Protocols (GAP) programme, the software options have now expanded to include a web service for local Trust's Maternity Information Systems (MIS) to link to. In addition, the software has now expanded to include data collection and reporting of rates of intrauterine growth restriction (birthweight below the tenth customised centile) and their antenatal detection rates.

The GROW API will produce the customised growth charts and birth weight centiles as part of the routine data entry for clinicians, reducing the need for double entry of data. The web service will support data collection and reporting of IUGR rates and antenatal detection rates and where required, automated plotting of fundal height and estimated fetal weight measurements. This will eliminate human error in plotting.

Phase two development will include informing the end user of abnormal plots (i.e. static, slow or accelerated growth) in order to trigger appropriate referral for further investigation.

## Versioning and further information

The latest version of this document, and further developer information is available from the following website: 

* [http://developer.grow-services.net/](http://developer.grow-services.net/)

This document itself is managed as an open source project on Github. Improvements, extensions and corrections are encouraged. We welcome forks and pull-requests on the following project url:

* [http://github.com/grow-services/developer-documentation](http://github.com/grow-services/developer-documentation)


## Legal

This documentation is (c)2013 M Account BV and licensed under the CC BY-SA 3.0 license:

* [http://creativecommons.org/licenses/by-sa/3.0/](http://creativecommons.org/licenses/by-sa/3.0/)


