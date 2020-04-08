# SQL Workshop

This repo contains files for an in-class activity for HUDK 4051: Learning Analytics: Process and Theory. The workshop included a walkthrough on setting
up a free-tier MySQL server using Amazon RDS, then connecting with it and
querying it using `DBI::` and `RMySQL::` in R.

HUDK 4051 is the second of three core courses in the Learning Analytics MS at
Teachers College, Columbia University focusing on the thinking, methods, and
conventions in data science. Particular attention is given to the fields of
Educational Data Mining and Learning Analytics. Refer to the
[Syllabus](https://github.com/timothyLeeXQ/HUDK-4051-Syllabus) (forked from
the [main repo](https://github.com/la-process-and-theory/syllabus) which may
contain updates for future class iterations) for more information on HUDK 4051.

Other classes in the series are:
* [HUDK 4050: Core Methods in Educational Data
Mining](https://github.com/timothyLeeXQ/HUDK-4050-Syllabus)
([Main repo](https://github.com/core-methods-in-edm/syllabus))
* HUDK 5053: Feature Engineering Studio (Starting in May 2020.
 [Main repo](https://github.com/feature-engineering-studio/syllabus))

[Slide Deck](https://github.com/learning-analytics-curriculum-teaching/sql-workshop/blob/master/sql_workshop.pdf)

## Instructor Notes

### Create MySQL Instance on Amazon Web Services

* Log into your [AWS Management Console](https://console.aws.amazon.com)
* Locate `RDS` under the `Databases` heading
* Within Amazon RDS click `Create database`
* Under `Choose a database creation method` click `Standard Create`
* Under `Engine options` choose `MySQL`
* Under `Templates` choose `Free tier`
* Under `Settings` name your `DB instance identifier` as `sqltest`
* Under `Credential settings` create a username and password combination and write it down (you will need it later)
* Under `Connectivity` expand `Additional connectivity configuration` to show additional menu items and make sure that `Publicly accessible` is checked `Yes`
* Expand the `Additional configuration` menu
* Under `Initial database name` write `testdb`
* Uncheck `Automatic backups`
* Click `Create database`

### Modify Security Group

* Under `Security Groups` click `Inbound` and then `Edit`
* Add the rule `SQL/Aurora` on `Port 3306` with the `Connection` of `MyIP`
