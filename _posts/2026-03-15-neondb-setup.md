---
layout: post
title: "psql dump to Neon"
date: 2026-03-15 09:00:00 -0800
categories: [General]
---

# Hello!
I am hosting this using my custom domain **miracleostrich.ca**.


##HOWTO: create a new project (db) in neon.tech

get the connection string "postgresql://...."


using powershell

psql -d "postgresql://neondb_owner:npg_BeT8Wk9cwfnv@ep-floral-credit-ad9os99j-pooler.c-2.us-east-1.aws.neon.tech/neondb?sslmode=require" -f "c:\hp\miracleostrich\adventure_works_dump.sql"


to test:
use sql editor on the project (db) created

ex. select * from sales.salesorderdetail limit 5;



<img src="/assets/img/testing-neondb.png" alt="neondb using dump.sql" width="400">
