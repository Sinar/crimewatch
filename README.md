CrimeWatch
==========

Crime reporting and vizualisation project for Malaysia

![Crime Mural JB](images/zacharevic-jb-mural.jpg "Ernest Zacharevic Crime Mural JB")

Overall Goals
=============

 - Crowdsource tracking of crime reports in Malaysia
 - Live visualizations of crime as they are reported
 - Visualizations to show heat maps of different types of crimes by location
 - Robust system that could be used by all, including different systems to aggregate/correlate

Background
==========

Malaysian government has stopped providing crime statistics to the United Nations. They have also refused
to share raw statistics of reported crimes, even in Parliament. [1] The public has no information of crime
hotspots. Official statistics of reduction in crime does not match increasing prevalance of people
affected by crime on a daily basis or police advisories that mark even residential suburbs as dangerous
areas targeted for crime.

Use cases
=========

 - Public - To share crime affecting them, to warn others and to help in sharing information for investigations
 - Public - Would like to know where crime is happening as it happens.
 - Public - Would like to know what kind of crimes are happening in specific areas and at what times
 - Public - Neighourhood watche would like to know what sort of crimes they have to look out for
 - Police - Detectives would want to search for information and patterns to solve caes
 - Police - Will be able to see heatmaps of problematic areas to assign more resources
 - Police - Will be able to justify lack of resources if crime escalating in an area
 - Local Councils - Would like to see crime hotpots, to see what improvements could be done (eg. better lighting)
 - Journalists - Additional information for stories
 - Researchers - Be able to get access to raw data for detailed analysis

Existing implementations and reports for reference
==================================================

Systems:

So far almost all systems worldwide rely on open data, which is one of
the problems identified here in Malaysia.

 - SJA1ert http://www.sjalert.com.my has co-ordination with police who share reports, and co-operation
   with citizens and local representatives. Looks somewhat inactive, but updated. Email sent for co-operation (Khairil)

 - Hatari, Kenya http://www.hatari.co.ke/ (Ushaidi)
   Limited reports, reports do not look helpful. Example of problem with crowd source data.
 - Crimereports https://www.crimereports.com (propietary, relies on official police open
   data)
 - Tyler Sirens http://www.joeycoleman.ca/2012/03/14/tyler-sirens-a-real-time-open-source-crime-map-coming-to-hamilton
 - crimespotting http://oakland.crimespotting.org 
   Also uses official police public data, but the UI has interesting time based info,
   such as light, dark, nightlife, commute and swing shift which should be emulated.

Data:

- FBI Uniform Crime Reports http://www.fbi.gov/about-us/cjis/ucr/ucr
- Street level crime  http://data.gov.uk/dataset/england-national-crime-mapping


Technical Design
================

Milestone 1 - Capture requirements as best as possible

The initial milestone for this project is design a good set of fields an
and forms storing reports that can be used to effectively solve key uses
cases.

Some examples of fields it would have:

 - Fields from Repot Polis (official Police report)
 - Detailed geolocation if possible
   - Sinar Project has a mapit server to map locations to Malaysian political boundaries.
   - Google does not at this time have limits for non-profit usage
 - For public update/info follow up reports and workflow see leading systems above.

Milestone 2 - Initial Test Demo

 - Initial backend system for form storage, API and web based client.
 - Basic visulizations of reports on maps and some example statistics
 - Ease of use for developers should be a focus, the demo client should be well documented.
   - Other developers are more likely able to create better end user applications, while this
     project focuses on providing API and data for them to build on. (Think Google Maps API, but for crime data)
 - TODO

Milestone 3 - Public pilot

 - Web client with mobile support
 - Mobile/Tablet app (Android or IOS depending on dev availability)
 - Better improvements to key visualizations that are most useful for key use cases.
 - TODO

Issues
======

Privacy and Security
--------------------

Checking what sort of data is release by US/UK to be able to generate Crimereports etc. could be used as
reference for best practice of minimal needed for good reports.

 - Police reports have names and addresses. This poses a privacy (and security risk) to reporters. 
   - Keeping this data may help some, but cause problems.
   - Probably best to keep police report numbers other id without private data, and let police
     systems if any interact with it to complete the picture. 
 - False info may cause wrong people to get in trouble. Since this is public, it could result in vigilante issues.
 - TODO

Verification Accuracy
----------------------

The key problem with crowdsourcing information is accuracy. We need steps to ensure accuracy
while keeping the system transparent and easy to contribute to. 

Possible solutions (can be combinations)

 - Police report reference field
   - Only police can verify
 - Ability to scan and upload police reports as attachments
   - con - can be faked (the police report format has no security markers like holograms or cash notes)
 - Point system attaches weight on additional conditions to help verification
   - examples include pictures, press reports, etc.
 - Ratings of users by other users
 - Rating of user due to additional verification process eg. scanned IC, credit card, job (Police) etc.
 - Mark as Abuse/Spam reports

Each of these have problems, we have to deal with spammers, or cybertroopers etc. 



[1]: http://www.nytimes.com/2013/10/20/world/asia/soaring-crime-rate-takes-a-growing-malaysia-by-surprise.html
