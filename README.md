# tewhatuora.fhir.template

Template for FHIR IGs based on Te Whatu Ora branding guidelines.

## Instructions

1. Copy the contents of this repo into a directory called `tewhatuora` in the top level of your IG's source.
2. Update igi.ini to point the new template by changing the template line to: `template = tewhatuora`

### logos and customisation

Logo images are appended from the `content/includes/_apppend.fragment-header.html` file. These can be replaced as appropriate by adding an image to the `content/assets/images` directory and referenncing from the header fragment. 

Anything added to the template directory will be added/replaced to the base template using the following logic: 
* When the custom template has a file that does not exist in the base, this file from the custom template gets added to the template
* When the custom template has a file that exists in the base, the base file gets replaced by the file from the custom template
* When the custom template has a file named _append.xyz , the content of this file is added to the file named xyz in the base

## OpenAPI Viewer
When this template is used to publish an IG using the `https://fhir-ig.health.digital.nz` publishing infrastructure, an OpenAPI UI can be included as a page in the IG. The requirements to enable this behaviour are
- use this template
- provide a valid OpenAPI specification, as part of the website at `/openapi.yaml`
- provide a page in the IG that includes a div with an id of `swagger-ui`

e.g. `input/pagecontent/openapi.xml`
```xml
<div xmlns="http://www.w3.org/1999/xhtml" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">
    <div id="swagger-ui"></div>
</div>
```

## To do

Currently the template isn't in https://registry.fhir.org FHIR package registry, so you need to include it and reference it by the filepath (the directory tewhatuora in your IG). Once added to the registry it will be possible to reference by id and the IG publisher will load it for you you (using `template = tewhatuora.fhir.template`)