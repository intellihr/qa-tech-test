# Tech test for QA applicants

As part of the hiring process, we ask you to demonstrate some skills with automation by producing a test suite that automates a series of user workflows.  You should also include any tests that you believe would be relevant but are not covered below, however focus on the objective of the user story and what it is trying to verify.

Please cover as many user stories as you can, whilst maintaining good readability and reusable codes. It's better you have a functional automated test suite rather than a framework with only 1 or 2 automated tests.

**Requirements**:

- We request that you use a JavaScript automation framework (ideally Typescript). intelliHR uses [Cypress](https://docs.cypress.io/guides/getting-started/installing-cypress.html#System-requirements).
- Please respond to this assessment with a code package, preferably hosted in a git repository.
- Automated tests should running in headless mode
- Automated tests should be executable by a single command (eg. yarn run test-intelliHR).

Spend no more than 4 hours on this assessment.  It is not intended that you achieve 100% coverage in this time period. We would like to see what you can do in 4 hours time.

**Note:  UAT environment is reset daily, do not expect data to persist.**

**Note:  Account credentials for the tenant will be provided to you separately.**

Bonus points (if you have capacities to do all of these, you are more than welcome to show us your skills and experience): 

- Code is clean and easy to read.
- Functions that are repeated are stored in a helper file and referenced as necessary
- Language is in TypeScript
- Helper files are constructed in Page Object Model style
- Failed tests are retried a few times before failing
- Documentation and comments as required
- Tests can be retried multiple time without failing


### User Story #1  - Easy

```
As an anonymous User
When I visit https://www.intellihr.com
Then I should see the intelliHR public homepage
Verify intelliHR logo is visible
```

### User Story #2 - Medium

```
As an anonymous User
When I visit https://www.intellihr.com
Then I can find a link to 'Careers'
When I click this link
Then I am taken to the Careers page
Then I click on the "Quality Engineer" career link
Then I click on the "Apply Now" button to open the relevant SEEK page
Verify content of "The Role" is visible
```

### User Story #3 - Easy

```
As a non-logged in user
When I visit <tenant>/spa/settings
Then I should see the login page <tenant>/auth/login
Verify username and password fields are visible
```

### User Story #4 - Medium

```
As an authenticated user <normal user>
When I visit <tenant>/auth/login
Then I should see the login page
When I login with the correct credentials
Then I should see the dashboard
Verify h1 which contains greeting is visible (eg. Good Morning, <name>)
```

### User Story #5 - Hard

```
As an authenticated user <Manager>
When I visit <tenant>/spa/settings/skills
Then I press 'Create Skill' button
Then I enter all of the mandatory data
Then I press 'Save' button
Then I see 1 newly Skill listed

Then I create a new skill once again
Then I see 2 Skills listed
When I select the kebab menu for the second skill
Then I select 'Delete' option
Then I confirm, by selecting the 'Delete' option
Verify out of the 2 skills created, only the first skill is listed

```

### User Story #6 - Easy

```
As an unauthenticated user <normal user>
When I visit <tenant>/configuration/edit
Then I should see the login page
When I login with the correct credentials
Then I should see 'Page Not Found'
Verify a sad intelliman image is visible
```

### User Story #7 - Medium

```
As an authenticated user <Manager>
When I visit my profile page (left-hand side)
Then I should see a 'Job' tab
When I click on that tab
Then I should see 'Remuneration Schedule' section
Then I select "Show Content" button within the 'Remuneration Schedule' section
Verify that a salary figure is visible
```

### User Story #8 - Very Hard

```
As an authenticated user <Admin>
When I select People link from the left-hand side
Then I should see People page
When I input "Lyanna" into the Search field
Then I should I see "Lyanna" as the only result
When I select "Lyanna"
Then I should see Lyanna's Profile Page
When I scroll down to 'Email Address' section
Then I should see that the second email entry (demo@intellihr.com.au) has the tag 'Personal'

Then I click the kebab button on the second email entry
Then I should see 'Edit' and 'Delete' option
Then I select 'Edit' option
Then I select Work Email Address radio button
Then I press the Save button
Then I am returned to the profile page
Verify the second email entry (demo@intellihr.com.au) now has the tag 'Work'
```

### User Story #9 - Easy

```
As an authenticated user <Admin>
When I select People link from the left-hand side
Then I should see People page
When I input "Lyanna" into the Search field
Then I should I see "Lyanna" as the only result
When I select "Lyanna"
Then I should see Lyanna's Profile Page

Then I select 'Job' tab
Then I should 'Reporting' section
Verify that Thomas Mason is shown under 'Direct Reports'
```

### User Story #10 - Medium

```
As an authenticated Admin (<Admin>)
When I visit People page
Then I Click on 'Export People' button
I can download a csv file and it is saved into <downloads> folder
```
