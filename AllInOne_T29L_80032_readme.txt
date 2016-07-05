[Owner Name] : Wei Ouyang
[Owner Phone] : 408-566-7547
[Owner Emergency Phone] : 510-396-8292
[Owner Email] : wouyang@cisco.com
[Site verification owner]:Tina Tang (tintnag@cisco.com ), 13429116985    Louis Lou  (louiou@cisco.com ), 15305715017   Evelyn Yao (xueyao@cisco.com ), 13588351197   Shawn Zhou(shawzhou@cisco.com), 13588768442

RELEASE NAME
==============================================
[Brief description of this release]
80032 - T29 Boeing Audio changed for CCA 

RELEASE DATE
==============================================
[Date of Release] 
DATE   : 6/8/2016

MEMO NUMBER
==============================================
80032

Features
==============================================
Aflac
TSystem
PJM
Ecommerce
Elert
AT&T
SSO
Boeing
Chylack
InsPerity
Dana
Cutter
SABA
HSBC


RELEASE
==============================================
[Release # on RMC] 
- PSO Web page release     WBXpage.T29L.PSOALLINONE-29.13.104-1280-centos6.5_64.rpm         -- (rmc.webex.com RPM File -> Component Home -> j2ee -> centos6.5_64)
                           WBXpagestatic.T29L.PSOALLINONE-29.13.104-1280-noarch.rpm         -- (rmc.webex.com RPM File -> Component Home -> j2ee -> centos6.5_64)

[Release # on CMC] : (cmc.webex.com -> My Services->Supported Services->psopage)              
CMC Service: 29.13.104.1280
Sub Service: webapp, staticpackage 
Package list:
    WBXpagestatic.T29L.PSOALLINONE
    WBXpage.T29L.PSOALLINONE

DEPENDENCIES
==============================================
[Provide specific dependency information to other releases]
- Web page release                 WBXpage.T29LSP13-29.13.104-10011-centos6.5_64.rpm
                                   WBXpagestatic.T29LSP13-29.13.104-10011-noarch.rpm
- Server/Communications Platform   Eureka 3.9 or above
- Web App Server                   Tomcat




BACKUP INSTRUCTIONS
==============================================
No.

INSTALLATION INSTRUCTION
==============================================
1. Install package on Tomcat server 
    1). Login CMC site. Navigate to My Deployments -> psopage
    2). Upgrade every j2eeapp server in the pool. Make sure to select "29.13.104.1280" on "Upgrade Service window"

2. Install Page static on DPL Server
    1) Login CMC site, Navigate to My Deployments -> j2ee
    2) Click bts or prod and then select specific pool name -> DPL server
    3) Click "Service Management" to select "Upgrade Service" in the dropdown list
    4) Select "29.13.104.1280" and Click button "Generate Configuration"
    5) Click Button "Confirm to Upgrade"



CONFIGURATION INSTRUCTION
==============================================

[Aflac]

++++++++++++++++++++++++++++++++++++++++++++++++++

1. Super Admin Configuration
   a. PSO Settings/Site Client Lockdown Type
      Check "PSO Site" option
      Set PSO Type as "PSO Custom Work"
      Set PSO Feature as "Aflac"

  
[T-Systems]

++++++++++++++++++++++++++++++++++++++++++++++++++

1. Super Admin Configuration
   a. PSO Settings/Site Client Lockdown Type
      Check "PSO Site" option
      Set PSO Type as "PSO Custom Work"
      Set PSO Feature as "T-Systems"

   b. My WebEx Configuration
      Uncheck "My Contacts" for "Standard" and "Pro"	  


[Elert]

++++++++++++++++++++++++++++++++++++++++++++++++++

1. Super Admin Configuration
   a. Supported Service Types
      Checked "Training Center" item if need "Training Center"

   b. PSO Settings/Site Client Lockdown Type
      Check "PSO Site" option
      Set PSO Type as "PSO Custom Work"
      Set PSO Feature as "Elert"

2. Branding Configuration
   a. PSO Config - Only set the following variables if they do not exist. If they do exist, don't modify them.
      Config "Query Period" to "12" Months

   b. Upload the following files in Graphics Upload in brand site, if the files were not uploaded previously. But if they do exist, don't modify them.
      Upload file "GoogleConversionTracking.txt" from rmc.webex.com Release -> Component Home -> pso ->Elert -> Document List
      NOTE: the txt name should be invariable, content should be offer by customer

 
  
[EC eCommerce]

++++++++++++++++++++++++++++++++++++++++++++++++++

