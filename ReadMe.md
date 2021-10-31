KUL Public Schedule To ICS
============================

A tool to dump a KU Leuven public course schedule to an .ics file.
This file can be imported in a calendar and is widely supported by
various applications and services.

## Motivation
PhD students have no way to sync/import the schedule of their teaching
assignments into a calendar. To avoid laborious and error-prone
copying by hand, this script can generate and `.ics` file.


## How to use
There is no command line at the time. The URL and destination file
name can be changed by editing the constants in the code to this
purpose.

To find the url, go to [KU Leuven onderwijsaanbod](https://www.onderwijsaanbod.kuleuven.be/2021/opleidingen/e/index.htm),
and find your course. Then, click on the clock-symbol to open it
schedule. The schedule opens in a separate window. Set the schedule to
*semester view*, and copy the URL from the address bar of your
browser.

**NOTE**: As this tool is still experimental, I recommend to import
the .ics file in new, bland calendar to see if everything is fine.
This way, your calendar does not risk to mess up.

**NOTE 2**: This URL is only temporarily valid. But still amply long
for you to run this script.

### Required packages
This script relies on other packages which you can get via pip. To
install these packages, run:
```shell
pip instal -r requirements.txt
```

Preferably do this in a `virtualenv`.

The requirements file was generated by running `pip freeze >
requirements.txt`

## How it works
This script scrapes the public SAP schedule which is accessible through
'onderwijsaanbod'. It uses the 

As this scrapes ugly SAP-generated HTML, this code is very prone to
any changes to schedule page. A **little changes in the page's HTML** will
most likely completely **break this tool**.

## Ideas and possible improvements

* add command-line arguments instead of constants in code
* better packaging so it's really a distributable tool
* The link acquired as described above is only temporary. Instead, using the ID 
  of the course in the pre\_laden.htm page (<http://www.kuleuven.be/sapredir/uurrooster/pre_laden.htm?OBJID=50448161&OTYPE=L&TAAL=E&SEL_JAAR=2018>)
  and then sending the correct POST-request to get to the semester-view page
  would be much more robust approach
* an extension / different script to periodically dump the ics, compare it with
  the previous version and notify the user of any schedule changes.



