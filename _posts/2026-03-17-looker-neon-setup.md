---
layout: post
title: "Setting up Looker Studio with AdventureWorks DB at neon.tech"
date: 2026-03-17 09:00:00 -0800
categories: [DataViz]
---

# Hello!
HOWTO: Setting up LookerStudio to use the AdventureWorks db set up at neon.com 

- once logged in in a google account. goto lookerstudio.google.com, 
    - select Blank Report
    - in Connect to data, click PostgreSQL
        
    

- login to neon.com account using github (preferred)
    - select db to use then click Connect to get connection string, copy snippet
           ex. postgresql://neondb_owner:npg_HbTDlU9zefV2@ep-muddy-cherry-aiacm753-pooler.c-4.us-east-1.aws.neon.tech/adventureworks-db?sslmode=require&channel_binding=require



        
- go back to lookerstudio, fill as follows:
    - host name or ip: ep-muddy-cherry-aiacm753-pooler.c-4.us-east-1.aws.neon.tech
    - port: 5432
    - database: adventureworks-db
    - username: neondb_owner
    - password: 
    - click Enable SSL
    - postgresql ssl configuration files: find this file: isrgrootx1.pem
    
    - click Authenticate
    
	<img src="/assets/img/looker-authenticate-success.png" alt="authentication success" width="400">

	
- select Custom Query, enter this:

SELECT 
	h.salesorderid,
	h.orderdate,
	h.duedate,
	h.shipdate,
	h.status,
	h.onlineorderflag,
	h.purchaseordernumber,
	h.accountnumber,
	h.customerid,
	h.salespersonid,
	h.territoryid,
	h.billtoaddressid,
	h.shiptoaddressid,
	h.shipmethodid,
	h.creditcardid,
	h.creditcardapprovalcode,
	h.currencyrateid,
	h.subtotal,
	h.taxamt,
	h.freight,
	h.totaldue,
	d.salesorderdetailid,
	d.carriertrackingnumber,
	d.orderqty,
	d.productid,
	d.unitprice,
	d.unitpricediscount,
	d.orderqty::numeric * d.unitprice * (1::numeric - d.unitpricediscount)::numeric(16,4) AS lineamount,
	p.name AS productname,
	p.productnumber,
	p.productnumber || '-' || p.name "Product_Name",
	p.makeflag,
	p.finishedgoodsflag,
	p.safetystocklevel,
	p.reorderpoint,
	--p.standardcost,
	--pch.standardcost,
	p.listprice,
	p.size,
	p.productsubcategoryid,
	p.discontinueddate,
	pc.name AS "Product_Category",
	--'x' as dummy,
	pcs.name AS "Product_Subcategory",
	t.name AS "Territory_Name",
	t.countryregioncode,
	t."group" AS "Territory_Group",
	c.personid,
	c.storeid,
	c.territoryid AS c_territoryid,
	pe.businessentityid AS customer_id,
	pe.persontype AS cust_type,
	pe.firstname AS cust_firstname,
	pe.lastname AS cust_lastname,
	cast(h.customerid as text) || '-' || pe.lastname || ', ' || pe.firstname "Customer_Name",
	pe2.businessentityid AS salesperson_id,
	pe2.persontype AS sp_type,
	pe2.firstname AS sp_firstname,
	pe2.lastname AS sp_lastname
FROM sales.salesorderheader h
	JOIN sales.salesorderdetail d ON h.salesorderid = d.salesorderid
	JOIN production.product p ON d.productid = p.productid
	--left join production.productcosthistory pch on (d.productid = pch.productid)	
	JOIN sales.customer c ON c.customerid = h.customerid
	JOIN sales.salesterritory t ON t.territoryid = h.territoryid
	JOIN production.productsubcategory pcs ON p.productsubcategoryid = pcs.productsubcategoryid
	JOIN production.productcategory pc ON pcs.productcategoryid = pc.productcategoryid
	LEFT JOIN person.person pe ON c.personid = pe.businessentityid
	LEFT JOIN person.person pe2 ON h.salespersonid = pe2.businessentityid
;

