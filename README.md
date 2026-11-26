# tewhatuora.fhir.template

Template for FHIR IGs based on Te Whatu Ora branding guidelines.

## Instructions

1. Update the template line in your IG's igi.ini file to: `template = https://github.com/tewhatuora/tewhatuora.fhir.template`

### logos and customisation

Logo images are appended from the `content/includes/_apppend.fragment-header.html` file. These can be replaced as appropriate by adding an image to the `content/assets/images` directory and referenncing from the header fragment. 

Anything added to the template directory will be added/replaced to the base template using the following logic: 
* When the custom template has a file that does not exist in the base, this file from the custom template gets added to the template
* When the custom template has a file that exists in the base, the base file gets replaced by the file from the custom template
* When the custom template has a file named _append.xyz , the content of this file is added to the file named xyz in the base