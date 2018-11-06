# CICD process

##The Goal

<aside class="warning">
"The ability to deliver features <code>quickly</code> to production with high <code>reliability</code>, <code>frequency</code> and <code>quality</code>"
</aside>

##Definitions
* **CICD**: Continuous Integration / Continuous Delivery (CICD) is a process for providing new functionality to end users by releasing small low risk features frequently and reliably

* **End to End Test**: A functional test which interacts with all of the application's dependencies for that scenario

* **Midway Test**: A functional test which interacts with stubbed endpoints instead of an application's dependencies.

* **Smoke Test**: End to End test which validates critical functionality (show stoppers)

    **Goals**:
    * Validate critical functionality in less than 10 minutes
    * 100% consistent
    * Clear descriptive reporting in the event of a failure
* **Regression Test** :  End to End test which validates all pre-existing functionality.

    **Goals**:
    * Validate functionality in less than 20 minutes
    * 95% consistent
    * Clear descriptive reporting in the event of the failure
* **Unit Test**:  Test which validate a single method of functionality

    **Goals**:
    * 90% coverage of all code
    * 100% Consistent
    * Clear descriptive reporting for coverage, errors, and maintainability
    * Execute tests in less than 30 seconds
* **Web Component**: Custom and reusable UI elements in the browser

    **Goals**:
    * Provide consistent user interaction and look & feel
    * Provide easy to use, well documented, and fully tested components for fast development

* **Component Test**: Test which validates a web component in isolation and in a browser

    **Goals**:
    * Separate the testing of functional stories and web components
    * Validate rendering and functionality inside a browser
    * Clear descriptive reporting in the event of a failure
    * 100% all of components tested with 85% coverage of unit tests
    * Execute all tests in less than 30 seconds
* **Image Diff**: Automated tool which renders a site and creates screenshots

    **Goals**:
    * Create a report to indicate what has visually changed on your website
    * Enable developer to validate intended visual changes and detect unintended changes before released to production

* **[Tripwire](http://blog.questionpro.com/2013/04/29/what-you-didnt-know-about-david-lee-roth-and-tripwires/)**:  A signal which indicates a decision needs to be made before continuing on with the process.


## Guidelines
Guidelines are general principles a team should consider as part of their process. Guidelines are not hard rules and can be overruled.  Teams should consciously overrule a guideline and determine their reasons for doing so.

* **master is Prod Ready**
    * The master branch should always be ready for production
    * If a show stopper defect enters master, roll forward with a fix or revert the commit.

* **Releases are small changes**
    * Releases should be isolated to small feature changes
    * Reduces risk for a single release
    * Releases become routine
    * Allows team to respond quickly to feedback and defects

* **First In First Out**:
    * Features are released in the order they enter the process
    * If feature blocks the process, then it should be removed and start the process again
    * Reduces merge conflicts
    * Clarifies priority of feature testing and delivery

* **Automate**:
   * Automate any tasks that are routine, mundane or does not require human interaction
   * Enables team to focus on more value-add work and decisions
   * Ensures repeatability of tasks (ie: deployments)

* **Keep WIP down**:
   * Work in progress should be reduced to keep team members focused and prevent task switching
   * WIP should be reduced to one feature per workflow step

* **Perfect is the enemy of Good Enough**
   * Team should release features even if they have 'minor' defect
   * Team decides what is a 'minor' defect
   * Iterate over features to improve reliabiliy and address defects

* **Iterate on Process**:
   * Team should identify bottle necks, problematic tasks or other areas of concernin their process
   * Team should experiment with process improvements
   * Team should drop any process or steps which do not add value

* **Clarity & Visibility**:
   * Team should provide an easily accessible report which provides the current state of the project
   * Team should provide an easily accessible report which lists the history of releases and their modifications

* **Release as often as possible**

## Performance Testing

Performance testing is a vital part of maintaining a production application.  In order to ensure performance either improves or remains constant over time, the following features are suggested.

* **Create Thresholds**
   * Team should create thresholds for the application's performance.
   * Thresholds should be validated via reporting and monitoring of the application.
* **Monitor Production**
   * Production should be monitored and metrics should be tracked on each of the production deployments
   * Alerts should be provided to the team when performance of the application falls under a pre-determined threshold
* **Reduce logging impact to users**
   * Monitoring and reporting should impact users as little as possible
   * Leverage asynchronous or 'fire & forget' (ie: UDP network protocol) techniques for tracking performance
* **Measure Perceived Performance**
   * [Perceived performance](http://en.wikipedia.org/wiki/Perceived_performance) is the perfomance of the application as it appears to end users.
   * Track all measurable aspects of your application which impacts users (ie: rendering, visual feedback, etc.)
* **Track over time**
   *  Performance metrics should be recorded and tracked overtime.
   *  Team should review regularly how new features or changes impact performance
* **Communicate with dependant teams**
   * Teams who manage the application's dependencies should receive feedback when latency increases or improves
   * Historical reporting should be provided with the feedback
