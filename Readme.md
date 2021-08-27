<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/128546905/13.1.4%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/E438)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
<!-- default badges end -->
<!-- default file list -->
*Files to look at*:

* [SchedulerData.cs](./CS/WebSite/App_Code/SchedulerData.cs) (VB: [SchedulerData.vb](./VB/WebSite/App_Code/SchedulerData.vb))
* [Default.aspx](./CS/WebSite/Default.aspx) (VB: [Default.aspx](./VB/WebSite/Default.aspx))
* [Default.aspx.cs](./CS/WebSite/Default.aspx.cs) (VB: [Default.aspx.vb](./VB/WebSite/Default.aspx.vb))
<!-- default file list end -->
# How to get appointment information using non-visual control


<p>Problem:</p><p>How can I display information about selected appointments on a new page? I'd like to pass the appointment ID and then retrieve the necessary information not showing the scheduler to the end-user on the client side. The problem is with the elements of the recurrence chain - they are not present in the database.</p><p>Solution:</p><p>You can obtain appointment info directly from a database. Although you cannot bypass the ASPxScheduler, a non-visual control suffices to operate scheduler objects and API. </p><p>The input appointment ID is an integer, which may be followed by an underscore and a number, signifying that this is an appointment occurrence whose occurrence index equals to that number.</p><p>The example implements the AppointmentSearchHelper class to perform a search by iterating through appointments contained within a storage. When necessary, a pattern is expanded to calculate the appointment occurrences chain.</p><p>Performance tips:<br />
1)  Navigation buttons visibility. Recalculation of target appointments takes too much time. Make buttons invisible to speed up the loop.<br />
2) Reduce the number of appointments in the storage. To accomplish this, modify the query used by a data source to retrieve data.</p>

<br/>


