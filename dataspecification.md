Open Crime Data Specification
===========================================

## **What Data Should a Police Agency Release?**

An agency should release anything that would appear on a Daily Incident Log or Call Log (public information only). Most departments pull something from their RMS. SpotCrime offers Catapult to any agency who doesn’t have the ability to create a public file from their RMS.

We typically ask for Part I and II crime information since most agencies already compile this information for their UCR or NIBRS reporting. Our motto is the more information (as long as it’s public), the better. Our system can decipher and define an array of crime types, as well as sort through what information is important and what information is useless. Information typically not released is victim information, juvenile information, or information pertaining to an arrestee’s personal information.

## **The Date Set Should Include**

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
</table>

## **File Format:**
  A lot of police agencies already generate a public file so as long as it holds the data required above and is in a machine readable format (meaning it can be easily processed by a computer). We also recommend that the data should be downloadable in bulk and publicly displayed on the agency’s or city’s own website. For example, Catapult creates a CSV file. 
<table>
  <tr>
    <td width=47.5%><b>Machine readable formats that fall under the Open Data definition and are accepted under the SpotCrime Standard:</b></td>
    <td width=5%><b></b></td>
    <td width=47.5%><b>Formats that do not fall under the Open Data definition:</b></td>
  </tr>
<tr>
  <td>XML</td>
  <td></td>
  <td>PDF</td>
</tr>
<tr>
  <td>RSS feed</td>
  <td></td>
  <td>HTML</td>
</tr>
<tr>
  <td>CSV</td>
  <td></td>
  <td>.DOC(X)</td>
</tr>
<tr>
  <td>RDF</td>
  <td></td>
  <td>Anything scanned</td>
</tr>
<tr>
  <td>JSON</td>
  <td></td>
  <td>Anything faxed</td>
</tr>
<tr>
  <td>TXT</td>
  <td></td>
  <td>Anything typed in an email</td>
</tr>
<tr>
  <td>XLS(X)</td>
  <td></td>
  <td></td>
</tr>
<tr>
  <td>KML</td>
  <td></td>
  <td></td>
</tr>
</table>

## **Frequency:**
Daily.
Expectations should be set high. Frequency of weekly or longer defeats the purposr of open data.

## **Open Crime Data XML example:**
<table>
 <tr>
  <td width=100%></td>
 </tr>
 <tr>
  <td>
<OpenCrimeData>
  Version="0.1"  # OpenCrimeData standard version.
  Language ="en" # Language data is published in.
  ReportingAgency="NYPD" # Reporting agency.
  ReportingAgencyURL="http://www.nyc.gov/html/nypd" # Reporting agency URL.
  ReportingTimeOffset="-5" # Indicates local time zone offset of the reporting agency.
  PubDate="Date in ISO 8601 format">
<CrimeData>
  <Crime>
    <CaseNumber></CaseNumber>
    <IncidentNumber></IncidentNumber>
    <Date>Crime date in ISO 8601 format</IncidentDate>
    <Time>UTC Time in ISO 8601 format</IncidentTime>
    <Type>Crime Type (not necessarily Spotcrime type).</Type>
    <Description>Crime description</Description>
    <Location>
      <Address>street address</Address>
      <Locality>city</Locality>
      <Region1>state</Region1>
      <Region2>{might be used in some countries}</Region2>
      <PostalCode>Zip</PostalCode>
      <Country>Country, ISO 3166-1 alpha-2</Country>
    </Location>
    <GeoLocation>
      <Latitude></Latitude>
      <Longitude></Longitude>
    </GeoLocation>
  </Crime>
  <Crime>
    ...
  </Crime>
</CrimeData>
</OpenCrimeData>
  </td
 </tr>
</table>
