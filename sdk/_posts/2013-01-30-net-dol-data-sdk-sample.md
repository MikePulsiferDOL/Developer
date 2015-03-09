---
layout: post
title: ".Net DOL Data SDK Sample"
created: 1359561327
---

<h2>Overview</h2>

<p>This sample will provide the steps to create a simple Dot Net web application that can consume DOL Data or DOL Service Operation (Beta Version). Following these steps in order will allow your application to operate correctly.<br />
&nbsp;</p>

<p>This solution was built using:</p>

<ul>
	<li>Microsoft's Visual Studio 2010</li>
	<li><a href="http://www.dol.gov/cgi-bin/leave-dol.asp?exiturl=http://www.microsoft.com/download/en/details.aspx?id=17851&amp;exitTitle=.Net Framework 4.0&amp;fedpage=no">.Net Framework 4.0</a></li>
	<li>MVC3 ( for Service Data Operation)</li>
</ul>

<p>&nbsp;</p>

<p>&nbsp;</p>

<h2>Create a New Project</h2>

<p>&nbsp;</p>

<p>For this sample we are going to create a web site that will consume and list Agency data.<br />
<br />
<img alt="New Project" src="/sites/default/files/opa.developer.sdk.dotnet.NewProject.png" style="width: 60%; " /><br />
<br />
Select the default ASP.NET Web Site and confirm web site details in the project setup page for DOL Data.<br />
<br />
<img alt="Project Details" src="/sites/default/files/opa.developer.sdk.dotnet.AspNetWebSite.png" style="width: 60%; " /></p>

<p>&nbsp;</p>

<p>Select the ASP.NET MVC3 Web Application and confirm web site details in the project setup page for DOL Service Operation (Beta Version).<br />
<br />
<img alt="Project Details" src="/sites/default/files/opa.developer.sdk.dotnet.V2NewProject.png" /></p>

<p>&nbsp;</p>

<p>&nbsp;</p>

<h2>Add SDK to Project</h2>

<p>&nbsp;</p>

<p>All request require account credentials to be submitted along with the request. The SDK was designed to manage this and can be downloaded at one of these two locations:</p>

<ul>
	<li><a href="http://developer.dol.gov/sdks/DotNet_DOLDataSDK.zip">Zip file download</a></li>
	<li><a href="http://www.dol.gov/cgi-bin/leave-dol.asp?exiturl=https://github.com/USDepartmentofLabor/DotNet_DOLDataSDK&amp;exitTitle=GitHub&amp;fedpage=no">GitHub Repository</a></li>
</ul>

<p>This SDK contains a <strong>DOLDataUtil</strong> class which is in <strong>DOLDataUtil.cs</strong>. This file needs to be included into your solution. For this demo <strong>DOLDataUtil.cs</strong> will be placed in the App_Code folder.<br />
<br />
<!--
Secure logins are provided by the SDK, which can be downloaded <a href="http://developer.dol.gov/sdks/DotNet_DOLDataSDK.zip">here</a>.
  Including the <strong>DOLDataUtil.cs</strong> file into your project will allow access to all DOL Data Feeds for your applications.  
  This file will be placed in the App_Code folder for this demo.<br><br>
--> <img alt="Add SDK File" src="/sites/default/files/opa.developer.sdk.dotnet.AddSdkFile.png" style="width: 40%; " /></p>

<p>&nbsp;</p>

<p>Add SDK to Project for DOL Service Operation (Beta Version)</p>

<p><img alt="Add SDK File" src="/sites/default/files/opa.developer.sdk.dotnet.AddSdk.png" /></p>

<p>&nbsp;</p>

<h2>Locate the Dataset Path</h2>

<p>&nbsp;</p>

<p>Each Dataset has a Dataset Location path that gives the URL that will be needed to reach the Dataset on the API. For the standard DOL Agency dataset sample please use <a>http://api.dol.gov/V1/DOLAgency</a><br />
<br />
<img alt="Add Service Reference" src="/sites/default/files/opa.developer.sdk.dotnet.DatasetLocation.png" style="width: 60%; " /></p>

<p>For the DOL Service Operation sample please use <a>http://api.dol.gov/V1/SummerJobs</a><br />
<br />
<img alt="Add Service Reference" src="/sites/default/files/opa.developer.sdk.dotnet.ServicePath.png" /></p>

<h2>Add Service Reference to Project</h2>

<p>This path is used by the <strong>Add Service Reference</strong> Tool within visual studios.<br />
<br />
<img alt="Add Service Reference" src="/sites/default/files/opa.developer.sdk.dotnet.AddServiceReference.png" /></p>

<p>&nbsp;</p>

<p>Enter the Dataset Location Path into the Address and select the service from the list.<br />
<br />
<img alt="Add Service Reference" src="/sites/default/files/opa.developer.sdk.dotnet.ServiceReferenceWithPath.png" style="width: 60%; " /></p>

<p>&nbsp;</p>

<p>&nbsp;</p>

<p>Enter the Dataset Location Path into the Address and select the service from the list for DOL Service Operation (Beta Version).<br />
<br />
<img alt="Add Service Reference" src="/sites/default/files/opa.developer.sdk.dotnet.AddReference.png" /></p>

<p>&nbsp;</p>

<p>&nbsp;</p>

<h2>Define the User Interface</h2>

<p>&nbsp;</p>

