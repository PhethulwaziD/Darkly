# Form_Value_Manipulation
Being able to manipulate a form field is no thing it's as simple as abc, if that's a thing. Point is this is a real vulnerability, and if not handled properly it can cause some serious damage.

## Example
For example, in <a href="http://192.168.43.251/index.php?page=survey">survey</a> we're given a table where we can rate Thor, and who ever; I forgot the names. This is done through a form so in we inspect the element for rating we can see the value respresenting the an option in the form. Like I said form manipulation is no thing, and that is what we need to do in this section. If we manipulate the value of an option to an obsurd value(it has to be really obsurd) like 1000000000000000000(point is I can go on 0000000). In submitting this form value on selection we can retrieve our flag.
<img src="https://github.com/PhethulwaziD/Darkly/blob/master/Form_Value_Manipulation/Resources/form.png" />

## Retrieved Flag
* flag: 03a944b434d5baff05f46c4bede5792551a2595574bcafc9a6e25f67c382ccaa

## Remedy
* I hate to say this but it's something we cannot control, atleast from the client side. On the other hand, sanitizing every input we can get, we can make sure that whateber data we get is what we want.

## Resources
* https://totaluptime.com/form-field-manipulation/
* https://owasp.org/www-community/attacks/Web_Parameter_Tampering