---
layout: post
title: "psql dump to Neon"
date: 2026-03-15 09:00:00 -0800
categories: [General]
---

# Hello!
I am hosting this using my custom domain **miracleostrich.ca**.

#### HOWTO: Using a PostgreSQL dump sql to create a new db source in neon.com

1. Create a project (db) in neon.com

   Get the connection string "postgresql://...."

2. Using powershell

   psql -d "postgresql://neondb_owner:****************@ep-floral-credit-ad9os99j-pooler.c-2.us-east-1.aws.neon.tech/neondb?sslmode=require" -f "c:\hp\miracleostrich\adventure_works_dump.sql"

3. After the .sql is executed, test:

   Use sql editor on the project (db) created
 
   Ex. select * from sales.salesorderdetail limit 5;

<img src="/assets/img/testing-neondb.png" alt="neondb using dump.sql" width="400">
