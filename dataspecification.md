Open Crime Data Specification
===========================================

**What Data Should a Police Agency Release?**

An agency should release anything that would appear on a Daily Incident Log or Call Log (public information only). Most departments pull something from their RMS. SpotCrime offers Catapult to any agency who doesn’t have the ability to create a public file from their RMS.

We typically ask for Part I and II crime information since most agencies already compile this information for their UCR or NIBRS reporting. Our motto is the more information (as long as it’s public), the better. Our system can decipher and define an array of crime types, as well as sort through what information is important and what information is useless. Information typically not released is victim information, juvenile information, or information pertaining to an arrestee’s personal information.

**The Date Set Should Include:**

<table>
  <tr>
    <td width=15%><b>Data Type</b></td>
    <td width=15%><b>Required</b></td>
    <td width=15%><b>Permitted Values</b></td>
    <td width=15%><b>Examples</b></td>
    <td width=40%><b>Details</b></td>
  </tr>
  <tr>
    <td>Area</td>
    <td>Yes</td>
    <td>Text</td>
    <td>Baltimore County, MD</td>
    <td>Defines city/county/jurisdiction and state</td>
  </tr>
 <tr>
    <td>Date</td>
    <td>Yes</td>
    <td>ISO 8601; YYYY-MM-DD</td>
    <td>2014-03-10</td>
    <td>Date occurred. Allows easy identifier and separation of data. Date displayed in mm/dd/yyyy on SpotCrime.</td>
  </tr>
 <tr>
    <td>Time</td>
    <td>Yes</td>
    <td>ISO 8601; UTC and 24 hour</td>
    <td>23:11</td>
    <td>Time occurred. Allows easy identifier and separation of data. Displayed in 12 hour format on SpotCrime.</td>
  </tr>
 <tr>
    <td>Incident Type</td>
    <td>Yes</td>
    <td>Text</td>
    <td>Aggravated Assault</td>
    <td>Allows icons to be assigned and decipher between crime types. SpotCrime dictionary categorizes each incident into 1 of 9 icons.</td>
  </tr>
 <tr>
    <td>Location</td>
    <td>Yes</td>
    <td>Street number and street name</td>
    <td>322 York Road</td>
    <td>Full and block addresses are accepted. Needed for geo-coding accuracy. All full addresses are masked to the block level on SpotCrime.</td>
  </tr>
 <tr>
    <td>City</td>
    <td>Yes</td>
    <td>Text</td>
    <td>Towson, MD</td>
    <td>Needed for geo-coding accuracy. 
</td>
  </tr>
 <tr>
    <td>Narrative</td>
    <td>Yes</td>
    <td>Text</td>
    <td>A victim was stabbed in the abdomen by an unknown subject after a verbal altercation.</td>
    <td>Provides more description and information on incident type (commercial burglary or residential burglary). Displayed in the details section on SpotCrime.</td>
  </tr>
 <tr>
    <td>Longitutde, Latitude</td>
    <td>Yes</td>
    <td>Georaphic coordinate system</td>
    <td>39.399262, -76.602990</td>
    <td>Geo-coding accuracy. Not displayed by SpotCrime.</td>
  </tr>
 <tr>
    <td>Case Number</td>
    <td>Yes</td>
    <td>Text and number accepted</td>
    <td>2014-031023111</td>
    <td>Helps identify specific incidents. Displayed in the details section on SpotCrime.</td>
  </tr>
 <tr>
    <td>Incident Number (if different from case number)</td>
    <td>Optional, highly recommended</td>
    <td>Text and number accepted</td>
    <td> </td>
    <td>Helps identify specific incidents. Displayed in the details section on SpotCrime.</td>
  </tr>
 <tr>
    <td>Beat/Sector</td>
    <td>Optional</td>
    <td>Text and number accepted</td>
    <td>6A</td>
    <td>Displayed in the details section on SpotCrime. </td>
  </tr>
 <tr>
    <td>District/Precinct</td>
    <td>Optional</td>
    <td>Text and number accepted</td>
    <td>Towson</td>
    <td>Displayed in the details section on SpotCrime. </td>
  </tr>
 <tr>
    <td>ZIP Code</td>
    <td>Optional</td>
    <td>US and International postal codes accepted</td>
    <td>21204</td>
    <td>Helps with geo-coding accuracy. Displayed in the details section on SpotCrime.</td>
  </tr>
  
  
