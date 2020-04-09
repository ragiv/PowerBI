
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
      OR Optimizing the DAX itself or VertiPaqAnalyzer
      <b> You can download DAX Studio form SQLBI.COM</b>
</p>
<p>
<p> Power BI Desktop - File - Options - Uncheck Auto date/time under Time Intelligence 
same this we can do at File level and Global level i.e., applies all the BI files

We can unchek it, but what is the advantage of having this option "Auto date/time"?
Roughly: Automatically creates hierarchies  
</p>
<b> Data Modeling best practices:<b/>
</p>
