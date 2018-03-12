# jira-estimates-calculator

Provides the functionality to execute a search for issues in JIRA based on a given JQL search query and returns the sum 
of the remaining estimates of the resulting issues.

## Requirements

- Java 8

## How to Run

Replace the values of parameters `uri`, `username`, and `password` in method 
`de.phib.jira.JiraEstimatesCalculatorTest.setupTests` with the connection details for your JIRA instance.

```
@BeforeAll
public static void setupTests() {
    jiraEstimatesCalculator = new JiraEstimatesCalculator("http://example.com", "jirauser", "secret");
}
```

Replace the value of parameter `jql` in method 
`de.phib.jira.JiraEstimatesCalculatorTest.testCalculateRemainingEstimates` with your search query.

```
@Test
public void testCalculateRemainingEstimates() {
    int estimates = jiraEstimatesCalculator.calculateRemainingEstimates("project = DEMO");

    Assertions.assertTrue(estimates > -1);
}
```

Then run the unit test `de.phib.jira.JiraEstimatesCalculatorTest.testCalculateRemainingEstimates`.

## License

[MIT](LICENSE)

## Author Information

Created by [Philippe Boessling](https://www.gihub.com/pboessling).