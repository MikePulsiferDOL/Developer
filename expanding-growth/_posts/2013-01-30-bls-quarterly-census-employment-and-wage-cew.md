---
layout: post
title: Quarterly Census Employment and Wage (CEW)
created: 1359578858
description: The Quarterly Census of Employment and Wages (QCEW) program publishes a quarterly count of employment and wages reported by employers covering 98 percent of U.S. jobs, available at the county, MSA, state and national levels by industry.
---

```
http://api.dol.gov/V1/Statistics/CEW
```

<p>The Quarterly Census of Employment and Wages (QCEW) program publishes a quarterly count of employment and wages reported by employers covering 98 percent of U.S. jobs, available at the county, MSA, state and national levels by industry.</p>

<p>More information and details about the data provided can be found at <a href="http://www.bls.gov/cew">http://www.bls.gov/cew</a></p>


<a href ="http://api.dol.gov/V1/Statistics/CEW/$metadata" class="button radius button_dataset">Browse Metadata</a>
<a href ="https://devtools.dol.gov/APISampler/Home/Index1?datasetName=BLS%20Quarterly%20Census%20Employment%20and%20Wage%20(CEW)" class="button radius button_dataset">Explore This Data</a>


## Dataset Tables  

- [EN_AREA](#EN_AREA)
- [EN_DATA_PUB](#EN_DATA_PUB)
- [EN_FOOTNOTE](#EN_FOOTNOTE)
- [EN_INDUSTRY](#EN_INDUSTRY)
- [EN_LQAREA](#EN_LQAREA)
- [EN_OWNER](#EN_OWNER)
- [EN_SERIES](#EN_SERIES)
- [EN_STATE](#EN_STATE)
- [EN_TYPE](#EN_TYPE)

<h3><a id="EN_AREA">EN_AREA</a></h3>


<table>
	<thead>
		<tr>
			<th>Column Name</th>
			<th>Column Description</th>
			<th>Data Type</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<th>AREA_CODE</th>
			<td>Area Code</td>
			<td>varchar (5)</td>
		</tr>
		<tr>
			<th>AREA_TITLE</th>
			<td>Area Name</td>
			<td>varchar (60)</td>
		</tr>
		<tr>
			<th>DISPLAY_LEVEL</th>
			<td>Display Indent Level For Query Tool</td>
			<td>varchar (2)</td>
		</tr>
		<tr>
			<th>SELECTABLE</th>
			<td>Code To Allow/Disallow Query Tool Selection</td>
			<td>varchar (1)</td>
		</tr>
		<tr>
			<th>SORT_SEQUENCE</th>
			<td>Data Query Tool Widget Sorting</td>
			<td>varchar (5)</td>
		</tr>
	</tbody>
</table>
<h3><a id="EN_DATA_PUB">EN_DATA_PUB</a></h3>

<table>
	<thead>
		<tr>
			<th>Column Name</th>
			<th>Column Description</th>
			<th>Data Type</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<th>SERIES_ID</th>
			<td>Series Identifier Code</td>
			<td>varchar (17)</td>
		</tr>
		<tr>
			<th>YEAR</th>
			<td>Data Observation Year</td>
			<td>varchar (4)</td>
		</tr>
		<tr>
			<th>PERIOD</th>
			<td>Data Observation Period (Month, Quarter, Semi-Annual, Annual)</td>
			<td>varchar (3)</td>
		</tr>
		<tr>
			<th>VALUE</th>
			<td>Data Observation/Estimate</td>
			<td>varchar (12)</td>
		</tr>
		<tr>
			<th>FOOTNOTE_CODES</th>
			<td>Footnote Codes</td>
			<td>varchar (10)</td>
		</tr>
	</tbody>
</table>
<h3><a id="EN_FOOTNOTE">EN_FOOTNOTE</a></h3>

<table>
	<thead>
		<tr>
			<th>Column Name</th>
			<th>Column Description</th>
			<th>Data Type</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<th>FOOTNOTE_CODE</th>
			<td>Footnote Code</td>
			<td>varchar (2)</td>
		</tr>
		<tr>
			<th>FOOTNOTE_TEXT</th>
			<td>Footnote Code Description</td>
			<td>varchar (150)</td>
		</tr>
	</tbody>
</table>
<h3><a id="EN_INDUSTRY">EN_INDUSTRY</a></h3>

<table>
	<thead>
		<tr>
			<th>Column Name</th>
			<th>Column Description</th>
			<th>Data Type</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<th>INDUSTRY_CODE</th>
			<td>Industry Code</td>
			<td>varchar (6)</td>
		</tr>
		<tr>
			<th>INDUSTRY_TITLE</th>
			<td>Industry Code Description</td>
			<td>varchar (60)</td>
		</tr>
		<tr>
			<th>DISPLAY_LEVEL</th>
			<td>Display Indent Level For Query Tool</td>
			<td>varchar (2)</td>
		</tr>
		<tr>
			<th>SELECTABLE</th>
			<td>Code To Allow/Disallow Query Tool Selection</td>
			<td>varchar (1)</td>
		</tr>
		<tr>
			<th>SORT_SEQUENCE</th>
			<td>Data Query Tool Widget Sorting</td>
			<td>varchar (5)</td>
		</tr>
	</tbody>
</table>
<h3><a id="EN_LQAREA">EN_LQAREA</a></h3>

<table>
	<thead>
		<tr>
			<th>Column Name</th>
			<th>Column Description</th>
			<th>Data Type</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<th>AREA_CODE</th>
			<td>Location Quotient Application Area Code</td>
			<td>varchar (5)</td>
		</tr>
		<tr>
			<th>AREA_TITLE</th>
			<td>Location Quotient Application Area Name</td>
			<td>varchar (60)</td>
		</tr>
		<tr>
			<th>DISPLAY_LEVEL</th>
			<td>Location Quotient Application Area Code</td>
			<td>varchar (2)</td>
		</tr>
		<tr>
			<th>SELECTABLE</th>
			<td>Code To Allow/Disallow Query Tool Selection</td>
			<td>varchar (1)</td>
		</tr>
		<tr>
			<th>SORT_SEQUENCE</th>
			<td>Data Query Tool Widget Sorting</td>
			<td>varchar (5)</td>
		</tr>
	</tbody>
</table>
<h3><a id="EN_OWNER">EN_OWNER</a></h3>

<table>
	<thead>
		<tr>
			<th>Column Name</th>
			<th>Column Description</th>
			<th>Data Type</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<th>OWNER_CODE</th>
			<td>Establishment Ownership Code</td>
			<td>varchar (1)</td>
		</tr>
		<tr>
			<th>OWNER_TITLE</th>
			<td>Establishment Ownership Code Description</td>
			<td>varchar (30)</td>
		</tr>
		<tr>
			<th>DISPLAY_LEVEL</th>
			<td>Display Indent Level For Query Tool</td>
			<td>varchar (2)</td>
		</tr>
		<tr>
			<th>SELECTABLE</th>
			<td>Code To Allow/Disallow Query Tool Selection</td>
			<td>varchar (1)</td>
		</tr>
		<tr>
			<th>SORT_SEQUENCE</th>
			<td>Data Query Tool Widget Sorting</td>
			<td>varchar (5)</td>
		</tr>
	</tbody>
</table>
<h3><a id="EN_SERIES">EN_SERIES</a></h3>

<table>
	<thead>
		<tr>
			<th>Column Name</th>
			<th>Column Description</th>
			<th>Data Type</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<th>SERIES_ID</th>
			<td>Series Identifier Code</td>
			<td>varchar (17)</td>
		</tr>
		<tr>
			<th>AREA_CODE</th>
			<td>Area Code</td>
			<td>varchar (5)</td>
		</tr>
		<tr>
			<th>TYPE_CODE</th>
			<td>Data Type Code</td>
			<td>varchar (1)</td>
		</tr>
		<tr>
			<th>SIZE_CODE</th>
			<td>Establishment Size Class Code</td>
			<td>varchar (1)</td>
		</tr>
		<tr>
			<th>OWNER_CODE</th>
			<td>Establishment Ownership Code</td>
			<td>varchar (1)</td>
		</tr>
		<tr>
			<th>INDUSTRY_CODE</th>
			<td>Industry Code</td>
			<td>varchar (6)</td>
		</tr>
		<tr>
			<th>STATE_CODE</th>
			<td>State Code / FIPS</td>
			<td>varchar (2)</td>
		</tr>
		<tr>
			<th>FOOTNOTE_CODES</th>
			<td>Footnote Codes</td>
			<td>varchar (10)</td>
		</tr>
		<tr>
			<th>BEGIN_YEAR</th>
			<td>Begin Year Of Series</td>
			<td>varchar (4)</td>
		</tr>
		<tr>
			<th>BEGIN_PERIOD</th>
			<td>Begin Period Of Series</td>
			<td>varchar (3)</td>
		</tr>
		<tr>
			<th>END_YEAR</th>
			<td>End Year Of Series</td>
			<td>varchar (4)</td>
		</tr>
		<tr>
			<th>END_PERIOD</th>
			<td>End Period Of Series</td>
			<td>varchar (3)</td>
		</tr>
	</tbody>
</table>
<h3><a id="EN_STATE">EN_STATE</a></h3>

<table>
	<thead>
		<tr>
			<th>Column Name</th>
			<th>Column Description</th>
			<th>Data Type</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<th>STATE_CODE</th>
			<td>State Code / FIPS</td>
			<td>varchar (2)</td>
		</tr>
		<tr>
			<th>STATE_TITLE</th>
			<td>State Name</td>
			<td>varchar (60)</td>
		</tr>
		<tr>
			<th>DISPLAY_LEVEL</th>
			<td>Display Indent Level For Query Tool</td>
			<td>varchar (2)</td>
		</tr>
		<tr>
			<th>SELECTABLE</th>
			<td>Code To Allow/Disallow Query Tool Selection</td>
			<td>varchar (1)</td>
		</tr>
		<tr>
			<th>SORT_SEQUENCE</th>
			<td>Data Query Tool Widget Sorting</td>
			<td>varchar (5)</td>
		</tr>
	</tbody>
</table>
<h3><a id="EN_TYPE">EN_TYPE</a></h3>

<table>
	<thead>
		<tr>
			<th>Column Name</th>
			<th>Column Description</th>
			<th>Data Type</th>
		</tr>
	</thead>
	<tbody>
		<tr>
			<th>TYPE_CODE</th>
			<td>Data Type Code</td>
			<td>varchar (1)</td>
		</tr>
		<tr>
			<th>TYPE_TITLE</th>
			<td>Data Type Code Description</td>
			<td>varchar (30)</td>
		</tr>
		<tr>
			<th>DISPLAY_LEVEL</th>
			<td>Display Indent Level For Query Tool</td>
			<td>varchar (2)</td>
		</tr>
		<tr>
			<th>SELECTABLE</th>
			<td>Code To Allow/Disallow Query Tool Selection</td>
			<td>varchar (1)</td>
		</tr>
		<tr>
			<th>SORT_SEQUENCE</th>
			<td>Data Query Tool Widget Sorting</td>
			<td>varchar (5)</td>
		</tr>
	</tbody>
</table>