<p>Add a simple <b>GridView</b> to the <b>Default.aspx</b> page..<br />
&nbsp;</p>

<pre class="prettyprint">
&lt;asp:GridView ID=”AgenciesView” runat=”Server” AutoGenerateColumns=”False”&gt;
	&lt;Columns&gt;
		&lt;asp:BoundField DataField=”Agency” HeaderText=”Agency” /&gt;
		&lt;asp:BoundField DataField=”AgencyFullName” HeaderText=”Agency Full Name” /&gt;
	&lt;/Columns&gt;
&lt;/asp:GridView&gt;</pre>

<p>&nbsp;</p>

<p>For Service Operation</p>

<p>This call return Json data which can be added directly to the view. Add this javascript to the application to inject this JSON directly to the script.<br />
&nbsp;</p>

<pre class="prettyprint">
&lt;script type="text/javascript"&gt;
var jsonData = @Html.Raw(ViewBag.JsonData);

$(document).ready(function () {
	var builder=[];
	for(var i=0; i &lt; jsonData.items.length; i++)
	{
		builder.push("&lt;span&gt;" + " " + jsonData.items[i].title + "&lt;/span&gt;&lt;br/&gt;");
	}
	
	$('p').html(builder.join(''));
});
&lt;/script&gt;</pre>

<p>&nbsp;</p>

<p>&nbsp;</p>

<h2>Implementing the DOL Data Request</h2>

<p>&nbsp;</p>

<p>Include Using statements to reference the appropriate classes.<br />
&nbsp;</p>

<pre class="prettyprint">
using System.Data.Services.Client;
using gov.dol.doldata.util;
using ServiceReference1;</pre>

<p>&nbsp;</p>

<p>&nbsp;</p>

<p>&nbsp;</p>

<p>Create and instance of the FormsEntity using the <strong>Dataset Location path</strong> found for the feed referenced by your Service Reference.<br />
Wire the <strong>DOLDataUtil.service_SendingRequest</strong> static method to the <strong>entity.SendingRequest</strong> event handler.<br />
&nbsp;</p>

<pre class="prettyprint">
protected void Page_Load(object sender, EventArgs e)
{
	AgencyEntities entity = new AgencyEntities(new Uri(“<a>http://api.dol.gov/V1/DOLAgency</a>”));
	entity.SendingRequest += new EventHandler&lt;SendingRequestEventArgs&gt;(DOLDataUtil.service_SendingRequest);
	AgenciesView.DataSource = entity.Agencies;
	AgenciesView.DataBind();
}</pre>

<p>&nbsp;</p>

<p>&nbsp;</p>

<p>Implementing the DOL Data Request for Service Operation</p>

<p>&nbsp;</p>

<p>&nbsp;</p>

<pre class="prettyprint">
public ActionResult Index()
{
	ViewBag.Message = "Welcome to ASP.NET MVC!";
	SummerJobsCall proxy = new SummerJobsCall(new Uri("<A>http://api.dol.gov/V1/SummerJobs</A>"));
	proxy.SendingRequest += new EventHandler&lt;System.Data.Services.Client.SendingRequestEventArgs&gt;
		(gov.dol.doldata.util.DOLDataUtil.service_SendingRequest);
		
	string jsonData = proxy.Execute&lt;string&gt;(
		new Uri("getJobsListing?format=json&amp;region=&amp;locality=&amp;zip=&amp;employmentType=%27Any%27SkipCount=1&amp;query=%27Nurse%27", UriKind.Relative)
		).FirstOrDefault().Replace("\\n", "").Replace("\\\"", "\"").Trim('\"');
		
	return View();
}
</pre>

<h2>Configure Security</h2>

<p>Once the SDK has been added to the project, we will need to modify both the <strong>ApiKey</strong> and the <strong>SharedSecret</strong> members of this class to access DOL Data.<br />
Edit the <strong>DOLDataUtil class</strong> within the <strong>DOLDataUtil.cs</strong> file.</p>

<ul>
	<li>The <strong>ApiKey</strong> corresponds to the <strong>Token</strong> identifier in your token list.</li>
	<li>The <strong>SharedSecret</strong> created during setup is the same value that is used in the DOLDataUtil class.</li>
	<li><sup>*</sup>Note: <strong>DOLDataUtil Class</strong> may be inaccessable due to its current access specifier. Precede with public keyword to resolve this problem.</li>
</ul>

<p>&nbsp;</p>

<pre class="prettyprint">
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Security.Cryptography;
using System.Data.Services.Client;

namespace gov.dol.doldata.util
{
	public static class DOLDataUtil
	{
		//Define API Key and Shared Secret
		private const string ApiKey = "ADD YOUR API KEY";
		private const string SharedSecret = "ADD YOUR SHARED SECRET";</pre>

<p>&nbsp;</p>

<p>&nbsp;</p>

<h2>Run the Application</h2>

<p>&nbsp;</p>

<p>Run the application and you should see a list of agencies in the grid.<br />
<br />
<img alt="Implement code" src="/sites/default/files/opa.developer.sdk.dotnet.data.png" style="width: 60%; " /></p>

<p>Run the application for Service Operation and you should see a list of job titles.<br />
<br />
<img alt="Implement code" src="/sites/default/files/opa.developer.sdk.dotnet.sodata.png" style="width: 60%; " /></p>
