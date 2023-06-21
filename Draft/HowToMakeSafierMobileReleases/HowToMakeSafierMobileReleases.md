# How To Make Safier Mobile Roll out Releases

App stores have a substantial influence on the release process. To prevent frustration, it is crucial to consider their specific flow and comprehend how they operate. 
Enhancing the release process to be more seamless and transparent is vital to ensure timely delivery of new content and features, 
thereby bringing joy to your players according to your schedule. 
From a business perspective, establishing a predictable time to market holds immense significance, particularly for activities such as CRM or marketing campaigns.

relevance of all links and the info at 21 June 2023.

**Overview**

| App store   | Review process                                                                     | Gradual opening                                                                                                                                                          | Release data                       | Official guids                                                                                                                   | Sandbox for tests            |
|-------------|------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------|----------------------------------------------------------------------------------------------------------------------------------|------------------------------|
| Google      | [Link](https://developers.google.com/workspace/marketplace/about-app-review)       | [yes](https://support.google.com/googleplay/android-developer/answer/6346149?visit_id=638228478821573509-2375162816&rd=1#zippy=) - target direct percent and countries   | The richest data from your release | [Release](https://play.google.com/console/about/guides/releasewithconfidence/), [Quality](https://developer.android.com/quality) | Beta testing                 |
| Apple store | [Link](https://developer.apple.com/app-store/review/)                              | [yes](https://developer.apple.com/help/app-store-connect/update-your-app/release-a-version-update-in-phases)  - for 7 days , not direct percent  and no target countries | Essential overview data            | ?                                                                                                                                | Testflight for connect users |
| Amazon      | [Link](https://developer.amazon.com/docs/app-submission/update-published-app.html) | [yes](https://developer.amazon.com/docs/app-submission/release-updates-in-staged-rollouts.html#advantages)  - target direct percent                                      | no                                 | no                                                                                                                               | ?                            |

>Gradual release is Phased release for AppStore and Stage release for Google and Stage roll out for Amazon

**Common limitation of app stores**
- You can not exclude directly specific players like VIP from target audience when roll out a new release.
- You can have only one gradual production release at the same time with the full rollout release.
- Review process usually takes about 1 day but can be up to 7 days in exceptional cases like during holidays.
- Technical metrics came to dashboard with delays. It can be a critical time lag to decrease affect of issues.

Shortly to avoid unexpected issues with a release you need to be good with:
- To be compliant with the newest of app store requirements. Like support new Android API for Google.
- To be compliant with app store quality guidelines.
- To know about gradual opening.
- To have ability to track your important KPI's in real time.
- To have plan B if the new version has a critical issue.
- Other options with excluding resubmit to store from your release process as much as possible.

First of all I recommend to  understand for you what is high risked release and less risked release.
For instance *high risked release* could include new  Unity version. 
You are not able to test the change on all target devices with full OS combinations. And it is not possible to disable part of native sdk remotely. 
In this case only production test will give you understanding about stability of the release.
**But how to decrease or fully avoid an impact of changes on your most valuable target audience ?** 

I recommend to separate technical and non technical changes into different releases to avoid mixing a lot of changes for big period of development into one release.
If you will see bad results in your tracked KPI for a new release it would be definitely hard to find a root cause. Is it an issue with new UI or there a technical issue with pushes that freeze devices?
Also it is good practice to make regular releases 2 per month or more. Decreasing size of new changes in one release wll reduce a chance to get unclear trouble in production
and will increase speed to diagnostic it and apply action items.

*Less risked release* will be when you can operate remotely new change list of features or some new content can be segmented or controlled dynamically and disable any unstable part of application if there happens any unexpected issues .

## general advice:
make any significant changes in client are remotely operated as much as possible with new bundles or dynamic configs and if something will go wrong
you can adjust settings and fix them remotely without resubmit of client tos tore. In resubmit you should rely on fast stable rebuild client, it can have dependance on content rebuild,
testing again and waiting for review. **Review process on App store for instance sometimes can be really frustrated experience.**


From my point of view *Google play console* can provide the richest advantages to make the calmest release than App store or Amazon store.
And you can make gradual release with target % of adoption and countries and track performance of new release. 
Also Google provide closed testings
>
>With [closed testing](https://play.google.com/console/about/closed-testing/), you can create 1 or more closed testing tracks to test pre-release versions of your app with your own groups of testers

>As a Play Partner, you also receive these benefits:
>Generate access codes to give users easy access to closed tests without collecting their email addresses
>Invite selected pre-registered users into a closed test with pre-registration testing. Go to the Pre-registration page to find out how.

Lets see 2 strategies to mitigate production incidents with risky changes in release

**Strategy A for all countries**
- 1 day) Starting from Google stage roll out from acceptable percent 10% depending on DAU of target audience and countries
- 2 day) Increase gradually target to 50% if technical metrics are acceptable.
- 2 day) If all release KPI metrics are acceptable sent to review iOS and Amazon build
- 4 day) Check D2 retention for 2 versions for 2 days in US organic. 
- 4 day) If all tracked release KPI metrics are acceptable sent to review iOS and Amazon build.
- 4 day) If business metrics are acceptable lets increase target to 99.9% for Google store.
- Start phased iOS release for 7 days and track technical performance. Business metrics mostly should be ok if you have crossplatform features.

**Strategy B starting gradual release from low tier countries**
- 1 day) Starting from Google stage roll out from acceptable percent 10% depending on DAU of target audience and low tier countries
- 2 day) if technical metrics are acceptable lets add high tier countries and increase target to 50%.
- 2 day) Send review iOS/amazon.
- 3 day) if technical metrics are acceptable lets add US and other world.
- 5 day) Check D2 retention for 2 versions for 2 days in US organic. 
- If business metrics are acceptable lets increase target to 99.9% for Google store.
- Start phased iOS release for 7 days and track technical performance. Business metrics mostly should be ok if you have crossplatform features. 

## important advice:
You have to compare KPI metrics between same countries and installs of same days and volume. 
You can make wrong decisions about stability a version when you compare 
a metric from version with 5k of sessions with a version with 1M sessions or to compare D2 for Vietnam location with USA D2.
Ideally you should take USA organic installs for last 2 days from the newest version and compare USA organic installs for last 2 days from the previous release.

How to choose Low tier countries: 
- No big revenue impaction
- Enough installs with reasonable adoption speed. If It is provide 100 installs for 1 week it is too long and not enough data to make any decision.
- Good variety of available devices with different models and different operation system. I could remember few cases when on some regions you get analytics and issues that is not corelated with other part of world. like most devices in Nepal are Vivo

The main reason to define low tier countries are to collect enough technical metrics to be sure that changes are safier and you continue 
rollout on other countries.

Less safest option but from analytics the most reliable option it is start gradual opening for all world countries from 5%-10%. Depends on installs and update trend of your product.
In this case you can control speed of installs target and will collect reliable analytics.

## general advice:
make full rollout only when you start a new release. lets put the main target adoption of a release to 99.9% for google. it will allow you to halt rollout
immediately in case of unexpected troubles in production. 
Otherwise you need to resubmit of client with new app version code to be accepted by store and pass the review again. When critical bug in production happens
and you could not decrease impact of an issue immediately by a remote option it makes sense.

## general advice:
make final smoke QA check before opening of the app on builds downloaded from stores(testflight , not distributed as a bundle or apk. for instance some functionalyt can be triggered only from store builds
like google referer api otherwise tou can miss the technical issues and be frustrated in production for real players. 

# features to take a look
[Google Custom store listings](https://support.google.com/googleplay/android-developer/answer/9867158?visit_id=638228524369380759-314294836&rd=1)