1. Super Admin Configuration
  1) Supported Service Types 
     Check "Event Center"
     Check "Marketing Add-on"

  2) PSO Settings/Site Client Lockdown Type
      Check "PSO Site" option
      Set PSO Type as "PSO Custom Work"
      Set PSO Feature as "EC eCommerce Package"
 
  3) Site Administrator Setting
     Check "Allow Site Administrator to Edit Email Templates"

  4) Commerce and Reporting
     Check "Site Admin Report"
 
2. Brand Site Settings
  1) Attendee eCommerce
     If eCommerce feature is not required, select "Disable".
     If eCommerce feature is required, select "Enable without shopping cart" or "Enable with shopping cart".
     If eCommerce feature is enabled, set "Payment Gateway Settings" as following:

                   Test                               Production
     Server Name:  pilot-payflowpro.paypal.com        payflowpro.paypal.com
     Port:         443                                443
 
  2) Data Migration
     If the site is upgraded site(not new created), then need to do data migration.
     If the migration button is activated, click the "Begin" button to migrate site config params and email templates.
     After the migration is completed, "Already done" will be displayed next to the corresponding "Begin" button, the "Begin" button will be disabled.
 
  3) Email 
     If the site is new created T28L site(not upgraded) , then add an email template for "Event Center" as following:
     Email name: eCommerce ID Retrieval
     From name: %attendeeEmail%
     From email: %SenderEmailAddress%
     Reply to: %attendeeEmail%
     Subject: eCommerce ID Retrieval
     Message:  
     I do not have a member id. My company name is: %CompanyName%. Please send me my member id.

     Thank you.%attendeeEmail%   

3. Site Admin Settings
  1) Email Templates
     Edit email templates for "Registration Approved":Event Center-->Registration Approved: 
     For HTML format, add "Event Fee: %Fee%<BR>" below "Event number: %MeetingNumber%<BR>"
     For Plain Text format, add "Event Fee: %Fee%" below "Event number: %MeetingNumber%"

  2) Site Settings for "Event Center" -> Attendee eCommerce
     First open "Attendee eCommerce" page will initialize eCommerce parameters.

[PJM]

++++++++++++++++++++++++++++++++++++++++++++++++++

1. Super Admin Configuration
   a. Supported Service Types
      Checked "Training Center" item if need "Training Center"

   b. PSO Settings/Site Client Lockdown Type
      Check "PSO Site" option
      Set PSO Type as "PSO Custom Work"
      Set PSO Feature as "PJM"

[Boeing]

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
Site configure:
  Please refer to "rmc.webex.com Release -> Component Home -> pso-> Document List->BOEING ->Boeing-Configuration-WebEx-use-Memo18492.xls" file

Brand Configuration:
1) Pso Config:
  a.Add pso configuration item as following:

     ItemName                               ItemValue(example)
 ----------------------------------------------------------------------------------------------------
     psoAttemptTimes                         10                                     
    
     psoCapthaShowTime                       10          

[AT&T]

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
1.Super Admin Configuration - Site:  
   1> Supported Service Types:
      Select Meeting Center service and session types

   2> PSO Settings/ Site Client Lockdown Type: 
      a. Choose "PSO" for "Site Client Lockdown Type" item.
      b. Check "PSO Site" item. 
      c. Choose "PSO Custom Work" for "PSO Type" item.

   3> Site Administrator Setting:
      Check "Allow Site Administrator to Edit Email Templates"
   
   4> Tools and Technologies:
      Check "Support customized online help"

   5> Resource Restrictions:
      Check "Session Controlled by License Manage", and check "Participants Limit"
  
   6> API:
      Check "Enable XML Interface", and select "XML 8.8.0"

   7> Telephony Configuration:
      Check "3rd-party TSP using telephony API"    


2. SiteAdmin configuration:
   1> Site Settings:
      Uncheck "Presence Integration"
   
   2> Email Templates->Existing Email Templates for Meeting Center:
      Edit email template for "Invitation to a Meeting in Progress" as UpdateEmailTemplate.txt
	 
