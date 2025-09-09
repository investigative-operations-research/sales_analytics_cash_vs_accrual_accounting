# sales_analytics_cash_vs_accrual_accounting

The Business ask

 

Sales and finance were running various promotional strategies in conjunction with products and marketing teams but were trying to unpick what the drivers were to attribute costs and value towards a basis for calculating ROI.

 

BREAKTHROUGH BLIND SPOT --- The accounting basis was using the accrual method which was done for revenue reporting and sales dashboard, which in itself is completely unremarkable in accounting. However, from my previous studies in accounting, it made me wonder if there was a gap based on this accounting method vs. cash. This proved to be a pivotal insight that helped with the root cause analysis when we considered sales and revenue on a cash basis which highlighted several loop holes being exploited causing revenue leakage - we will return to this concept under the heading of "Secure product design" below.

 

I mapped out the customer journey from buying a SIM card to activating it including retail sales channels through to a brief decription of the CRM, billing and ERP systems included along the way to activation of the SIM to give us the technical frame of reference to understand the journey in context to also highlight some of the data and business knowledge gaps that had blocked previous attempts at reporting here.

 

 

 

 

I then did detailed sub-process maps BPMN-style for each of the above components which allowed me to also develop a data governance framework and highlighted several data gaps that required some data engineering pipelines and SQL table development work to enable the data science side of things.

 
Overcoming obstacles

Once the process flows were modelled in this way, I was able to then create the core data tables for reporting and analysis using SQL.

 

This also required several nested queries to both clean and join data which required data discovery and auditing to match a sale to a completed order.

 

It was found that there was a lack of linking ID to complete the chain of order to activation, so presented that solution to the platforms team to fix in future sprints.

 

In the meantime, in speaking with the O2A teams and doing my own analysis for reference, I found that around 95% of the orders were activated within 14 days - so I presented back to the finance team the situation and said I can create a historical view going back 3 years but it will be a proballistic model - they approved that and I created a synthetic link to do the matching end-to-end.
 
The results

 

Based on this I was able to then present the initial key report that was asked for to show how different sales promotions worked in the market.

 

Cohort modelling showed very quickly what promotions and products were winners and losers historically, while also being repeatable for future use where these report were sought for monthly planning and update sessions between sales and finance as a regular cadance.

 

Report highlights:

 
* Per product/promotion drill downs
* P&L of a given product/promotion
* Lifetime value of a customer
* Total sales, revenue and cancellations
* Churn predictions using logistic regression to predict churn 30 days ahead

 
Further applications

 

1) SECURE PRODUCT DESIGN: The P&L figures lead to a further analysis were I found that due to the way some offers were designed, it provided a loophole for several customers who figured out they could game the system with a certain offer that allowed customers to buy a SIM, activate it, get the data allowance and transfer it to another customer, then get a referral credit to pay for more SIM activation and then cancel within the first month before we collected an actual payment from the customer.

 

This showed that some promotions looked great on sales figures and headline revenue, but actual revenue and this security flaw meant that there were a number of promotions that were actually losing up to $500,000 or more which lead to end of year financial discrepancies that the finance team hated reconciling.

 

By doing the data analysis on that as well, I was able to provide evidence for the sales team to ensure that new products and promotions going to market went through some red-team testing conceptually and at the system level to enforce controls to block future vulnerabilities.

 

2) FEATURE ENGINEERING FOR AI: Because I had such a solid understanding of the business processes and data flow, I could create better features which improved detection models of fraud and abusers such as those using the SIM cards as part of sim boxing activities which increased network flow and global interconnection costs that were not being passed back to customers on fixed price unlimited overseas calling offers.
