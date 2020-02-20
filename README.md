This is a tool for pulling USQL data from the Dynatrace API

It uses a simple GUI for users to insert their queries and report on the results of those queries.
The data is output to a table and in a json format

![Image of GUI](https://i.imgur.com/5PGxXCW.png)



![Image of GUI Table](https://i.imgur.com/DUj8XCA.png)



![Image of GUI Json](https://i.imgur.com/s0kfmoM.png)

Typically when an API call is made in Dynatrace it will be returned with extrapolated data because the amount of data being queried is too large.
This tool will check the extrapolation level and split the main query into smaller time periods to get more accurate data.

This currentlly should work in situations where users are querying for
- Maximum values
- Minimum values
- Sums
- counts

All other values returned will be extrapolated as normal though. At this point I believe the extrapolated data would likely be more accurate for Average, and median aggregations

I may start to account for other aggregations in the future, but just getting this tool to its current state was enough to satisfy me for now.

Currently has been tested with Dynatrace version 1.186 but should still work with most other versions that allow for USQL api calls
This tool is currently querying the endpoint: "api/v1/userSessionQueryLanguage/table"