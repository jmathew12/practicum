Week 7
This week I worked on next wave dev static website and nsc events supabase backend integration. I added myself to the developers page on next wave dev and then helped refactor the files in next wave dev. developers were still being refered to as students - changes what was remaining when we cloned the nsc ad website for next wave dev. I changed all the reference of student to developer. I also helped review a whole bunch of pull requests. On top of that, I am working on nec events. Currently I am helping set up the front end to use supabase as backend. I am completele new to this and have been teaching me supabase by taking courses for it. 
Issues: https://github.com/next-wave-dev-org/nwd-static-website/issues/72, https://github.com/next-wave-dev-org/nwd-static-website/issues/116, https://github.com/SeattleColleges/nsc-events-fullstack/issues/145
Pull Requests: https://github.com/next-wave-dev-org/nwd-static-website/pull/115, https://github.com/next-wave-dev-org/nwd-static-website/pull/117
Pull Request reviews: https://github.com/next-wave-dev-org/nwd-static-website/pull/111, https://github.com/SeattleColleges/seattlecolleges.github.io/pull/141, https://github.com/SeattleColleges/seattlecolleges.github.io/pull/140, https://github.com/SeattleColleges/seattlecolleges.github.io/pull/139, https://github.com/SeattleColleges/seattlecolleges.github.io/pull/138

Total Hours 30
PR Reviews - 6 hours 
Issue and PR - 12
Research for supabase - 12

Week 6
This week I continued working on the NSC events apt end points research. Because of the supabase integration, we will need to know all of the endpoints the front end uses so that we can cover those same endpoints with supabase. This was a lot if manual work. Looking through all the files searching for all the api calls. I am sure there may be some that I have missed. I did not have a pr this week since it was mostly just research and no pr. I did two pull request reviews as well. 
Issue: https://github.com/SeattleColleges/nsc-events-fullstack/issues/146
PR: none, issue did not need a pr, it was research 
PR Review: https://github.com/GeekGirlCon/mobile-app/pull/159, https://github.com/next-wave-dev-org/nwd-static-website/pull/107#pullrequestreview-3803445846
Total hours 15
Issue: 12 hours
PR Reviews: 3 hours

BC
Week 6
This week, I worked on researching an issue with geekgirlcon. There was an issue with the android push notifications failing. I did research and found out that the notifications were failing because expo-notifications were removed from expo go starting sdk 53. So instead of using expo go to test it, you would have to create a development build on an android phone to test it. I was able to do this. This was the first time I was testing something and I was able to fidure out that notifications were working as intended. No pull request was needed for it since there was no "issue" to resolve other than just finding out that we needed to change the way we test some of the prs because of the limitation of expo go. This was similar to the issue we ran into week 1 and two where splash screen did not show in expo go either and we needed development build. This issue taught me about different types of builds and how to test them. Also about the difference between expo go and dev builds.

Issue:https://github.com/GeekGirlCon/mobile-app/issues/169
PR Review: https://github.com/GeekGirlCon/mobile-app/pull/159
Total hours 13: 
    Research, set up, and testing the build: 10 hours
    PR Review: 3 hours

Scrum note
Since there were not any open tickets available, I worked on a ticket which was for 3 developers. It was ti find bugs on NSC events. Since I am not familiar with the backend that well, I tried to find the bugs on the front end. I found 7 bugs after logging in as user, creator and admin. One of the main parts of the app that seem to be buggy is the add and edit event form. Currently edit and create events have different forms, which I think needs to change. I think it would be ideal if a same form was used both with similar logic. Also another suggestion is making tags on the main events page clickable. Since these are not necessarily bugs, I did not include them. 

