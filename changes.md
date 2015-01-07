# API Changelog

This living document will be updated with changes to the service that may be relevant and/or interesting for developers that support the API in their application or intend to do so. 

We hope this document will help to better keep you informed.

## Change process

Rest assured that no unannounced breaking changes will be made to endpoints of which we know they are currently in **production** use.

Breaking changes will only be introduced through new API endpoints through a versioning system. As long as the application uses the ‘old’ end-point, no changes are required. To support a new end-point, the application will need to change the end-point urls, and test / update the application before releasing it to their end-users.

We may introduce non-breaking changes such as new end-points or extended functionality. These changes should always be fully backwards compatible. Occasionally we may introduce breaking changes to APIs that are not in production usage, in collaboration with the implementing parties. If such a change is needed, we will clearly communicate this to all implementing parties.

Any updates to this document will be sent out to everybody that has applied for a developer key.

If you have any questions about our change-process, please don’t hesitate to contact us at developer@grow-services.net

## Changes by date

### 01/12/2014 The API v3 online (improvement)

With the release of v3 of the API, the base url has been changed from https://www.grow-services.net/api/grow/ to https://www.grow-services.net/api/grow/v3/. This new version improves the speed to store the data and will reduce the request times. Also a new way to register a pregnancy has been added. You can now register more pregnancies at once using registerPregnancies. The response can get all information of this pregnancy. Please look at this example for more detail:
[Example][1]
The new API is backwards compatible with the previous version.

### 15/08/2014 SOAP/v1 (improvement)

As a further improvement on the last SOAP/v1 change, we’re now explicitly defining the complex types instead of the `soap-enc:Array`. This allows code class generators to understand the WSDL even better.

### 13/08/2014 SOAP/v1 (improvement)

The WSDL has been updated replace several `xsd:struct` types with `soap-enc:Array`. This allows the WSDL to pass validation in XML Spy.

### 08/08/2014 All/v1 (improvement)

All end-points now have methods to `update` or `remove` previously registered measurements. 

This requires the calling application to keep track of measurement id’s internally. 
As a simpler integration, it is still possible to just clear all data, and re-register all measurements before generating a chart.


[1]: https://github.com/grow-services/developer-documentation/blob/master/src/examples-xml.md#register-pregnancies-new-api-for-registering-more-pregnancies-at-once  "Register pregnancies example"
