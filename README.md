[![Build Status](https://travis-ci.org/freiheit-com/fdc-test-statistics.svg?branch=master)](https://travis-ci.org/freiheit-com/fdc-test-statistics)

#REST-API:

## Store coverage data:

    curl -X PUT http://<servername>:10000/data/coverage -d '{"lines": <n>, "covered": <m>, "project": "<project-name>", "subproject": "<subproject-name>", "language": "<language>"}' -H "Content-Type: application/json"

Only the last PUT of the day is remembered by the statistic server.


## Get latest coverage data:
    
    curl http://<servername>:10000/statistics/coverage/latest/<project-name>

Gives you the most recent coverage data for project `<project-name>`. Looks back at most 30 days.
Aggregates coverage data over all subprojects and languages in `<project-name>`.