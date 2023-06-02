![](./images/media/image1.jpeg){width="6.692913385826771in"
height="3.374015748031496in"}

PUBLIC

Data Formatter for Concur Request

V3.1

This file has been created to assist TMCs with documenting proposals
back to a GDS Container PNR as part of the Agency Proposal Powered by
Compleat flow.

This file will ensure accuracy when entering the remark lines into the
GDS Container PNR and help provide all the mandatory elements to Travel
Request.

Table of ContentS

CONFIGURATION [3](#configuration)

[generate gds code Section
[4](#generate-gds-code-section)](#generate-gds-code-section)

[GENERAL Section [5](#general-section)](#general-section)

[General section completion flow
[5](#general-section-completion-flow)](#general-section-completion-flow)

[General Section screenshot example
[5](#general-section-screenshot-example)](#general-section-screenshot-example)

[General Section table of definitions
[6](#general-section-table-of-definitions)](#general-section-table-of-definitions)

[General Section mandatory information
[6](#general-section-mandatory-information)](#general-section-mandatory-information)

[General Section optional information
[7](#general-section-optional-information)](#general-section-optional-information)

[AIR TAB [8](#air-tab)](#air-tab)

[Air Tab completion flow
[8](#air-tab-completion-flow)](#air-tab-completion-flow)

[Air Tab screenshot example
[8](#air-tab-screenshot-example)](#air-tab-screenshot-example)

[Air Tab table of definitions
[9](#air-tab-table-of-definitions)](#air-tab-table-of-definitions)

[Air Tab mandatory information
[9](#air-tab-mandatory-information)](#air-tab-mandatory-information)

[Air Tab optional information
[10](#air-tab-optional-information)](#air-tab-optional-information)

[CAR TAB [11](#car-tab)](#car-tab)

[Car Tab completion flow
[11](#car-tab-completion-flow)](#car-tab-completion-flow)

[Car Tab screenshot example
[11](#car-tab-screenshot-example)](#car-tab-screenshot-example)

[Car Tab table of definitions
[12](#car-tab-table-of-definitions)](#car-tab-table-of-definitions)

[Car Tab mandatory information
[12](#car-tab-table-of-definitions)](#car-tab-table-of-definitions)

[Car Tab optional information
[13](#car-tab-optional-information)](#car-tab-optional-information)

[HOTEL TAB [15](#hotel-tab)](#hotel-tab)

[Hotel Tab completion flow
[15](#hotel-tab-completion-flow)](#hotel-tab-completion-flow)

[Hotel Tab screenshot example [15](#hotel-tab-1)](#hotel-tab-1)

[Hotel Tab table of definitions
[16](#hotel-tab-table-of-definitions)](#hotel-tab-table-of-definitions)

[Hotel Tab mandatory information
[16](#hotel-tab-mandatory-information)](#hotel-tab-mandatory-information)

[Hotel Tab optional information [17](#_Toc94552504)](#_Toc94552504)

[RAIL TAB [18](#rail-tab)](#rail-tab)

[Rail Tab completion flow for one-way rail
[18](#rail-tab-completion-flow-for-one-way-rail)](#rail-tab-completion-flow-for-one-way-rail)

[Rail Tab one-way screenshot example
[18](#rail-tab-one-way-screenshot-example)](#rail-tab-one-way-screenshot-example)

[Rail Tab one-way table of definitions
[19](#rail-tab-one-way-table-of-definitions)](#rail-tab-one-way-table-of-definitions)

[Rail Tab one-way mandatory information
[19](#rail-tab-one-way-mandatory-information)](#rail-tab-one-way-mandatory-information)

[Rail Tab one-way optional information
[20](#rail-tab-one-way-optional-information)](#rail-tab-one-way-optional-information)

[SEGMENT COUNTERS: [21](#section-11)](#section-11)

[CONCATENATION [21](#concatenation)](#concatenation)

[REMARK SEPARATORS [22](#remark-separators)](#remark-separators)

[VERSION HISTORY [23](#version-history)](#version-history)

# 

# CONFIGURATION

The "Data Formatter for Concur Request" file has been programmed to
perform a concatenation of the remarks generated to allow for more than
one remark line to be copied at a time.

**The remarks order must be respected in order to have a successful PNR
transmission to Request.**

The configuration for the concatenation varies depending on the tool
used to interact with the GDS and the GDS itself. We have therefore
allowed for updates to the concatenation character and the number of
instances in the output block.

For more information on concatenation use and output examples, please
see the [Concatenation](#section-11) section below.

Prior to implementation, please determine the correct character and
instances for your tool and GDS.

To edit the character and instances:

-   Save the file

-   Right click the file, and "open with" any document editor.

You will see the following at the beginning of the document:

/\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\* Concatenation Variables
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*/

// Concatenation Characters for each gds

concatStringApollo = \"+\"

concatStringAmadeus = \";\"

concatStringGalileo = \"+\"

concatStringSabre = \"&\"

concatStringWorldspan = \"#\"

// Number of Concatenations for each Gds

lineLimitApollo = 8

lineLimitAmadeus = 8

lineLimitGalileo = 28

lineLimitSabre = 79

lineLimitWorldspan = 80

/\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\* Declaring GDS Array
\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*/

const constGDS =
\[\'Apollo\',\'Amadeus\',\'Galileo\',\'Sabre\',\'Worldspan\'\];

const defaultGDS =\"Sabre\";

const constSegCount = 99;

-   To update the character, amend the concatString value inside \" \"

-   To amend the number of concatenation instances, amend the lineLimit
    value after =\[space\]

-   To amend the Default GDS amend the defaultGDS value after =\[space\]
    with one of GDS values provided in the constGDS array

-   To amend the maximum segments that can be created amend the
    constSegCount value after =\[space\] with a number

-   Save the changes

-   Test the output against your GDS interaction tool, ensuring that the
    maximum value of instances is achieved

# generate gds code Section

This section is used to Generate GDS code for all the segments including
General Remarks.

# 

# 

# ![](./images/media/image3.png){width="6.7000360892388455in" height="3.3391338582677164in"}

# 

This step must be performed after Adding All the segments. This section
generates PNR command for all the segments including General Remarks.

# 

# 

# GENERAL Section 

This section is used to add mandatory information remarks to the GDS
Container PNR.

N.B. This document uses Apollo remark examples only.

## General section completion flow

## General Section screenshot example

![](./images/media/image4.png){width="6.69375in"
height="2.752083333333333in"}

This step must be performed for each proposal before adding the related
segment remark data into the PNR.

## General Section table of definitions

### General Section mandatory information

+-----------------------------------+--------------+-------------------+
| File input                        | PNR Remark   | PNR Remark        |
|                                   | label        | example           |
| and description                   |              |                   |
+===================================+==============+===================+
| \(1\) Locator                     | LOC-         | LOC-2NCMIA        |
|                                   |              |                   |
| This is the record locator of the |              |                   |
| container PNR that the customer   |              |                   |
| will use in any communication.    |              |                   |
|                                   |              |                   |
| It can be either the GDS          |              |                   |
| Container PNR locator or the      |              |                   |
| locator of an additional booking. |              |                   |
+-----------------------------------+--------------+-------------------+
| \(2\) Select a GDS                | Drop down    | @:5P/APTR...      |
|                                   | choice on    |                   |
| This is where you choose the GDS  | file         |                   |
| (in our example Apollo) needed to |              |                   |
| generate the Container PNR.       |              |                   |
+-----------------------------------+--------------+-------------------+
| \(3\) Select a Proposal Number    | PROP1        | @:5P/             |
|                                   |              | APTR/54/PROP1/... |
| This is where you select the      |              |                   |
| proposal number (3 is the         |              |                   |
| maximum).                         |              |                   |
|                                   |              |                   |
| Each proposal must be entered in  |              |                   |
| turn. After each is completed     |              |                   |
| (and copied and pasted) the data  |              |                   |
| for the next proposal can be      |              |                   |
| updated.                          |              |                   |
+-----------------------------------+--------------+-------------------+
| \(4\) General                     | GEN          | @:5P/APTR         |
|                                   |              | /54/PROP1/GEN/... |
| This tab is used to fill in the   |              |                   |
| general information that is       |              |                   |
| needed for the GDS Container PNR. |              |                   |
+-----------------------------------+--------------+-------------------+

### 

***\
***

### General Section optional information

+--------------------------------------+-------------+-----------------+
| File input                           | PNR Remark  | PNR Remark      |
|                                      | label       | example         |
| and description                      |             |                 |
|                                      |             | with default    |
|                                      |             | values          |
+======================================+=============+=================+
| Proposal Expiry Date                 | LIMIT-      | L               |
|                                      |             | IMIT-2023-03-31 |
| This is the expiry date and time of  | T-          |                 |
| the proposal.                        |             | T102500.000     |
|                                      |             |                 |
| -   Date is in the format            |             | (shows as       |
|     DD/MMM/YYYY                      |             | LIMIT-/ if      |
|                                      |             | blank)          |
| -   Time is in the format HHMM and   |             |                 |
|     is 24 hours                      |             |                 |
+--------------------------------------+-------------+-----------------+
| Agency Branch Offset to GMT/UTC      | ZPLUS       | ZPLUS0000       |
|                                      |             |                 |
| This is the agency branch time zone. |             | (not shown if   |
|                                      |             | blank)          |
| This works in conjunction with the   |             |                 |
| Proposal Expiry so that the correct  |             |                 |
| time can be applied adjusting any    |             |                 |
| offset.                              |             |                 |
|                                      |             |                 |
| Select if the Offset is MINUS or     |             |                 |
| PLUS GMT/UTC                         |             |                 |
|                                      |             |                 |
| -   Date is in the format            |             |                 |
|     DD/MMM/YYYY                      |             |                 |
|                                      |             |                 |
| -   Time is in the format HHMM and   |             |                 |
|     is 24 hours                      |             |                 |
+--------------------------------------+-------------+-----------------+
| Remarks                              | RMKS-       | RMKS-GENERAL    |
|                                      |             | TAB COMMENTS    |
| This is a free text field for any    |             | FREE TEXT       |
| additional information.              |             |                 |
|                                      |             | (shows as       |
|                                      |             | RMKS-/ if       |
|                                      |             | blank)          |
+--------------------------------------+-------------+-----------------+
| Booked                               | BKD-        | BKD-FALSE       |
|                                      |             |                 |
| Select this option if you have       |             | (default value) |
| pre-booked a proposal for policy     |             |                 |
| compliance reasons. This will be     |             |                 |
| shown to the traveller in the next   |             |                 |
| version of Agency Proposal user      |             |                 |
| interface v2.                        |             |                 |
|                                      |             |                 |
| The default is unchecked             |             |                 |
+--------------------------------------+-------------+-----------------+

## AIR TAB

This is where you complete the details for a single or return or
multi-Air segment.

This will be the landing page when the file is opened.

### Air Tab completion flow

### 

### 

### 

### Air Tab screenshot example

![](./images/media/image5.png){width="6.69375in"
height="3.097916666666667in"}

N.B. The summary of each segment will be displayed as a row under the
"Total Air Segments". The segment counter will be incremented once each
segment is added

## Air Tab table of definitions 

### Air Tab mandatory information

+-----------------------------------+-------------+-------------------+
| File input                        | PNR Remark  | PNR Remark        |
|                                   | label       | example           |
| and description                   |             |                   |
+===================================+=============+===================+
| AIR -- One Way                    | SEG-        | SEG-AIR1          |
|                                   |             |                   |
| This is the Air segment tab to    |             |                   |
| fill in the information for       |             |                   |
+-----------------------------------+-------------+-------------------+
| \(1\) Total Air Fare For All      | VAL-        | VAL-215.00        |
| Segments                          |             |                   |
|                                   |             |                   |
| This is the total amount for all  |             |                   |
| the Air segments added in the Air |             |                   |
| Tab.                              |             |                   |
|                                   |             |                   |
| It will automatically format to 2 |             |                   |
| decimal places if not typed.      |             |                   |
|                                   |             |                   |
| We currently only support         |             |                   |
| decimalized currencies            |             |                   |
+-----------------------------------+-------------+-------------------+
| \(2\) Departure IATA              | SIATA       | SIATA-LHR         |
|                                   |             |                   |
| This is the three-letter IATA     |             |                   |
| airport code for the departure.   |             |                   |
+-----------------------------------+-------------+-------------------+
| \(3\) Arrival IATA                | EIATA       | EIATA-CDG         |
|                                   |             |                   |
| This is the three-letter IATA     |             |                   |
| airport code for the arrival.     |             |                   |
+-----------------------------------+-------------+-------------------+
| \(4\) Flight Number               | FN-         | FN-BA258          |
|                                   |             |                   |
| This is the flight number and     |             |                   |
| should be:                        |             |                   |
|                                   |             |                   |
| the airline two-letter IATA code  |             |                   |
| followed by the flight number     |             |                   |
+-----------------------------------+-------------+-------------------+
| \(5\) Confirmation Number         | CONF-       | CONF-ABCDEF       |
|                                   |             |                   |
| This is where you will add the    |             | CONF-NA           |
| provider reference if you have    |             |                   |
| selected "Booked".                |             | (default value if |
|                                   |             | blank)            |
| This is only mandatory when       |             |                   |
| Booked is checked                 |             |                   |
+-----------------------------------+-------------+-------------------+
| \(6\) Departure Date and Time     | S           | SDTE-2            |
|                                   | DTE-.../AT- | 021-09-07/AT-0920 |
| \(7\) Arrival Date and Time       |             |                   |
|                                   | E           | EDTE-2            |
| This should be entered using the  | DTE-.../AT- | 021-09-07/AT-1130 |
| following format:                 |             |                   |
|                                   |             |                   |
| -   Date is in the format         |             |                   |
|     DD/MMM/YYYY                   |             |                   |
|                                   |             |                   |
| -   Time is in the format HHMM    |             |                   |
|     and is 24 hours               |             |                   |
+-----------------------------------+-------------+-------------------+
| \(8\) Airline Class               | C-          | C-ECONOMY         |
|                                   |             |                   |
| This is the cabin class           |             |                   |
| description in full.              |             |                   |
+-----------------------------------+-------------+-------------------+

### Air Tab optional information

+-------------------------------------+------------+-------------------+
| File input                          | PNR Remark | PNR Remark        |
|                                     | label      | example           |
| and description                     |            |                   |
+=====================================+============+===================+
| Booked                              | BKD-       | BKD-TRUE          |
|                                     |            |                   |
| Select this if the flight is booked |            | or                |
| (eg low-cost carrier).              |            |                   |
|                                     |            | BKD-FALSE         |
|                                     |            |                   |
|                                     |            | (default value)   |
+-------------------------------------+------------+-------------------+
| Confirmation Number                 | CONF-      | CONF-ABCDEF       |
|                                     |            |                   |
| This is where you will add the      |            | CONF-NA           |
| provider reference if applicable.   |            |                   |
|                                     |            | (default value if |
| This is optional when "Booked" is   |            | blank)            |
| not selected.                       |            |                   |
+-------------------------------------+------------+-------------------+
| Flight Duration                     | DUR-       | DUR-150           |
|                                     |            |                   |
| This is the flight duration         |            | (shows as DUR-/   |
| information in minutes.             |            | if blank)         |
+-------------------------------------+------------+-------------------+
| Departure Terminal                  | TD-        | TD-NORTH          |
|                                     |            |                   |
| This is where you add the departure |            | (not shown if     |
| terminal information.               |            | blank)            |
+-------------------------------------+------------+-------------------+
| Arrival Terminal                    | TA-        | TA-SOUTH          |
|                                     |            |                   |
| This is where you add the arrival   |            | (not shown if     |
| terminal information.               |            | blank)            |
+-------------------------------------+------------+-------------------+
| Segment Policy Complaint            | CMPL-      | CMPL-TRUE         |
|                                     |            |                   |
| This will be a Boolean value True   |            | (not shown if not |
| or False                            |            | selected)         |
+-------------------------------------+------------+-------------------+
| Comments                            | RMKS-      | RMKS-AIR COMMENTS |
|                                     |            | TEST              |
| This is where any additional        |            |                   |
| comments related to the air segment |            | (not shown if     |
| can be added.                       |            | blank)            |
|                                     |            |                   |
| For example, the fare conditions or |            |                   |
| any information that you want to    |            |                   |
| pass to the traveller. It is free   |            |                   |
| text.                               |            |                   |
+-------------------------------------+------------+-------------------+
| Seat Number                         | SEAT-      | SEAT-2C           |
|                                     |            |                   |
| This is where you add the seat      |            | (not shown if     |
| number. It is free text.            |            | blank)            |
+-------------------------------------+------------+-------------------+
| Equipment                           | EQP-       | EQP-757           |
|                                     |            |                   |
| This is where you add the equipment |            | (not shown if     |
| information if available.           |            | blank)            |
+-------------------------------------+------------+-------------------+

## CAR TAB

This is where all the details regarding the information for a Car
segment should be added.

## Car Tab completion flow

## Car Tab screenshot example

![](./images/media/image6.png){width="6.69375in"
height="2.8305555555555557in"}

N.B. The summary of each segment will be displayed as a row under the
"Total Car Segments". The segment counter will be incremented once each
segment is added

## Car Tab table of definitions 

## Car Tab mandatory information

+----------------------------------+-------------+--------------------+
| File input                       | PNR Remark  | PNR Remark         |
|                                  | label       | examples           |
| and description                  |             |                    |
+==================================+=============+====================+
| CAR                              | SEG-        | SEG-CAR            |
|                                  |             |                    |
| This is the tab and the segment  |             |                    |
| type.                            |             |                    |
+----------------------------------+-------------+--------------------+
| \(1\) Pickup Country Code        | SCO-        | SCO-FR             |
|                                  |             |                    |
| This is the pickup two-letter    |             |                    |
| IATA country code.               |             |                    |
+----------------------------------+-------------+--------------------+
| \(2\) Pickup City                | SCITY-      | SCITY-PARIS        |
|                                  |             |                    |
| This is the pickup city name in  |             |                    |
| full.                            |             |                    |
+----------------------------------+-------------+--------------------+
| \(3\) Pickup Location Code       | SCODE-      | SCODE-FRPLD        |
|                                  |             |                    |
| This is the UN Location Code     |             |                    |
+----------------------------------+-------------+--------------------+
| \(4\) Pickup Details             | SNOTE-      | SNOTE-RAIL STATION |
|                                  |             |                    |
| This is where you enter the      |             |                    |
| details about the pickup.        |             |                    |
+----------------------------------+-------------+--------------------+
| \(5\) Confirmation Number        | CONF-       | CONF-ABCDEF        |
|                                  |             |                    |
| This is where you will add the   |             | CONF-NA            |
| provider reference if you have   |             |                    |
| selected "Booked".               |             | (default value if  |
|                                  |             | blank)             |
| This is only mandatory when      |             |                    |
| "Booked" is checked              |             |                    |
+----------------------------------+-------------+--------------------+
| \(6\) Pickup IATA                | SIATA-      | SIATA-PAR          |
|                                  |             |                    |
| This is the three-letter city    |             | (not shown if      |
| code of the pickup city.         |             | blank)             |
+----------------------------------+-------------+--------------------+
| \(7\) Drop Off Country Code      | ECO-        | ECO-FR             |
|                                  |             |                    |
| This is the drop off two-letter  |             |                    |
| IATA country code.               |             |                    |
+----------------------------------+-------------+--------------------+
| \(8\) Drop Off City              | ECITY-      | ECITY-LYON         |
|                                  |             |                    |
| This is the drop off city name   |             |                    |
| in full.                         |             |                    |
+----------------------------------+-------------+--------------------+
| \(9\) Drop Off Location Code     | ECODE-      | ECODE-FRLYS        |
|                                  |             |                    |
| This is the UN Location Code     |             |                    |
+----------------------------------+-------------+--------------------+
| \(10\) Drop Off Details          | ENOTE-      | ENOTE-AT HILTON    |
|                                  |             | RECEPTION          |
| This is where you can add any    |             |                    |
| information regarding the drop   |             |                    |
| off.                             |             |                    |
+----------------------------------+-------------+--------------------+
| \(11\) Supplier Name             | SUP-        | SUP-AVIS           |
|                                  |             |                    |
| This is the supplier name in     |             |                    |
| full.                            |             |                    |
+----------------------------------+-------------+--------------------+
| \(12\) Drop Off IATA             | EIATA-      | EIATA-LYS          |
|                                  |             |                    |
| This is the three-letter city    |             | (not shown if      |
| code of the drop off city.       |             | blank)             |
+----------------------------------+-------------+--------------------+
| \(13\) Pickup Date and Time      | SDTE        | SDTE-              |
|                                  | -.../AT-... | 2023-11-17/AT-1200 |
| This is the pickup date and time |             |                    |
| using the following format:      |             |                    |
|                                  |             |                    |
| -   Date is in the format        |             |                    |
|     DD/MMM/YYYY                  |             |                    |
|                                  |             |                    |
| -   Time is in the format HHMM   |             |                    |
|     and is 24 hours              |             |                    |
+----------------------------------+-------------+--------------------+
| \(14\) Drop Off Date and Time    | EDTE        | EDTE-              |
|                                  | -.../AT-... | 2023-11-17/AT-1430 |
| This is the drop off date and    |             |                    |
| time using the following format: |             |                    |
|                                  |             |                    |
| -   Date is in the format        |             |                    |
|     DD/MMM/YYYY                  |             |                    |
|                                  |             |                    |
| -   Time is in the format HHMM   |             |                    |
|     and is 24 hours              |             |                    |
+----------------------------------+-------------+--------------------+
| \(15\) Rate                      | VAL-        | VAL-150.00         |
|                                  |             |                    |
| This is the total amount of the  |             |                    |
| Car segment.                     |             |                    |
|                                  |             |                    |
| It will automatically format to  |             |                    |
| 2 decimal places if not typed.   |             |                    |
|                                  |             |                    |
| We currently only support        |             |                    |
| decimalized currencies.          |             |                    |
+----------------------------------+-------------+--------------------+

### Car Tab optional information

+--------------------------------+-------------+-----------------------+
| File input                     | PNR Remark  | PNR Remark examples   |
|                                | label       |                       |
| and description                |             | with default values   |
+================================+=============+=======================+
| Booked                         | BKD-        | BKD-TRUE              |
|                                |             |                       |
| If you have booked the car and |             | or                    |
| selected this field, the       |             |                       |
| "Confirmation Number" will     |             | BKD-FALSE             |
| become mandatory.              |             |                       |
|                                |             | (default value)       |
+--------------------------------+-------------+-----------------------+
| Confirmation Number            | CONF-       | CONF-14545            |
|                                |             |                       |
| This is where you enter the    |             | or                    |
| booking reference obtained     |             |                       |
| from the provider if           |             | CONF-NA               |
| applicable.                    |             |                       |
|                                |             | (default value)       |
| This is optional when "Booked" |             |                       |
| is not selected.               |             |                       |
+--------------------------------+-------------+-----------------------+
| Class                          | C-          | C-COMPACT             |
|                                |             |                       |
| This is where you add the car  |             | (not shown if blank)  |
| category in full.              |             |                       |
+--------------------------------+-------------+-----------------------+
| Segment Policy Compliant (True | CMPL-       | CMPL-True             |
| or False)                      |             |                       |
|                                |             | (not shown if blank)  |
| This will be a Boolean value   |             |                       |
| True or False                  |             |                       |
+--------------------------------+-------------+-----------------------+
| Comments                       | RMKS-       | RMKS-CAR COMMENT      |
|                                |             | EXAMPLE               |
| This is where you can add any  |             |                       |
| free text additional           |             | (not shown if blank)  |
| information regarding the car  |             |                       |
| segment.                       |             |                       |
+--------------------------------+-------------+-----------------------+
| Transmission Preference        | TRAN-       | TRAN-A                |
|                                |             |                       |
| This is where you choose the   |             | (default value)       |
| car transmission in the        |             |                       |
| drop-down menu.                |             |                       |
+--------------------------------+-------------+-----------------------+
| Pickup Phone                   | PUPH-       | PUPH-1233333333       |
|                                |             |                       |
| Here you can enter the pickup  |             | (not shown if blank)  |
| office phone number.           |             |                       |
+--------------------------------+-------------+-----------------------+
| Drop Off Phone                 | DOPH-       | DOPH-415747777        |
|                                |             |                       |
| Here you can enter the drop    |             | (not shown if blank)  |
| off office phone number.       |             |                       |
+--------------------------------+-------------+-----------------------+
| Additional Equipment           | EQP-        | EQP-SAT NAV           |
|                                |             |                       |
| This is where you can add any  |             | (not shown if blank)  |
| car feature/equipment          |             |                       |
| required. It is free text.     |             |                       |
+--------------------------------+-------------+-----------------------+
| Air Conditioning               | AC-         | AC-TRUE               |
|                                |             |                       |
| Select from the drop-down as   |             | (default is FALSE)    |
| preferred.                     |             |                       |
+--------------------------------+-------------+-----------------------+
| Airport Pickup                 | PU-         | PU-FALSE              |
|                                |             |                       |
| This is a drop-down menu where |             | (default value)       |
| you select if the pickup will  |             |                       |
| be at the airport or not.      |             |                       |
+--------------------------------+-------------+-----------------------+
| Airport Drop Off               | DO-         | DO-TRUE               |
|                                |             |                       |
| This is a drop-down menu where |             | (default is FALSE)    |
| you select if the drop off     |             |                       |
| will be at the airport or not. |             |                       |
+--------------------------------+-------------+-----------------------+

# HOTEL TAB

This is where all the details regarding the proposal for a Hotel segment
are added.

## Hotel Tab completion flow

## Hotel Tab ![](./images/media/image7.png){width="6.69375in" height="2.939583333333333in"}

N.B. The summary of each segment will be displayed as a row under the
"Total Hotel Segments". The segment counter will be incremented once
each segment is added

##  Hotel Tab table of definitions 

### Hotel Tab mandatory information

+----------------------------------+----------------+------------------+
| File input                       | PNR Remark     | PNR Remark       |
|                                  | label          | examples         |
| and description                  |                |                  |
+==================================+================+==================+
| HOTEL                            | SEG-           | SEG-HOT          |
|                                  |                |                  |
| This is the tab name and the     |                |                  |
| segment type.                    |                |                  |
+----------------------------------+----------------+------------------+
| \(1\) Country Code               | SCO-           | SCO-GB           |
|                                  |                |                  |
| This is the destination          |                |                  |
| two-letter country code.         |                |                  |
+----------------------------------+----------------+------------------+
| \(2\) Destination City           | SCITY-         | SCITY-LONDON     |
|                                  |                |                  |
| This is the destination city     |                |                  |
| name in full                     |                |                  |
+----------------------------------+----------------+------------------+
| \(3\) Destination Location Code  | SCODE-         | SCODE-GBLHR      |
|                                  |                |                  |
| This is the UN Location Code for |                |                  |
| Destination                      |                |                  |
+----------------------------------+----------------+------------------+
| \(4\) Destination IATA           | SIATA-         | SIATA-LHR        |
|                                  |                |                  |
| This is the IATA three-letter    |                |                  |
| code of the destination city.    |                |                  |
+----------------------------------+----------------+------------------+
| \(5\) Hotel Name                 | HTLNAME-       | HTLNAME-LEA      |
|                                  |                | PALACE           |
| This is where you enter the      |                |                  |
| hotel name.                      |                |                  |
+----------------------------------+----------------+------------------+
| \(6\) Check-In Date and Time     | SDTE-.../AT-   | SDTE-20          |
|                                  |                | 23-11-17/AT-1520 |
| This is the check-in date and    |                |                  |
| time using the following format: |                |                  |
|                                  |                |                  |
| -   Date is in the format        |                |                  |
|     DD/MMM/YYYY                  |                |                  |
|                                  |                |                  |
| -   Time is in the format HHMM   |                |                  |
|     and is 24 hours              |                |                  |
+----------------------------------+----------------+------------------+
| \(7\) Check-Out Date and Time    | EDTE-.../AT-   | EDTE-20          |
|                                  |                | 23-11-20/AT-1200 |
| This is the check-out date and   |                |                  |
| time using the following format: |                |                  |
|                                  |                |                  |
| -   Date is in the format        |                |                  |
|     DD/MMM/YYYY                  |                |                  |
|                                  |                |                  |
| -   Time is in the format HHMM   |                |                  |
|     and is 24 hours              |                |                  |
+----------------------------------+----------------+------------------+
| \(8\) Confirmation Number        | CONF-          | CONF-ABCDEF      |
|                                  |                |                  |
| This is where you will add the   |                | CONF-NA          |
| provider reference if you have   |                |                  |
| selected "Booked".               |                | (default value   |
|                                  |                | if blank)        |
| This is only mandatory when      |                |                  |
| Booked is checked.               |                |                  |
+----------------------------------+----------------+------------------+
| \(9\) Supplier Name              | SUP-           | SUP-SHERATON     |
|                                  |                |                  |
| This is where you enter the      |                |                  |
| supplier name in full.           |                |                  |
+----------------------------------+----------------+------------------+
| \(10\) Rate                      | VAL-           | VAL-125.20       |
|                                  |                |                  |
| This is the total amount of the  |                |                  |
| Hotel segment.                   |                |                  |
|                                  |                |                  |
| It will automatically format to  |                |                  |
| 2 decimal places if not typed.   |                |                  |
|                                  |                |                  |
| We currently only support        |                |                  |
| decimalized currencies.          |                |                  |
+----------------------------------+----------------+------------------+

[]{#_Toc94552504 .anchor}Hotel Tab optional information

+-------------------------------+----------+--------------------------+
| File input                    | PNR      | PNR Remark examples      |
|                               | Remark   |                          |
| and description               | label    | with default value       |
|                               |          | information              |
+===============================+==========+==========================+
| Booked                        | BKD-     | BKD-FALSE                |
|                               |          |                          |
| If you check "Booked", the    |          | (default value)          |
| "Confirmation Number" field   |          |                          |
| will become mandatory.        |          |                          |
+-------------------------------+----------+--------------------------+
| Confirmation Number           | CONF-    | CONF-A123456             |
|                               |          |                          |
| This is where you add the     |          | or                       |
| provider confirmation number  |          |                          |
| if the hotel has been booked  |          | CONF-NA                  |
| directly with the provider.   |          |                          |
|                               |          | (default value)          |
| This is optional when         |          |                          |
| "Booked" is not selected.     |          |                          |
+-------------------------------+----------+--------------------------+
| Location Details              | NOTE-    | NOTE-DOWNTOWN            |
|                               |          |                          |
| This is a free text field     |          | (not shown if blank)     |
| where you can add information |          |                          |
| about the hotel location.     |          |                          |
+-------------------------------+----------+--------------------------+
| Hotel Address                 | ADD-     | ADD-ASTON ROAD, LONDON   |
|                               |          |                          |
| This is where you add the     |          | (not shown if blank)     |
| hotel address information.    |          |                          |
+-------------------------------+----------+--------------------------+
| Hotel Zip Code                | ZIP-     | ZIP-LW45 6ER             |
|                               |          |                          |
| This is the zip code of the   |          | (not shown if blank)     |
| hotel location                |          |                          |
+-------------------------------+----------+--------------------------+
| Phone Number                  | PH-      | PH-0044 1256321          |
|                               |          |                          |
| This is where you add the     |          | (not shown if blank)     |
| hotel phone number            |          |                          |
+-------------------------------+----------+--------------------------+
| Segment Policy Compliant      | CMPL-    | CMPL-True                |
| (True or False)               |          |                          |
|                               |          | (not shown if blank)     |
| This will be a Boolean value  |          |                          |
| True or False                 |          |                          |
+-------------------------------+----------+--------------------------+
| Room Type                     | ROOM-    | ROOM-DOUBLE              |
|                               |          |                          |
| This is where you can enter   |          | (not shown if blank)     |
| the room type in full.        |          |                          |
|                               |          |                          |
| It is free text.              |          |                          |
+-------------------------------+----------+--------------------------+
| Comments                      | RMKS-    | RMKS-24HR CXX POLICY     |
|                               |          |                          |
| This is where you can add any |          | (not shown if blank)     |
| additional comments such as   |          |                          |
| cancellation policy.          |          |                          |
+-------------------------------+----------+--------------------------+

## RAIL TAB

This is where all the details regarding the rail segment are added.

## Rail Tab completion flow for one-way rail

## Rail Tab one-way screenshot example

![](./images/media/image8.png){width="6.69375in"
height="2.8493055555555555in"}

N.B. The summary of each segment will be displayed as a row under the
"Total Rail Segments". The segment counter will be incremented once each
segment is added

## Rail Tab one-way table of definitions

### Rail Tab one-way mandatory information

+--------------------------------------+----------+--------------------+
| File input                           | PNR      | PNR Remark         |
|                                      | Remark   | examples           |
| and description                      | label    |                    |
+======================================+==========+====================+
| RAIL -- One Way                      | SEG-     | SEG-RAIL1          |
|                                      |          |                    |
| This is the tab name and the segment |          |                    |
| type.                                |          |                    |
+--------------------------------------+----------+--------------------+
| \(1\) Booked                         | BKD-     | BKD-FALSE          |
|                                      |          |                    |
| Check the field "Booked" if you have |          | (default value)    |
| confirmed the booking with the       |          |                    |
| provider. The "Confirmation Number"  |          |                    |
| field will then become mandatory.    |          |                    |
+--------------------------------------+----------+--------------------+
| \(2\) Fare                           | VAL-     | VAL-250.00         |
|                                      |          |                    |
| This is the total amount of the rail |          |                    |
| segment.                             |          |                    |
|                                      |          |                    |
| It will automatically format to 2    |          |                    |
| decimal places if not typed.         |          |                    |
|                                      |          |                    |
| We currently only support            |          |                    |
| decimalized currencies.              |          |                    |
+--------------------------------------+----------+--------------------+
| \(3\) Booking Source                 | STYPE-   | STYPE-SNCF         |
|                                      |          |                    |
| This is the rail provider booking    |          |                    |
| source. It is a drop-down menu of    |          |                    |
| the supported providers.             |          |                    |
+--------------------------------------+----------+--------------------+
| \(4\) Departure Country Code         | SCO-     | SCO-FR             |
|                                      |          |                    |
| This is the two-letter IATA          |          |                    |
| departure country code.              |          |                    |
+--------------------------------------+----------+--------------------+
| \(5\) Departure Station Name         | CODE-    | CODE-FRDHP         |
|                                      |          |                    |
| This is the departure station name   | NAME-    | NAME-PARIS         |
| from the drop down provided and      |          | MONTPARNASSE 2     |
| includes the departure rail station  |          | PASTEUR            |
| code. Items in the list are supplier |          |                    |
| specific.                            |          |                    |
+--------------------------------------+----------+--------------------+
| \(6\) Confirmation Number            | CONF-    | CONF-A123456       |
|                                      |          |                    |
| This is where you will add the       |          | or                 |
| provider reference if you have       |          |                    |
| selected "Booked". This is only      |          | CONF-NA            |
| mandatory when Booked is checked.    |          |                    |
|                                      |          | (default value)    |
+--------------------------------------+----------+--------------------+
| \(7\) Arrival Country Code           | CO-      | CO-GB              |
|                                      |          |                    |
| This is the two-letter IATA arrival  |          |                    |
| country code.                        |          |                    |
|                                      |          |                    |
| It is a drop-down menu.              |          |                    |
+--------------------------------------+----------+--------------------+
| \(8\) Arrival Station Name           | CODE-    | CODE-GBBLL         |
|                                      |          |                    |
| This is the arrival station name     | NAME-    | NAME-BLACKFRIARS   |
| from the drop down provided and      |          | LONDON             |
| includes the rail station code.      |          |                    |
| Items in the list are supplier       |          |                    |
| specific.                            |          |                    |
+--------------------------------------+----------+--------------------+
| \(9\) Carrier Name                   | SUP-     | SUP-EUROSTAR       |
|                                      |          |                    |
| This is the carrier name in full.    |          |                    |
+--------------------------------------+----------+--------------------+
| \(10\) Departure Date and Time       | DTE      | DTE-               |
|                                      | -.../AT- | 2023-11-19/AT-0850 |
| This is the departure date and time  |          |                    |
| using the following format:          |          |                    |
|                                      |          |                    |
| -   Date is in the format            |          |                    |
|     DD/MMM/YYYY                      |          |                    |
|                                      |          |                    |
| -   Time is in the format HHMM and   |          |                    |
|     is 24 hours                      |          |                    |
+--------------------------------------+----------+--------------------+
| \(11\) Arrival Date and Time         | DTE      | DTE-               |
|                                      | -.../AT- | 2023-11-19/AT-1100 |
| This is the arrival date and time    |          |                    |
| using the following format:          |          |                    |
|                                      |          |                    |
| -   Date is in the format            |          |                    |
|     DD/MMM/YYYY                      |          |                    |
|                                      |          |                    |
| -   Time is in the format HHMM and   |          |                    |
|     is 24 hours                      |          |                    |
+--------------------------------------+----------+--------------------+

### Rail Tab one-way optional information

+--------------------------------------+----------+--------------------+
| File input                           | PNR      | PNR Remark         |
|                                      | Remark   | examples           |
| and description                      | label    |                    |
|                                      |          | with default value |
|                                      |          | information        |
+======================================+==========+====================+
| Booked                               | BKD-     | BKD-FALSE          |
|                                      |          |                    |
| Check the field "Booked" if you have |          | (default value)    |
| confirmed the booking with the       |          |                    |
| provider. "Confirmation Number"      |          |                    |
| field will then become mandatory     |          |                    |
+--------------------------------------+----------+--------------------+
| Confirmation Number                  | CONF-    | CONF-A12345        |
|                                      |          |                    |
| This is where you add the provider   |          | or                 |
| confirmation number if applicable.   |          |                    |
| This is optional if "Booked" is not  |          | CONF-NA            |
| checked.                             |          |                    |
|                                      |          | (default value)    |
+--------------------------------------+----------+--------------------+
| Class of Services                    | C-       | C-STANDARD         |
|                                      |          |                    |
| This is the class of services in     |          | (not shown if      |
| full.                                |          | blank)             |
+--------------------------------------+----------+--------------------+
| Duration                             | DUR-     | DUR-280            |
|                                      |          |                    |
| This is the trip duration in         |          | (shows as DUR-/ if |
| minutes.                             |          | blank)             |
+--------------------------------------+----------+--------------------+
| Train Number                         | TRN-     | TRN-4              |
|                                      |          |                    |
| This is where you add the train      |          | (not shown if      |
| number.                              |          | blank)             |
+--------------------------------------+----------+--------------------+
| Wagon Number                         | WAG-     | WAG-8              |
|                                      |          |                    |
| This is where you add the wagon      |          | (not shown if      |
| number.                              |          | blank)             |
+--------------------------------------+----------+--------------------+
| Seat Number                          | SEAT-    | SEAT-1C            |
|                                      |          |                    |
| This is where you add the seat       |          | (not shown if      |
| number.                              |          | blank)             |
+--------------------------------------+----------+--------------------+
| Segment Policy Compliant (True or    | CMPL-    | CMPL-True          |
| False)                               |          |                    |
|                                      |          | (not shown if      |
| This will be a Boolean value True or |          | blank)             |
| False                                |          |                    |
+--------------------------------------+----------+--------------------+
| Comments                             | RMKS-    | RMKS-QUIET ZONE    |
|                                      |          | AVAILABLE          |
| This is where you add any free text  |          |                    |
| information.                         |          | (not shown if      |
|                                      |          | blank)             |
+--------------------------------------+----------+--------------------+

## 

## SEGMENT COUNTERS:

-   From this version we have added a new feature which keeps track of
    number of segments added for each tab - air/car/hotel/rail

-   The "Total Segments created" counter indicates Total number of
    segments created.

-   The limit on Total number of segments to be created will be set in
    the variable "**constSegCount**"

![](./images/media/image9.png){width="6.7769006999125105in"
height="1.093416447944007in"}

## 

## CONCATENATION

Remark concatenation allows for multiple remark lines to be copied in a
single block. Where the maximum number of concatenations has been
reached, a new remark block will be created. This ensures that the
minimum number of copy and paste actions is required.

For more information on configuring concatenation, please see
[Configuration](#configuration) above.

[Example of blocks:]{.underline}

@:5P/APTR/54/PROP1/GEN/LIMIT-2023-03-31T102500.000ZPLUS0000+@:5P/APTR/27/PROP1/GEN/BKD-FALSE+@:5P/APTR/53/PROP1/GEN/RMKS-GENERAL
TAB COMMENTS FREE TEXT+@:5P/APTR/28/PROP1/GEN/LOC-2NCMIA

@:5P/APTR/55/PROP1/SEG-AIR1/BKD-FALSE/RMKS-AIR COMMENTS
TEST+@:5P/APTR/46/PROP1/SEG-AIR1/SDTE-2023-11-17/ST-0930+@:5P/APTR/57/PROP1/SEG-AIR1/EDTE-2023-11-17/ET-1130/PNR-2NCMIA+@:5P/APTR/44/PROP1/SEG-AIR1/CMPL-TRUE/CONF-ABCDEF+@:5P/APTR/40/PROP1/SEG-AIR1/C-ECONOMY/DUR-150+@:5P/APTR/39/PROP1/SEG-AIR1/FN-BA258/SEAT-2C+@:5P/APTR/32/PROP1/SEG-AIR1/SIATA-LHR+@:5P/APTR/32/PROP1/SEG-AIR1/EIATA-CDG+@:5P/APTR/30/PROP1/SEG-AIR1/EQP-757

@:5P/APTR/40/PROP1/SEG-AIR1/TD-NORTH/TA-SOUTH+@:5P/APTR/42/PROP1/SEG-AIR1/CURR-USD/VAL-0.00

@:5P/APTR/32/PROP1/SEG-AIR2/BKD-FALSE+@:5P/APTR/52/PROP1/SEG-AIR2/RMKS-RETURN
AIR COMMENTS
TEST+@:5P/APTR/46/PROP1/SEG-AIR2/SDTE-2023-11-20/ST-0930+@:5P/APTR/57/PROP1/SEG-AIR2/EDTE-2023-11-20/ET-1130/PNR-2NCMIA+@:5P/APTR/44/PROP1/SEG-AIR2/CMPL-TRUE/CONF-ABDDEE+@:5P/APTR/40/PROP1/SEG-AIR2/C-ECONOMY/DUR-150+@:5P/APTR/39/PROP1/SEG-AIR2/FN-BA258/SEAT-2C+@:5P/APTR/32/PROP1/SEG-AIR2/SIATA-CDG+@:5P/APTR/32/PROP1/SEG-AIR2/EIATA-LHR

@:5P/APTR/30/PROP1/SEG-AIR2/EQP-757+@:5P/APTR/40/PROP1/SEG-AIR2/TD-SOUTH/TA-NORTH+@:5P/APTR/42/PROP1/SEG-AIR2/CURR-USD/VAL-215.00

@:5P/APTR/57/PROP1/SEG-CAR1/BKD-FALSE/RMKS-CAR COMMENT
EXAMPLE+@:5P/APTR/34/PROP1/SEG-CAR1/CONF-ABCDEF+@:5P/APTR/46/PROP1/SEG-CAR1/SDTE-2023-11-17/ST-1200+@:5P/APTR/46/PROP1/SEG-CAR1/EDTE-2023-11-17/ET-1430+@:5P/APTR/34/PROP1/SEG-CAR1/SCODE-FRPLD+@:5P/APTR/34/PROP1/SEG-CAR1/ECODE-FRLYS+@:5P/APTR/43/PROP1/SEG-CAR1/PNR-2NCMIA/CMPL-TRUE+@:5P/APTR/31/PROP1/SEG-CAR1/SUP-AVIS+@:5P/APTR/51/PROP1/SEG-CAR1/SCO-FR/SCITY-PARIS/SIATA-PAR

@:5P/APTR/50/PROP1/SEG-CAR1/ECO-FR/ECITY-LYON/EIATA-LYS+@:5P/APTR/30/PROP1/SEG-CAR1/AC-TRUE+@:5P/APTR/29/PROP1/SEG-CAR1/TRAN-A+@:5P/APTR/32/PROP1/SEG-CAR1/C-COMPACT+@:5P/APTR/38/PROP1/SEG-CAR1/PUPH-1233333333+@:5P/APTR/37/PROP1/SEG-CAR1/DOPH-415747777+@:5P/APTR/51/PROP1/SEG-CAR1/PU-FALSE/DO-TRUE/EQP-SAT
NAV+@:5P/APTR/41/PROP1/SEG-CAR1/SNOTE-RAIL
STATION+@:5P/APTR/48/PROP1/SEG-CAR1/ENOTE-AT HILTON RECEPTION

@:5P/APTR/42/PROP1/SEG-CAR1/CURR-USD/VAL-150.00

@:5P/APTR/54/PROP1/SEG-HOT1/BKD-FALSE/RMKS-24HR CXX POLICY
+@:5P/APTR/34/PROP1/SEG-HOT1/CONF-ABCDEF+@:5P/APTR/43/PROP1/SEG-HOT1/SDTE-2023-11-17/ST-/+@:5P/APTR/43/PROP1/SEG-HOT1/EDTE-2023-11-20/ET-/+@:5P/APTR/34/PROP1/SEG-HOT1/SCODE-GBLHR+@:5P/APTR/43/PROP1/SEG-HOT1/PNR-2NCMIA/CMPL-TRUE+@:5P/APTR/35/PROP1/SEG-HOT1/SUP-SHERATON+@:5P/APTR/52/PROP1/SEG-HOT1/SCO-GB/SCITY-LONDON/SIATA-LHR+@:5P/APTR/41/PROP1/SEG-HOT1/HTLNAME-LEA
PALACE

@:5P/APTR/34/PROP1/SEG-HOT1/ROOM-DOUBLE+@:5P/APTR/38/PROP1/SEG-HOT1/PH-0044
1256321+@:5P/APTR/36/PROP1/SEG-HOT1/NOTE-DOWNTOWN+@:5P/APTR/42/PROP1/SEG-HOT1/CURR-USD/VAL-125.20+@:5P/APTR/45/PROP1/SEG-HOT1/ADD-ASTON
ROAD, LONDON+@:5P/APTR/35/PROP1/SEG-HOT1/ZIP-LW45 6ER

@:5P/APTR/33/PROP1/SEG-RAIL1/BKD-FALSE+@:5P/APTR/50/PROP1/SEG-RAIL1/RMKS-QUIET
ZONE AVAILABLE
+@:5P/APTR/36/PROP1/SEG-RAIL1/CONF-A123456+@:5P/APTR/47/PROP1/SEG-RAIL1/SDTE-2023-11-19/ST-0850+@:5P/APTR/47/PROP1/SEG-RAIL1/EDTE-2023-11-19/ET-1100+@:5P/APTR/44/PROP1/SEG-RAIL1/PNR-2NCMIA/CMPL-TRUE+@:5P/APTR/36/PROP1/SEG-RAIL1/SUP-EUROSTAR+@:5P/APTR/51/PROP1/SEG-RAIL1/SCO-FR/SCODE-FRDHP/STYPE-2C+@:5P/APTR/57/PROP1/SEG-RAIL1/NAME-PARIS
MONTPARNASSE 2 PASTEUR

@:5P/APTR/51/PROP1/SEG-RAIL1/ECO-GB/ECODE-GBBLL/ETYPE-2C+@:5P/APTR/47/PROP1/SEG-RAIL1/NAME-BLACKFRIARS
LONDON+@:5P/APTR/43/PROP1/SEG-RAIL1/CURR-USD/VAL-250.00+@:5P/APTR/42/PROP1/SEG-RAIL1/C-STANDARD/DUR-280+@:5P/APTR/35/PROP1/SEG-RAIL1/TRN-4/WAG-8+@:5P/APTR/31/PROP1/SEG-RAIL1/SEAT-1C

# REMARK SEPARATORS

Remark entries use a single forward slash between fields but may also
contain a double forward slash for long remark content.

The single forward slash **/** denotes the end of a field and the
beginning of the next field.

A forward slash **/** is a **reserved character** and should **not** be
added in any field.

The double forward slash **//** denotes that the content is longer than
the line length permitted by the GDS. The remaining content is then
split into a new entry or entries with no label. The number of splits
will depend on how many are required.

Double slash example:

@:5P/APTR/54/PROP1/SEG-AIR2/RMKS-**COMMENTS FOR THE RETURN**

//+@:5P/APTR/34/PROP1/SEG-AIR2/**AIR SEGMENT**

# VERSION HISTORY

+----------------------+-----------------------------------------------+
| **Data Formatter for | Amendments dates                              |
| Concur Request       |                                               |
| Version Number**     |                                               |
+======================+===============================================+
| V2.10                | **02Jun21**                                   |
|                      |                                               |
| v2.11                | ALL TABS :                                    |
|                      |                                               |
| v2.12                | -   Time - can now be entered manually only   |
|                      |                                               |
| v2.12.1              | -   Date - user can manually enter the date   |
|                      |     or use the calendar                       |
| v2.12.2              |                                               |
|                      |     AIR, CAR, HOTEL and RAIL TABS:            |
|                      |                                               |
|                      | -   Fare/Rate - two decimals will be added    |
|                      |     automatically if not entered in the       |
|                      |     corresponding field                       |
|                      |                                               |
|                      | -   Policy compliance - accept only numeric   |
|                      |     value between 0 and 100                   |
|                      |                                               |
|                      |     AIR and RAIL TABS:                        |
|                      |                                               |
|                      | -   Policy compliance - will now show for     |
|                      |     each leg in case of return trips          |
|                      |                                               |
|                      |     AIR TAB:                                  |
|                      |                                               |
|                      | -   Departure/Arrival Details - Mandatory and |
|                      |     Optional information are now on the same  |
|                      |     block for the air one-way segment         |
|                      |                                               |
|                      | -   Return Details - Mandatory and optional   |
|                      |     information are now on the same block     |
|                      |                                               |
|                      |     RAIL TAB:                                 |
|                      |                                               |
|                      | -   Departure/Arrival Details - Mandatory and |
|                      |     optional information are now on the same  |
|                      |     block for the rail one-way segment        |
|                      |                                               |
|                      | -   Return Details - Mandatory and optional   |
|                      |     information are now on the same block     |
|                      |                                               |
|                      |     CAR TAB:                                  |
|                      |                                               |
|                      | -   Drop Off Details - this field is now      |
|                      |     optional                                  |
|                      |                                               |
|                      |     OPTIONAL INFORMATION                      |
|                      |                                               |
|                      | -   We will show the data in the remarks only |
|                      |     if the value is entered in the            |
|                      |     file.(please refer to each optional field |
|                      |     for each segment                          |
|                      |                                               |
|                      |     **07Jun21**                               |
|                      |                                               |
|                      |     CAR TAB                                   |
|                      |                                               |
|                      | -   Location data has now been added          |
|                      |                                               |
|                      | -   Drop Off Details is now optional          |
|                      |                                               |
|                      | ALL TABS                                      |
|                      |                                               |
|                      | -   Currency fields will now accept only      |
|                      |     alpha characters                          |
|                      |                                               |
|                      | AIR and RAIL TAB                              |
|                      |                                               |
|                      | -   For return trips we have now all the      |
|                      |     information boxes on the same page        |
|                      |                                               |
|                      |     GENERATE CODE                             |
|                      |                                               |
|                      | -   Introduction of the concatenation of the  |
|                      |     remarks                                   |
|                      |                                               |
|                      |     **28Jun21**                               |
|                      |                                               |
|                      | -   Concatenation has been implemented        |
|                      |                                               |
|                      | -   Bug fixes (Hotel Phone now populated in   |
|                      |     the remarks when added, double "/" in the |
|                      |     car remarks)                              |
|                      |                                               |
|                      |     **30Jun21**                               |
|                      |                                               |
|                      | -   File name has been updated                |
|                      |                                               |
|                      | -   UI updates (adding "Return" before        |
|                      |     "Confirmation number" and "Policy         |
|                      |     Compliance Level" fields)                 |
|                      |                                               |
|                      |     **03Aug21**                               |
|                      |                                               |
|                      | ```{=html}                                    |
|                      | <!-- -->                                      |
|                      | ```                                           |
|                      | -   Airline name removed from One Way and     |
|                      |     Return                                    |
+----------------------+-----------------------------------------------+

+----------------------+-----------------------------------------------+
| **Data Formatter for | Amendments dates                              |
| Concur Request       |                                               |
| Version Number**     |                                               |
+======================+===============================================+
| V3.0                 | **31Jan22**                                   |
|                      |                                               |
|                      | ALL TABS :                                    |
|                      |                                               |
|                      | -   Currency removed from all tabs and moved  |
|                      |     to common section as a single field       |
|                      |                                               |
|                      |     GENERAL TAB:                              |
|                      |                                               |
|                      | -   General tab is removed, and all the       |
|                      |     fields are moved to common section.       |
|                      |                                               |
|                      |     AIR, CAR, HOTEL and RAIL TABS:            |
|                      |                                               |
|                      | -   Meals has been removed from Air Tab       |
|                      |                                               |
|                      | -   Option to Add multiple segments for each  |
|                      |     tab                                       |
|                      |                                               |
|                      | -   Multi city segment feature has been added |
|                      |                                               |
|                      | -   Added segment counters for each tab.      |
|                      |                                               |
|                      |     Generate GDS code Section:                |
|                      |                                               |
|                      | ```{=html}                                    |
|                      | <!-- -->                                      |
|                      | ```                                           |
|                      | -   This section enables to generate code for |
|                      |     each GDS without reentering values for    |
|                      |     each segment.                             |
+----------------------+-----------------------------------------------+
| V3.1                 | **01MAR23**                                   |
|                      |                                               |
|                      | ALL TABS :                                    |
|                      |                                               |
|                      | -   Policy compliant level field is renamed   |
|                      |     to "Segment Policy Compliant" and is now  |
|                      |     Boolean value (True or False).            |
+----------------------+-----------------------------------------------+

N.B. This document v3.1 is a guide for the file v3.3 and supersedes any
previous documentation
