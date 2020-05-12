This is a branch for Supporting Oracle 10g/11g

For the original verison is using HMAC_SH256,HMAC_SH384, HMAC_SH512 of DBMS_CRYPTO package which does not support before Oracle 12.  I have modified some lines in package body by using OOS_UTIL instead 

Of course, you need to install the OOS_UTIL https://github.com/OraOpenSource/oos-utils/blob/master/install/oos_utils_install.sql

Actually, just run @https://observant-message.glitch.me/oos-utils/latest/oos_utils_install.sql; 

= jwt_ninja
Morten Egan <morten@plsql.ninja>

== Summary

This is a PLSQL implementation of JWT (JSON Web Tokens) as defined in https://tools.ietf.org/html/rfc7519[RFC7519]

== Pre-requisites

The following privileges are needed in the schema installing this package:

* grant create procedure to <schemaname>
* grant execute on dbms_crypto to <schemaname>

== Installation

To install the package simply run the the following 2 sql files as the schema owner of the package in sqlplus:

SQL> @jwt_ninja.package.sql

Package created.

SQL> @"jwt_ninja.package body.sql"

Package body created.

SQL>

== Procedures and Functions

* jwt_generate

== Examples

For a detailed demo of this package, please see my blog entries on the package on my http://www.codemonth.dk/code_is_good/dev_qa_prod.assert?condition=codemonth:::17:[Codemonth website]