Issue: https://github.com/SeattleColleges/nsc-events-nextjs/issues/704
Issue: https://github.com/SeattleColleges/nsc-events-nextjs/issues/703
Issue: https://github.com/SeattleColleges/nsc-events-nextjs/issues/702
Issue: https://github.com/SeattleColleges/nsc-events-nextjs/issues/701
Issue: https://github.com/SeattleColleges/nsc-events-nextjs/issues/700
Issue: https://github.com/SeattleColleges/nsc-events-nextjs/issues/699
Issue: https://github.com/SeattleColleges/nsc-events-nextjs/issues/698
About 10 hours spend
Hour and half or so for finding and reporting bugs.
Learning outcomes:
    Manual testing of the app

Since this is not a normal development week and I did not do much of code, none of the other sections are included.


Scrum Note
For week two, I worked on geek girl con for the first time. I set up my environment and tried to get a feel for the project. I picked up issue 162 which was investigating a white splash screen  that used to be green before. This was due to a change starting with sdk 52. I tried to change the configurations files to see if anything changes and nothing did. So I did do some research and the got the same answer. It was that expo do not preview the actual splash screen anymore and you have to run the ass as  a build and not in expo. Me and Katrina met up to talk about the issue.

Issue: https://github.com/GeekGirlCon/mobile-app/issues/162
Setting up and going over the project 4 hours
Meeting with team 1hr
meeting with Katrina 1hr
Research on the issue: 8 hours

Total 14 hours


Scrum note
I continued to work on the same issue from last week. I did some more research and was coming to the same conclusion, there is no way to preview the changes to the splash screen on an expo build. Katrina came to the same conclusion as well. Ayub confirmed that we can ignore this issue since it is not reproducible and there is no picture or video os the issue to go off of. I also did pr reviews for week 2. Hopefully I am able to find some development related tasks for upcoming weeks.

Issue: https://github.com/GeekGirlCon/mobile-app/issues/162
PR Review 1: https://github.com/GeekGirlCon/mobile-app/pull/165
PR Review 2: https://github.com/SeattleColleges/seattlecolleges.github.io/pull/124#pullrequestreview-3720541826

Total Hours for week 3: 6 hours
    Issue: 4 hours
    PR Reviews: 2 hours 


Week 4
Scrum note
This week I worked on issue 142 for NSC Events. The password reset workflow allowed users to reset their credentials to the same password they are already using. This was very inefficient and caused unnecessary work. I added a password validation feature to prevent this from happening. This was a good experience and I was able to work with the back end and the front end and see how the two interacts with each other. I was able to understand a lot. Especially navigating the project and understanding the structure. Currently the PR is not able to merge because of some failing tests. I have never done tests, so this will be a good chance for me to learn how to do tests. I also did two reviews for the same pr. The first time, there was an issue, and troy suggested me to try something else and I did that as well. There still seems to be a bug that is causing an issue. This needs to be addressed.

Issue: https://github.com/SeattleColleges/nsc-events-fullstack/issues/143

Pull request: https://github.com/SeattleColleges/nsc-events-fullstack/pull/147

Branch: https://github.com/SeattleColleges/nsc-events-fullstack/tree/143-missing-password-reuse-validation

Pull request review: https://github.com/GeekGirlCon/mobile-app/pull/159

Total hours: 21
Understanding the code and working on the issue: 18 hours
PR Reviews: 2 hour 
Pull request: 1 hour

Week 5
This week I fixed the tests that were failing on the pr that was wfailing last week, My pr broke some of the tests and they had to be rewritten. It was my first time writing tests and the logic was pretty hard for me to understand. I had to do a little bit of research to figure out what I was doing and I am still not confident on how it is going. I think I need to pick up couple of the writing tests tasks and see if I can learn about it. I also helped troy review a pr. It was still failing and it needs to be changed. I had to do some extra work on figuring out what the issue was. I am going to do some research on the issue and see if I can figure out what is going on. 

Issue:https://github.com/GeekGirlCon/mobile-app/pull/159
PR:https://github.com/SeattleColleges/nsc-events-fullstack/pull/147
PR Review:https://github.com/GeekGirlCon/mobile-app/pull/159
Total hours 15: 
    Research and writing tests: 13 hours
    PR Review: 2 hours