## Description

The application you will be building is a kind of a job board, where anyone can create an account and apply
to vacancies.

1. Account creation
2. Sign in
3. Log out
4. Profile Edition(consider profile pic attachment)
5. Apply to vacancy
6. Add skills to my profile
7. Vacancy search(by company, by skills)

## As a User I can create an account

### Why

**As a User**
**I want to create an account**
**So that I can search for vacancies**

### Acceptance Criteria

```gherkin
Scenario: User Sign Up
Given I'm on the root of the page
When I click on the "Sign Up" button
And fill the email field with "example@sample.io"
And I fill the password field with "123456"
Than I should see a Sign out link
```

## As a User I can login in the system

### Why

**As a User**
**I want to sign in**
**So that I can search for vacancies and apply to any of them**

### Acceptance Criteria

```gherkin
Scenario: User Sign In
Given I'm on the root of the page
When I click on the "Sign In" button
And I fill the email with 'example@sample.io'
And I fill the password with '123456'
Then I should see a Sign out link
```

## As a User I can log out in the system

### Why

**As a User**
**I want to sign out**
**So that I cannot apply to any vacancy**

### Acceptance Criteria

```gherkin
Scenario: User Sign Out
Given I'm logged in
When I click on the "Sign out" link
Then I should see a "Goodbye" message
```

## As a User I edit my personal details

### Why

**As a User**
**I want to update my personal details**
**So that I have a better profile on the platform**

### Acceptance Criteria

```gherkin
Scenario: Edit Personal Details
Given I'm logged in as "example@sample.io"
When I click on the "Edit profile" link on the navigation bar
And I attach a profile picture
And I fill in the name with 'John'
And I fill in the last name with 'Wick'
And I fill in the birthdate with '1964-10-12'
And I fill in the bio with 'A ninja developer, hihgly skilled, hired to refactor the most dangerous code, the world has ever seen'
And I click the "Save" button
Then I should see a "Profile updated successfully" message
```

## As a User I apply to a vacancy

### Why

**As a User**
**I want to apply to a vacancy**
**So that I can follow up**

### Acceptance Criteria

```gherkin
Scenario: User applies to vacancy
Given I'm logged in as "example@sample.io"
When I click on the "Vacancies" link on the navigation bar
And I click on the one titled "Ruby on Rails Full Stack Developer"
Then I should see the vacancy description
And I should see the vacancy title
And I should see the vacancy required skills
And I click on the 'Apply' button
Then I should see a "You applied to Ruby on Rails Full Stack Developer successfully" message
```

## As a User I can add skills to my profile

### Why

**As a User**
**I want to add skills to my profile**
**So that I can see my skills on my profile**

### Acceptance Criteria

```gherkin
Scenario: User add skills to his/her profile
Given I'm logged in as "example@sample.io"
When I click on the "Skillset" link on the navigation bar
And I fill in the "Skill name" with "Ruby"
And I fill in the "Years" with 4
And I click on the "Add another skill" button
And I fill in the "Skill name" with "Javascript"
And I fill in the "Years" with 3
And I click on the "Save" button
Then I should see a "Skills added successfully" message
And I should see the added skills under the skillset section
And I should see my full name
And I should see my bio
```

## As a User I can filter vacancies

### Why

**As a User**
**I want to filter vacancies by title or skills**
**So that I can apply to the ones more suitable for myself**

### Acceptance Criteria

```gherkin
Scenario: User filter vacancies
Given I'm logged in as "example@sample.io"
When I click on the "Vacancies" link on the navigation bar
When I fill in the "Search" field with "ruby"
And I click on the "Search" button
Then I should see the vacancies with "ruby" on the title or as a skill
```

**Development Notes:**

- The search method should filter vacancies ignoring the case of the search keyword
