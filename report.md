# Report for assignment 4

This is a template for your report. You are free to modify it as needed.
It is not required to use markdown for your report either, but the report
has to be delivered in a standard, cross-platform format.

## Project

Name: Mattermost

URL: https://github.com/mattermost/mattermost-server

Mattermost is an open source, private cloud, Slack-alternative.

## Onboarding experience

Did it build and run as documented?

See the assignment for details; if everything works out of the box,
there is no need to write much here. If the first project(s) you picked
ended up being unsuitable, you can describe the "onboarding experience"
for each project, along with reason(s) why you changed to a different one.

The first project we chose was Strongbox https://github.com/strongbox/strongbox, Strongbox is an OSS artifact repository manager with clear instructions (https://strongbox.github.io/developer-guide/building-the-code.html) on how to build the project. The project uses maven and all one had to do to build the project was to clone the repository and run ´´´mvn clean install´´´ in the local clone. The project has an active community and we were in touch with the developers whom were ready to assist us. In the end the issue proved a bit too complicated and we decided to change project.

The project we ended up working on was Mattermost, an open source and self hosted alternative to the messaging platform Slack. Mattermost has well documented information on how to run their project (https://developers.mattermost.com/contribute/webapp/developer-setup/). There were no trouble in building the project. Just like with Strongbox there was quite an active community, in the Mattermost application itself infact, where you could ask questions and get help in a moments notice. This was used in a couple of instances where we got stuck because of mostly files outside of our issue scope giving us problems.

## UML class diagram and its description

Optional (point 1): Architectural overview.
[UML](https://github.com/adbjo/mattermost-webapp/blob/Documentation_Report/doc_imgs/uml_diagram.pdf).

Optional (point 2): relation to design pattern(s).

## Selected issue(s)

Title: Migrate 'components/user_settings/notifications' module and associated tests to TypeScript

URL: https://github.com/mattermost/mattermost-server/issues/13690

Migrate the code from Javascript to TypeScript for the files.

### Requirements affected by functionality being refactored

##### #1 Rename to .tsx
All files (except in subfolder) in the folder `components/user_settings/notifications` should have their file extensions changed from `.js(x)` to `.ts(x)`.

##### #2 Update `import` statements
All `import X from 'Y.js(x)'` where `Y` is a file in `components/user_settings/notifications` should be changed to `import X from 'Y'`. 

##### #3 Solve type errors 
All type checks should pass. To test this, run `make check-types` or `npm run check-types`.

The relevant test for these requirements is running the `@types/marked` library (by running task `check-types`) which will fail if any type error is found, as well as running the test suite (`npm run test`) which compares the stated types against the data in the test. As no functionality should be changed by resolving these requirements, no explicit test cases are relevant, but instead the regression suite as a whole decides if the requirements are followed or not.

### Existing test cases relating to refactored code

All test cases related to the code that was refactored have been further documented in their respective files. They can be found here;

[desktop_notification_settings.test.jsx](https://github.com/adbjo/mattermost-webapp/blob/Documentation_Report/components/user_settings/notifications/desktop_notification_settings.test.jsx)

[manage_auto_responder.test.jsx](https://github.com/adbjo/mattermost-webapp/blob/Documentation_Report/components/user_settings/notifications/manage_auto_responder.test.jsx)

[user_settings_notifications.test.js](https://github.com/adbjo/mattermost-webapp/blob/Documentation_Report/components/user_settings/notifications/user_settings_notifications.test.js)


### Test results

Overall results with link to a copy or excerpt of the logs (before/after
refactoring).

#### Strongbox
[Test results before refactoring](https://github.com/adbjo/mattermost-webapp/blob/Documentation_Report/doc_logs/testlog_strongbox)

Considering we didn't actually refactor their code, since we chose anotehr project, there are no tests results after the refactor because it never happened.

#### Mattermost

[Test results before refactoring](https://github.com/adbjo/mattermost-webapp/blob/Documentation_Report/doc_logs/testlog_before_mattermost)

[Test results after refactoring](https://github.com/adbjo/mattermost-webapp/blob/Documentation_Report/doc_logs/testlog_after_mattermost)

### Patch/fix

The fix can be copied or linked to (git diff).

All changes made can be found in [pull request #4963](https://github.com/mattermost/mattermost-webapp/pull/4963)

Optional (point 4): the patch is clean.

Optional (point 5): considered for acceptance (passes all automated checks).

## Effort spent for discarded project 5.5h per person
 ( https://github.com/strongbox/strongbox/issues/1398 )
For each team member, how much time was spent in

1. plenary discussions/meetings;

Everyone: 1 hour

We found a project and issue that looked promising and proceeded to read documentation and set up.

3. reading documentation;
    
Everyone: 45 min

4. configuration and setup;
    
Everyone: 45 min

The project is rather large and took some time to set-up and some members had some issues that we had to figure out.

5. analyzing code/output;

Everyone: 3 hour
We all went through the documentation and tried to understand the code. We realized the issue was a bit too complex for us and decided to find a new issue.

## Effort spent for project 2

For each team member, how much time was spent in

1. plenary discussions/meetings;

Everyone: 2.5 hours

Took a while to find another project, which we looked for by going through different github repositories that had a lot of issues, good documentation and the 'good first issue' label. Once mattermost was found we started to read up on documentation and set it up.

2. discussions within parts of the group;

Gabriel: 2.5 hours

Discussed report writing with Kasper and typescript conventions in repository with Robin and Adam.

Kasper: 4.5 hours

Looking for new projects with Johan, discussed report writing with Gabriel and to find the actual issue to work on with Robin and Adam. 

Robin: 3 hours

Discussed potential issues with Kasper and Adam and the typescript conventions in the repository with Adam and Gabriel.

Johan: 3.5 hour
Looking for new projects with Kasper, and being the local typescript-guru, helping everyone in the group.

Adam: 3 hours

- Discussed TypeScript principles and conventions with Robin and Gabriel.
- Browsed the mattermost-server repo together with Robin and Kasper to find a suitable issue.
- Communicated with the mattermost developers to get us assigned to the issue.

3. reading documentation;

Gabriel: 3 hours

First off I looked through the mattermost [documentation](https://developers.mattermost.com/contribute/webapp/) to learn more about how the project is set up and how components and testing is done in the project which they described quite nicely. After this, I had to take a closer look at how typescript worked, to learn it basically, and related issues to see what the convention was when refactoring.

Kasper: 3 hours

I went through the same process as Gabriel.

Johan: 2.5 hours
Went through the same procees as Gabriel, except for learning typescript, which I knew since before.

Robin: 3.5 hours

I basically did the same stuff as Gabriel, a lot of time spent looking through old issues and PRs to understand their conventions.

Adam: 3 hours

- Same as Gabriel.
- Went over the contributor guidelines over at [mattermost](https://developers.mattermost.com/contribute/getting-started/contribution-checklist/), and examined issues and pull request already on the repo to understand their practices and conventions.

4. configuration and setup;

To setup the Mattermost server:
- Docker CE was installed and configured
- Go was installed and added to PATH
- The repository was forked and cloned locally.

To setup the development environment, these dependencies were needed:
- node.js
- libpng

Gabriel: 1.5 hours

It went quite smoothly for the most part, but we had some issues with getting the Docker environment to work properly. After reinstalling it and its dependencies it magically started working.

Kasper: 1.5 hours

Johan: 1.5 hours

Robin: 2.5 hours

My computer is old as @#%$ and I had some problems with node/npm.

Adam: 2 hours

- Forked the repo and managed development branches
- Setup was very smooth thanks to great guides available at the repo owners website.

5. analyzing code/output;

Gabriel: 1.5 hours

Analyzing relevant tests and code in order to add documentation for them and to figure out types to use for variables that require them.

Kasper: 1.5 hours

Robin: 2 hours

Johan: 4h
See point 7.

6. writing documentation;

Gabriel: 4 hours

Writing code documentation and report

Kasper: 2 hours

Robin: 3 hours

Code documentation for the tests and report writing, also helped with the UML class diagram.

Johan: 3 hours

Adam: 3 hours

- Co-wrote UML class diagram with Robin.

7. writing code;

Gabriel: 5 hours

Not a lot of code had to be changed in my assigned file which was user_settings_notifications.test.tsx, just took a little bit for me to figure out how typescript properly worked. Most of my time was spent pair-programming with Kasper on the manage_auto_responder file.

Robin: 4.5 hours

My assigned work was on index and desktop_notification_settings, but as Gabriel it took some time to understand typescript and the changes themselves were not that large. I did some pair-programming with Adam during the remaining time.

Kasper: 6 hours

Mainly worked on manage_auto_responder file and manage_auto_responder.test file. Had to change proptypes to Props in manage_auto_responder file and move them outside of the function and update some parameters. There was some issue with some of the props and I had to get in touch with the developers whom gave me premission to add the props in autosize_textarea. Gabriel pair-programmed with me on manage_auto_responder.

Johan: 7 hours

Had `user_settings_notifications.tsx` as main file to migrate. This was the primary file in the folder and therefor had quite a lot of connections, internally to other components in the folder as well as externally through props from parent components. To get all the prop and state types correct I had to do a lot of research into neighboring components as well as into the redux files. This led me to the `UserProfile` interface and the `utils/constants.jsx` files. The latter had to be converted into typescript to gain type benefits to `user_settings_notifications.tsx`. This further led down to finding a few bugs as well as a few questions regarding these external resources.

Adam: 5 hours

- Migrated desktop_notifications_setting to typescript.
- Helped Kasper with migrating manage_auto_responder.
- Rebased and cleaned the patch branch.
- Squashed our branch and resolved conflicts in preparation for the pull request.

## Overall experience

What are your main take-aways from this project? What did you learn?

Our main take-away from this project would be how to work with open source projects in general. We got to learn things like how to find good issues, how to adapt your coding style to an already existing code base and how to get in contact with existing developers of the project to ask for feedback and help. Some of us also had not worked that much in TypeScript before, so converting code the code taught us about how the language itself works and also conventions in it. In context to best software engineering practices we did use issues to track our problems, branches, had almost daily meetings to see where we were all at, made sure to keep styling conventions, kept in touch with the developers of the software and used unit tests to make sure that the code itself in fact still worked.

Optional (point 6): How would you put your work in context with best software engineering practice?

Optional (point 7): Is there something special you want to mention here?