3.	For Document:
	1> Create documentation directories using the base releases as defined in section Dependencies.

	2> Create directory /www/htdocs/docs/T28L/custdocs/ATTSHARE if it does not exist

	3> Copy the whole directory of the folder /www/htdocs/docs/T28L to /www/htdocs/docs/T28L/custdocs/ATTSHARE
     yes|cp -rf /www/htdocs/T28L/ custdocs/ATTSHARE/

	4> Extract custdocs.tar to the folder
     tar -xvf custdocs.tar

	5> Copy the whole directory of the folder custdocs/ATTSHARE to /www/htdocs/docs/T28L/custdocs
     yes|cp -rf custdocs/ATTSHARE /www/htdocs/docs/T28L/custdocs

	6> Create symbolic link for each particular site in the ticket	
     cd /www/htdocs/docs/T28L/custdocs
     ln -s ATTSHARE [Site Name]  
   
	7> Change all patch files attributes to 755 nobody:nobody 
     cd /www/htdocs/docs/T28L
     chmod -R 755 custdocs
     chown -R nobody:nobody custdocs 

[SSO]

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 
Please refer to Configuration.txt                    --( rmc.webex.com Release -> Component Home -> pso -> Document List -> SSO)

[Clylack]

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

1. Super Admin Configuration
   1) PSO Settings/Site Client Lockdown Type
      Check "PSO Site" option
      Set PSO Type as "PSO Custom Work"
      Set PSO Feature as "Chylack"

2. Brand Configuration:(Please refer RT to set the value of following Configuration, following just an example)
 1) Pso Config:
   a.Add pso configuration item as following:

   ItemName                               ItemValue(example)
----------------------------------------------------------------------------------------------------
   CancelURL_Dialog                       https://locs.webex.com

   SupportAccessControl                   YES   

   DisplayOnlyAdminRecord                 YES

   DeleteCategoryWithSubcategory          Can not delete. Category has subcategories.   

   DeleteCategoryWithRecord               This category contains recordings. If it is deleted, all recordings will be detached from the category. Click YES if you still want to delete this category.   

   DeleteSubcategoryWithRecord            This subcategory contains recordings. If it is deleted, all existing recordings will be reassigned to the higher category level. Click YES if you still want to delete this subcategory.   

   AccessFailPrompt                       Error: The access code or email address is incorrect.   
   
   CategoryDescriptionBackground          #012456

   CategoryNameColor                      #100233

   CategoryNameSize                       24
  
   SubCategoryNameColor                   #4FFEE0

   SubCategoryNameSize                    20
 
   Note:The messages can be changed by customer's requirement. If customer has set them, please don't change them.

 2)General:
   Turn on attendee disclaimer or recording disclaimer for TC if need

3.Site Admin Configuration:
 1)PSO Configuration->Disclaimer file upload :
   Upload attendeedisclaimer.htm, recorddisclaimer.htm or recorddescription.htm file if need(Files will be provided by customer )

[Insperity]

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

1. Super Admin Configuration
   1) PSO Settings/Site Client Lockdown Type
      Check "PSO Site" option
      Set PSO Type as "PSO Custom Work"
      Set PSO Feature as "Insperity"

[Dana]

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

1. Super Admin Configuration
   <1> Supported service types
       Select "Event Center" service type.

   <2> PSO Settings/Site Client Lockdown Type
       Check "PSO Site" option
       Set PSO Type as "PSO Custom Work"
       Set PSO Feature as "Dana"

2. SiteAdmin Configuration
   <1> IP range config
       Set "Allowed IP address range"
       "Add allowed IP address range"
       Step1: Click "IP range config" in the left menu
       Step2: Add allowed IP range, for example: 10.224.181.1-10.224.181.255
       Step3: Fill in "Description" if need 
       Step4: Click "Add" button

3. SiteBrand Configuration
   <1> PSO Config
       Add PSO configuration item
       Item Name = pso_InvalidIPMessage
       Item Value = Your system's IP address client_ip is not authorized to attend this event. If you believe you received this message in error, please contact the IT Customer Care Service Desk (North America 855.857.1690) or by email at ITServiceDesk@dana.com. Prior to calling, even if connected to the internet remotely, verify your web browser is set for the appropriate Dana proxy server.
       Note: 1) The Value should be provided by customer.
             2) The "client_ip" is a dynamic param for page to get the current IP address


[Cutter]

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

1. Super Admin Configuration
  1) Supported Service Types
       Select "Event Center"
       Check "Allow Customizable Session Type" item

  2) PSO Settings/Site Client Lockdown Type
       Check "PSO Site" option
       Set PSO Type as "PSO Custom Work"
       Set PSO Feature as "Cutter"

  3) API
       Select all options


[SABA]

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

1. Super Admin Configuration
  1) Supported Service Types
       Select "Training Center"

  2) PSO Settings/Site Client Lockdown Type
       Check "PSO Site" option
       Set PSO Type as "PSO Custom Work"
       Set PSO Feature as "SABA Integration"

