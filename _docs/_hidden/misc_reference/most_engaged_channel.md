---
nav_title: Most Engaged Channel
permalink: /most_engaged_channel/
---

# Most Engaged Channel Filter
The Most Engaged Channel filter selects the portion of your audience for whom the selected messaging channel is their "best" channel. In this case, "best" means "has the highest likelihood of engagement, given the user's history". You can select Email, Web Push, or Mobile Push (which includes any available mobile OS or device) as a channel. 
![most_engaged_channel_filter][1]{: height="50%" width="50%"}

The Most Engaged Channel computes the engagement rate for each user for each of the three channels by taking the ratio of message interactions (opens or clicks) to the number of messages received over the last 6 months of activity. The available channels are ranked according to their respective engagement ratios, and the channel with the highest ratio is the "Most Engaged" for that user. Every time a message is sent to a user and every time they interact with a message, the Most Engaged Channel is refreshed within seconds. Any interaction with a message causes it to be considered "interacted with" only once, e.g. an open and click on the same email will cause that message to be marked as having been engaged with only once, not twice.

## The "Not Enough Data" Option

For Braze to determine which channel is "best", there needs to be adequate data. This means that a user must have received at least three (3) or more messages on at least two (2) of the three (3) available channels. The messages do not necessarily need to have been opened.

So, if a user only has data for one (1) channel, or less than three (3) messages received on two (2) or three (3) channels, that user will then fall under the "Not Enough Data" option of this filter. This will allow you to choose to use whichever messaging channel you wish for the users that do not have a "Most Engaged Channel" reliably calculated.

For example, if you want users who prefer _push messages_ to receive a push, as well as users for whom there is not enough data to receive the same push message, you could set the "Most Engaged Channel" filter as "Mobile" and use __OR__ to add a second "Most Engaged Channel" filter set to "Not Enough Data". This way users who prefer push will receive one as well as users for whom there isn't enough data to know. A separate campaign with the Most Engaged filter set to "Email" could address users who prefer email.

## The "Mobile Push" Option

Mobile Push incorporates Android, iOS, Windows, Kindle, and all other mobile device channels available on Braze. When computing the Most Engaged Channel, Braze looks at each kind of mobile device separately, but then chooses the highest engagement rate among them to represent the "Mobile Push" category when comparing against Email and Web Push. So a user with an iPhone, Android phone, and iPad with engagement rates of 0.1, 0.2, and 0.45, respectively would have their Mobile Push engagement rate calculated as the best of all those devices: 0.45. This would not, however, force that user to receive Push notifications on the iPad— they can still be considered as preferring “Mobile Push” even when using the filter on an Android push message.

## Best Practices & Effective Use Strategy

### Tie-Breaking

Because some users will have low numbers of messages received, it is not unusual to have "ties" in engagement rates across the available channels for a single given user (a single user has a 0.2 engagement rate for __both__ Email and Mobile Push). In such cases, ties will be broken by prioritizing (giving a higher ranking to) the channel with the most recent open events.

### Unreachable Channels

When the user has sufficient data for a ranking to be determined, but becomes unreachable on their "Most Engaged Channel", the user will "fall out" and not receive any messages. Users who are unreachable on specific channels should be targeted separately.

### Audience Sizing

Most Engaged Channel allows you to selectively target in advance the fraction of users who have a much higher likelihood of engaging with a message than the rest of your audience. This is not likely to represent a majority of users in a typical audience. Rather, you can expect this filter to find the 5-20% from your usual audience who have an established record of engaging on a particular channel. 


[1]: {% image_buster /assets/img/most_engaged_channel.png %} "Most Engaged Channel Filter"
