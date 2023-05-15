~ ISSUE SUMMARY

From 7:00 AM to 10:30 AM GMT, urgent requests for Full Throttle RC APIs resulted in 500 and 504 error response messages. My company's mobile applications that rely on the aforementioned APIs also returned similar errors. At its peak, the issue affected 80% of traffic to this API infrastructure. Users could continue to access specific APIs that run on separate infrastructures. The root cause of this outage was a syntax error in the SQL queries and wrong file imports.

~ TIMELINE

11:19 AM: Deployment push begins 11:26 AM: Outage begins 11:26 AM: Pagers alerted teams 11:54 AM: Failed configuration change rollback 12:15 PM: Successful configuration change rollback 12:19 PM: Server restarts begin 12:58 PM: 100% of traffic back online

~ ROOT CAUSE

At 11:19 AM PT, a deployment has the newly configured code released into production. The new code pushed has SQL syntax errors, and some files were wrongly imported. Since the errors were not correctly handled in the system, this led to a system-wide breakdown of the entire system. c Resolution and recovery

~ CORRECTIVE AND PREVENTATIVE MEASURES

The errors were fixed by uploading new code to the server with errors fixed. To avoid getting into a similar situation next time: Test code before uploading Use canary deployment Build CI/CD pipelines.
