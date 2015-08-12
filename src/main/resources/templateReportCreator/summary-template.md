<% def stats = com.athaydes.spockframework.report.util.Utils.aggregateStats( data )
 %># Specification run results

## Specifications summary

<small>Created on ${new Date()} by ${System.properties['user.name']}</small>

| Total          | Passed          | Failed          | Feature failures | Feature errors   | Success rate        | Total time (ms) |
|----------------|-----------------|-----------------|------------------|------------------|---------------------|-----------------|
| ${stats.total} | ${stats.passed} | ${stats.failed} | ${stats.fFails}  | ${stats.fErrors} | ${stats.successRate}| ${stats.time}   |

## Specifications


|Name  | Features | Failed | Errors | Skipped | Success rate | Time |
|------|----------|--------|--------|---------|--------------|------|
<% data.each { name, map ->
 %>| $name | ${map.totalRuns} | ${map.failures} | ${map.errors} | ${map.skipped} | ${map.successRate} | ${map.time} |
<% }
 %>

<small>Generated by <a href="<%out << com.athaydes.spockframework.report.SpockReportExtension.PROJECT_URL%>">Athaydes Spock Reports</a></small>