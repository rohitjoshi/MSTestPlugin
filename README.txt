
1. When UnitTestResult in trx file doesn't have 'outcome' attribute, it doesn't process and doesn' reporte as an error.
2. When UnitTestResult in trx file doesn't have 'duration' attribute, it reports value as 'NaN' which causes summary time to be 0.

Eg. Below unit test is treated as a success in MSTest report but it is treated as an error in MSTest trx file.

<UnitTestResult executionId="70be9f02-00a0-49df-8c5a-8fb84a74b210" testId="44861a89-0ac6-f405-4b04-99f6f9d85d1e" testName="HasTargetTest" computerName="xxx-LT" startTime="2012-05-22T14:32:34.3525653-04:00" endTime="2012-05-22T14:32:41.9625760-04:00" testType="13cdc9d9-ddb5-4fa4-a97d-d965ccfc6d4b" testListId="8c84fa94-04c1-424b-9868-57a2d4851a1d" relativeResultsDirectory="70be9f02-00a0-49df-8c5a-8fb84a74b210">
<Output>
<ErrorInfo>
<Message>The agent process was stopped while the test was running.</Message>
</ErrorInfo>
</Output>
</UnitTestResult>

To fix the issue,
Copy 'mstest-to-junit.xls' to $Jenkins_home\plugins\mstest\WEB-INF\classes\hudson\plugins\mstest directory.