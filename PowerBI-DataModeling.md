
<b>Data Modeling with Power BI and Power Query</b>
<p>Power BI provides PowerQuery to apply transforamtions 
(for nice and clean i.e., the data in suitable state for reporting before we start buidling a 
visualizations). Power query essentially allows us to do a whole bunnch of data modeling and we can see 
lot of feature and functions up in the ribbon (Power query Editor).
</p>

<p>
2 ways to reduce Power BI dataset size and speed up refresh
<p> Power BI Dataset size Reduction Tips</p>
      <p>
      On Power BI Desktop we can select an option in View tab: 
      Select "Performance Analyzer" this should be your first step, open the Power BI report which you want to 
      look the performance, it shows good analysis with how much time taken for DAX Query/VisualDisplay/Others, it dispalys for each control
      on power bi report, is taking longer time.
      </p>
      Some times the issue with the "Refresh", refresh get slow, we can see ther refresh history Power BI Service,
      for example refresh might take 1 hr. If report Refresh is taking time or visualization taking time lot of times its a MODEL OPTIMIZATION option
      OR Optimizing the DAX itself or VertiPaqAnalyzer (https://www.sqlbi.com/tools/vertipaq-analyzer/)
      <b> You can download DAX Studio form SQLBI.COM</b>
      <b>Remove Unneeded columns</b> Do not pull those columns which are not used. Then check the power bi file size its drastically reduced after removing unnecessary columns. Even you can check the Refresh history in Power BI Service, there check the load time (start/end).
      Vertipaq Analyzier (Veripaq Engine Aalyzer): It shows each table size, and cardinaltiy/TotlaTbalsize/Columntotalsize/Data size/Dictionary size/Column Hierarchy size/user hierarchhy size/...etc. 
      First go with high cardinality table, if you expand that table we can see the each column cardinality. Pick the columns which are having high cardinality, try to remove those columns. When can we remove? if we are not using any where in the Report/ and in model there is no relation defined on coluns.
</p>
https://docs.microsoft.com/en-us/power-bi/guidance/import-modeling-data-reduction
<p>
<p> Power BI Desktop - File - Options - Uncheck Auto date/time under Time Intelligence 
same this we can do at File level and Global level i.e., applies all the BI files

We can unchek it, but what is the advantage of having this option "Auto date/time"?
Roughly: Automatically creates hierarchies  
</p>
<b> Data Modeling best practices:<b/>
      
      
Avoid Wide tables
------------------
	As data volumes grow performance can start to suffer due to longer scans/reads.
	It misuses Memory, your model gets big and it uses more memory


What if some one asks to introduce another table and i wanted to correalte values across those two table (with existig table)?

Correlate one single wide table to another wide table (internetsales/resellerSales), as there is no relation it just does cartesion product so the report
does not show properly.

How can we solve this problem?
We have to create relation between these two wide tables. If we see them we are comparing with 
ProductKey
-----------
then try to create realtion, but it shows waring saying it is MANY-MANY relations (we shoudl totally avoid many-many relations), but any how 
we can create relation, it creates bi-directional relation.

but also i want to create relation with SalesterritorrKey
--------------------
This time it creates an inactive relations (with dotted lines where as the first was a line). how do you gonna handle that?
Some another complexcity added to the model, DAX is gonna be complex and now your performace is surely affetected.

first point is, try to avoid wide tables, for all the above reasons.

Nex point is, you shoudl really focused narrow tables, these are called as STAR schema.

Example:
Will split into fact/dimension tables, Product_dim, f_internetsales, f_resellerSales. STAR Schema is optimized for reporting. With those three tables and having the relation (internetsales <- Product -> ResellerSales, both tables are having one-many relation with Prodcut_Dim). Now if we use this new model in our report then the visualization woudl be good i.e., meaningful.

What happend if there is relation between two tables and trying to correlate them in a report? Why it does show wrong chart?
Why we have to avoid Many-many relations?
What is inactive relation? How it works? any advatages/disadvantages?      
</p>
