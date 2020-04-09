<b>M Query Language basics</b>
<p><b> M Language means: Data Mashup language </b></p>

What is Query Folding in Power BI
<p>Pushing logic back to the Database server. Server will do lot of work rather than the client-side</p>

<p>Run the profiler and check what is happening when you filter on Power Query editor?
Any transformation logic which you have written/applied in power query, pushes that logic back to source Query language, for example sql server (if we connected to the SQL Server).</p>
 <i>Thsi push backs does not happend when we select "Advance query editor" while connecting to the server.

</i>
 
 <p> To encourage query folding:</p>
  <p>Do not write any queries (T-SQL in case SQL Server) in query editor, it wont do any Query folding means that the transformation happens at the client side.</p>


<b>Why you woudl write M Queries?
        User Cases:
</b>
 <li>
 For Dynamic Queries: If your query needs to be in dynamic then you probably need to write some M. If you want to pass the one query        result to another query.
 
 Create a parameterized Query Function.
 
 </li>
