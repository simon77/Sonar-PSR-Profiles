Having searched the web for a suitable set of rules for sonar and found nothing, I decided to write them myself.

This is a very brief guide to installing the additional rules and profiles into sonar.

I am making the following assumptions:

Sonar is installed, I used version 3.3
PHP Plugin installed into sonar, I used version 1.1
PHP_CodeSniffer is installed, I used 1.4.2
No previous additional CodeSniffer rules have been added to sonar
PSR-2 includes PSR-1 but I have split the rules and profiles in case you only want to install PSR-1.

Installing PSR1
Download the rules from here
This file must be copied in the directory $SONAR_HOME/extensions/rules/php_codesniffer_rules/. Make sure it is called rules.xml
Restart your sonar instance sudo service sonar restart
Download the PSR1 profile from here
Log into sonar and go to the Configuration Quality Profiles page
Click the “Restore Profile” button in the top right hand corner
Choose the PSR1.xml file and click restore
This should create a new profile PSR1 with 14 rules
Finally click the Set As Default link
Installing PSR2
Download the rules from here
This file must be copied in the directory $SONAR_HOME/extensions/rules/php_codesniffer_rules/. Make sure it is called rules.xml. Please note this replaces the rules.xml used for PSR1
Restart your sonar instance sudo service sonar restart
Download the PSR2 profile from here
Log into sonar and go to the Configuration Quality Profiles page
Click the “Restore Profile” button in the top right hand corner
Choose the PSR2.xml file and click restore
This should create a new profile PSR2 with 117 rules
Click on the PSR2 profile
Click the Profile Inheritance tab
Choose PSR1 as the parent profile, click update
You should now see a graphic that shows PSR2 inherits from PSR1
Finally click the Set As Default link
Once this has been completed Sonar should now be aware of the violations produced by PHP_Codesniffer using either the PSR1 or PSR2 standards.

The additional rules that I have created are based upon my interpretation of the sniffs from PHP_Codesniffer, as far as I know I have included all the possible violations but should you find any that Sonar is still unaware of please leave a comment.
