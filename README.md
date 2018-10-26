# javascriptfun
This is a simple converter util in JS which formats Application SQL queries from ORACLE, SQL server to actual database queries removing unnecessary text and characters, to avoid manually editing stuff in SQL editor.

Please refer to the image file in the project. 

So we have the convert button and you can choose the database type Oracle or Sqlserver primarily to differentiate between the dates which get passed

For sqlserver we might have the date as contractversion0.validfrom <= '2017-07-31 00:00:00'

whereas for Oracle we might need contractversion0.validfrom <= to_date('2017-07-31 00:00:00','YYYY-MM-DD HH24:MI:SS')

 
paste the two lines from the logs which have the query as well as the input argument for the query e.g.

Sample , ugly Query from the logs which cannot be directly run in any SQL editor. The idea is to beautify, format the query so it is sql editor ready

01002907 INFO [20170424 09:31:41] - 01475 SofAncestorBo.getData: executing SELECT contractversion0.contractversion_id, contractversion0.versionnumber, contractversion0.description, contractversion0.validfrom, contractversion0.validto, contractversion0.isrelevant, contractversion0.isfrozen, contractversion0.billingenddate, contractversion0.retroactivecalc, contractversion0.paymentcommunication, contractversion0.timestamp, contractversion0.userAccount_id, contractversion0.generalagreement_id, contractversion0.contract_id, contractversion0.precedingVersion_id, contractversion0.mergedversion_id, contractversion0.quote_id, contractversion0.customer_id, contractversion0.invoiceContact_id, contractversion0.payingBankaccount_id, contractversion0.receivingBankaccount_id, contractversion0.invoiceCurrency_id, contractversion0.financialCustomer_id, contractversion0.reliefpool_id FROM contractversion contractversion0 WHERE contractversion0.contract_id = ? AND contractversion0.validfrom <= ? AND contractversion0.validto > ?01002907 INFO [20170424 09:31:41] - 01475 SofAncestorBo.getData: with args 1000221, 2017-07-31 00:00:00, 2017-07-31 00:00:00


and hit convert button and boom the right text area will get populated and you can directly run that in your database client. Please use this and let me know if there are any issues , might come handy while debugging.

So what are you waiting for, download  ParseSQL.html and give it a go.

 

NOTE:- Though , I have done some initial testing, there might be some corner cases which could give some tricky results. Its always good to do a cursory review for the SQL generated.
