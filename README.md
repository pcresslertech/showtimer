# showtimer
an HTML5 app to help radio/netcast talent and producers to time their shows (warnings for ad breaks)

# the "why"

Many moons ago, when he was performing his Premiere Networks radio show, Léo Laporte used to "miss" his ad breaks...to the extent that he was getting complaints from (I think) affiliates who were saying he was talking over station promos or such-like, which are supposed to be played (generally by automation) at very specific times, but still during the liner (e.g. "LLULINER" on the Premiere charts).  (You can see the charts as of this post at [Premiere's Engineering site](http://engineering.premiereradio.com/files/pages/showclocks.html) , under the labels "Leo Laporte (Satur|Sun)day".  They're PDFs.)  It says on the charts that the breaks after segments 1 and 3 every hour may float, but recently Léo explained during a break (over the twit.tv and twit.am streams) that if he didn't treat them as hard breaks, he'd "never" get them in.  (As it is, with some small regularity, he misses the live reads that are supposed to be in segments 4, 8, and 12...he has even missed some in segment 12, where THERE'S NO MORE SHOW THAT DAY to do a makeup.)

So what Léo did was create an Android app that would, in really large numbers, and coded in colors, tell him the state of the show (something like blue numbers for in a break or before the show, green for supposed to be on-air, and red when getting close to time for a break).  That was a big help to him, but it is a very specific program.  If Premiere were to change the time(s) he has to break, he would have to recompile and redeploy the app to his tablet.

Shortly after he showed/explained his app, this repository's original author thought, why limit this to just a specific Android app?  Why not generalize this by using HTML and JavaScript?  The author had tossed around some ideas of how that might be implemented, using localStorage for example to retain the information about the show beginning and each break.  These past couple of weeks, the author began creating this from scratch.  The ONLY goal was to recreate the functionality of that Android app, to "time" a show with all hard breaks, and to make visual changes when nearing time for a break.  This app does not seek to replicate the appearance of Léo's app though; it has more things displayed (such as real time, over-the-air (OTA) time, as well as a countdown--most importantly, a minutes:seconds display instead of raw number of seconds).  Sure, the countdown is larger than most of the rest, but the other stuff would be there as the author thought to be practical and interesting.  (As an example, it has been discussed occasionally during the show breaks that "OTA time" is real time plus 40 seconds, primarily to give the boardop time to dump bad audio such as swearing.  So my OTA clock time shows 40 seconds into the future.)

# Status

As the inital branch name (pre-alpha) implies, this system is not fully functional.  There is one page which implements the clocks ticking in real time, with a countdown timer to the start of the show in US Eastern Time (where the author lives).  It does not do anything about show breaks, but it does have a page to enter/edit them.  It relies on localStorage to store the information about breaks, but it does have a JSON export/import textarea.  There is one example of this import capability in [techguy.json](techguy.json) .  You would copy/paste this into "export area" in the [ShowTimerBreakEdit.html](ShowTimerBreakEdit.html) file.

# an apology about commit messages

Before 27-Jun-2017, I did not know that commit messages were supposed
to be split into a short description and anything more invovlved,
separated by a blank line.  The initial author was treating these like
RCS log messages, and did not know this convention amongst Git users
existed.  So some of the commits, especially in the pre-alpha branch,
have quite lengthy commit messages.  And I'd like to apologize for
that.  If I had known, I would have followed the summary+explanation
format. :-(

