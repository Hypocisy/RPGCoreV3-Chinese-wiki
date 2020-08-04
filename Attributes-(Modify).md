Directory: "./../Attributes.yml"  
Module: Attributes  

This allows you to modify pre-existing attributes on the server, setting limitations and overiding default values. Beware that this is **not** creating a new attribute, you can only modify existing attributes. Check out [[CustomAttributeModule]] if you want to create additional attributes.

# How to modify existing attributes

This covers general item configuration, equipment still may need to specify the options defined here.

| Option | Type | Description |
|-|-|-|
| minimum | decimal | fixed threshold we cannot evaluate below |
| maximum | decimal | fixed threshold we cannot evaluate above |
| minimum-id | string | attribute we cannot evaluate below |
| maximum-id | string | attribute we cannot evaluate above |
| defaults | decimal | always added to base value of attribute |
