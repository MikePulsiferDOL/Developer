---
layout: post
title: Summer Jobs Service Beta
created: 1359481108
description: The Summer Jobs Plus Bank is a new search tool designed to help connect job seekers with employers.
---

```
http://api.dol.gov/V1/SummerJobs
```

<p>The Summer Jobs Plus Bank is a new search tool designed to help connect job seekers with employers. Summer Jobs Plus allows sites to search job postings using a widget that provides a single window into the myriad job boards, social&nbsp;media platforms, and corporate employment sites that are currently spread across the Internet.</p>

<p>The search widget is powered by a new open Web standard, the JobPosting schema, designed by a voluntary network of job search and technology companies and supported by schema.org—a collaboration among Bing, Google, and Yahoo to make structured data on the Web easier to find.</p>

<p>Interested in adding the widget as a feature on your website? <a href="http://www.dol.gov/summerjobs/Widget.htm">Instructions are found here to learn how to add Summer Jobs Plus widget to your web site</a>.</p>

<p>For employers committed to hiring, "tagging" job listings in the JobPosting schema ensures that those listings will be discoverable through the Summer Jobs Plus Bank.</p>

<p>Read our <a href="http://www.dol.gov/summerjobs/Employers.htm">guide for tagging job posts for the Summer Jobs Plus search</a>.</p>

<h3>Service Operations Details</h3>

<p>The Summer Jobs Plus API is supported using Service Operations. Service Operations provide users the ability to call other services, perform specific tasks, or retrieve data that is not found in the standard API datasets. To use the Summer Jobs Plus API the Operation name and parameters need to be supplied using the data services format. For summer jobs query and skip parameter are required.<br />
Each request to the DOL API also requires the standard authorization header.  <a href="http://developer.dol.gov/req-auth.htm">View the authorization specification here.</a> ​</p>

<p><b>Summer Jobs Signature</b><br />
getJobsListing(string query, string employmentType, string region, string locality, string zip, int skipCount)</p>

<h4><u>Parameter Encoding</u></h4>

<p><b>Strings</b><br />
Each String typed parameter must be surrounded in quotes in order to work correctly. These quotes are then Url encoded and passed to the Service Operation.<br />
' = %27<br />
For example: 'Nurse' Becomes %27Nurse%27<br />
<br />
<b>Int</b><br />
Each integer typed parameter must be entered without quotes in order to work correctly.<br />
<br />
<b>Null Parameter</b><br />
Each parameter that is assigned null should be left blank<br />
<br />
For example: ?region=&amp;locality=<br />
&nbsp;</p>

<h4>Service Operation Examples</h4>

<p>The following queries are examples of requests that can be made to the API to call the Summer Jobs API. Each SDK will require different usages of these forms. <span style="COLOR: #f00">The Summer Jobs API requires either the query parameter to be filled out or, either the region or locality field to be filed out.</span><br />
<br />
<a>http://api.dol.gov/V1/SummerJobs/getJobsListing?format=%27json%27&amp;query=%27Nurse%27&amp;region=&amp;locality=&amp;skipCount=1</a><br />
<a>http://api.dol.gov/V1/SummerJobs/getJobsListing?format=%27xml%27&amp;query=&amp;region=%27FL%27&amp;locality=&amp;skipCount=99</a><br />
<a>http://api.dol.gov/V1/SummerJobs/getJobsListing?format=%27xml%27&amp;query=&amp;region=&amp;locality=%27Tampa%27&amp;skipCount=99</a><br />
<a>http://api.dol.gov/V1/SummerJobs/getJobsListing?format=%27atom%27&amp;query=%27Nurse%27&amp;region=%27New York%27&amp;locality=%27New York%27&amp;skipCount=1</a></p>


<a href ="http://api.dol.gov/V1/SummerJobs/$metadata" class="button radius button_dataset">Browse Metadata</a>


## Dataset Tables  
<h3>List of Service Operations</h3>

<h4>getJobsListing Operation</h4>

<p>- <strong>Returns</strong> a json, xml, or atom formatted string.</p>

<table>
	<tbody>
		<tr>
			<th>Parameter Name</th>
			<th>Parameter Description</th>
			<th>Data Type</th>
		</tr>
		<tr>
			<th>format</th>
			<td>The format that the results string will be returned. <a href="#formatcodes">See below for list</a></td>
			<td>String</td>
		</tr>
		<tr>
			<th>query</th>
			<td>The keywords that will be used to find matching job listings. This is required if region or locality are not provided.</td>
			<td>String(Required)</td>
		</tr>
		<tr>
			<th>region</th>
			<td>The state name or abbreviation used to filter jobs listings. This is required if query or locality are not provided.</td>
			<td>String</td>
		</tr>
		<tr>
			<th>locality</th>
			<td>The city name used to filter job listings. This is required if query or region are not provided.</td>
			<td>String</td>
		</tr>
		<tr>
			<th>skipCount</th>
			<td>The number of records to skip ahead from the first record. Valid range of 1-99.</td>
			<td>int (Required)</td>
		</tr>
	</tbody>
</table>
<h3>Lookup Codes</h3>

<p><label><a id="formatcodes"></a>Format Codes:</label><br />
json ( Default )<br />
xml<br />
atom</p>