2. Site admin Settings
   1> Manage Site -> Site Settings
      Uncheck the "Require mixed case" under the Password management.
	  Uncheck the "User can reset password after hours " under the Password management.
	  Uncheck the "Do not allow reuse of the last passwords " under the Password management.


[HSBC]

++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++

1. Super Admin Configuration - Session Type:
   New a MC PRO session type called "PRO-HSBCHK", and make following change:
   1)Site Type:
     a. Check "Enterprise" and "Meeting Center"      

   2)Session Features
     a. Uncheck "Recording Client-Side", "Polling", "Remote printing"
     b. Select "Open" for "Chat", "Participant list"
     c. Select "Closed" for "Closed captions", "Notes", "Q & A"

2.Super Admin Configuration - Site:  
   1)Site and Session Configurations      
     a. Check "Meeting Center" and "WebACD", and check session type "PRO-HSBCHK"
	 b. Uncheck "Sales Center"  
 
   2)PSO Settings/Site Client Lockdown Type
	  Set Client Lockdown Type as "PSO"
      Check "PSO Site" option
      Set PSO Type as "PSO Custom Work"
      Set PSO Type as "HSBC"

   3)Tools and Technologies
     a. Check "Recording Network-based"
     b. Check "Enable Recording Encryption"
     c. Check "SAML SSO"
     d. Check "Allow Auto Account Creation"
     e. Uncheck "Allow to clean SSO user's password" before completing WebACD upgrade for all HSBC RMS

   4)Telephony Configuration 
     a. Select "WebEx Telephony"
     b. Check "Call-in Teleconferencing"
     c. Check "Call-back Teleconferencing", and uncheck "Enable Call Me back (for MC, $C, SC only)"
     d. Check "Integrated VoIP"
     e. Check "Enable WebEx hybrid audio"
     f. Uncheck "Other Teleconferencing" 
	 
   5)API
     a. Check "Enable WebACD APIs", and uncheck "Enforce Plug-in Signature Verification"
	 
   6)Client Platforms
     a. Uncheck Linux Client, Java Client, Mobile Web Access, iOS Client, Blackberry Client, Windows Mobile Client and Android Client 

   7)Productivity Tool
     a. Uncheck "Enable Productivity Tools"

   8)CDN Host Name
     a. Enter the correct CDN server's domain name only without protocol. 
	 
3. Brand Configuration
   1)PSO Config:  
     a. Please add the following items(Note: Following item value just an example, please refer to RT to set Item Value):
        Item Name		                  Item Value  
 --------------------------------------------------------------------------           
     psoAppletDetect                            15                           
     psoBlockLogin                              true       
     psoBlockJoinMeeting                        true
     psoTokenTimeSpan                           60  
     psoCookieCheck                             yes
     psoRMTimeout                               180
     psoCustomerTimeout                         180
     psoCustomerIDName                       customerID
 --------------------------------------------------------------------------  

     b. Please add "Login Page Content"(Note: the content is from customer)
  
   2)PSO Log:
     Select "On" 

4. Site Admin configuration:
   1)Site Settings for Common:
     a. Select "Java" for "Primary client download method"
     b. Uncheck "Presence Integration"
     c. Make 0 value for "Chat Phrase Library"
     d. Uncheck "Require login before site access"
     e. Check "Encrypt all network-based recordings"

   2)Site Settings for WebACD:
     a. Add 3 customized fields for each queue(Personal and Normal Queue): 
	    customerID, Text box, 20 characters, check the Displayed on Form and Required
		timeout, Text box, 20 characters, check the Displayed on Form and Required
		ticket, Text box, 100 characters, Only check the Displayed on Form
     b. Set "Round Robin" for each normal queque's "Request Distribution"
     e. For normal queue, set "Accept Threshold" to 100, and set "Escalation threshold" to 110

   3)HSBC Confirmation Settings:
     a. Upload HSBCPanel.xml(Note: the file is from customer)

   4)Manage Users->Add/Edit Users:
     a. For RM account:
     WebACD Preferences->"Default Session Type": "PRO-HSBCHK"


ROLLBACK INSTRUCTIONS
==============================================
Please contact project owner for details in case need to rollback.


SPECIAL SITE VERIFICATION PROCEDURE
==============================================
[Provide special site verification procedure for this patch if can't use standard procedure]
N/A   

MISCELLANEOUS
==============================================
[Provide other important information about this release]
Service down time: (minutes) No
Server program restart? Y/N No
Server machine reboot? Y/N No
Customer impact? Low



