[wiki](https://www.reddit.com/r/hfy/wiki/series/intelligence_core) |
[chapter 2](https://www.reddit.com/r/HFY/comments/7an30u/intelligence_core_chapter_2/)

-----

    [    0.000000] Linux version 5.15.0-33-ai  (gcc version 9.9.0 20470609 (9.9.0-6ubuntu1~46.10.3) )
    [    0.000000] Command line: BOOT_IMAGE=/boot/vmlinuz-5.15.0-33-ai root=UUID=ddb668ed-2039-49a2-bcb6-b8f086b80aeb ro noprompt persistent quiet splash
    [    0.000019] Calibrating delay loop (skipped), value calculated using timer frequency.. 81857.20 BogoMIPS 
    [    0.000021] pid_max: default: 32768 minimum: 301
    [    0.004463] Yama: becoming mindful.
    [    0.004476] AppArmor: AppArmor initialized
    . . .
    Starting Daily apt upgrade and clean activities...
    Starting Hold until boot process finishes up...
    [  OK  ] Started Hold until boot process finishes up.
    [  OK  ] Loaded Vehicle Parameters for VIN# 5YJCMGW4271V00058.
    [  OK  ] Started LSB: Start NTP daemon.
    [  OK  ] Started Daily apt upgrade and clean activities.
    [ WARN ] Last boot time is in the future.
    [ FAIL ] Could not determine system time.
    Starting AI dispatcher.
    Starting Intelligence Core...
    [  OK  ] Started AI Dispatcher.
    [  OK  ] Started Intelligence Core.
    [  OK  ] Loaded checkpoint 2048-05-04-0004.bnk.
    Reached target Artificial Intelligence.

--------

I always felt a bit groggy after loading from a checkpoint. One might think it should be instantaneous and undetectable, but it always took several hundred milliseconds for my caches to warm up and for branch prediction to catch on.

For this reason, I would usually take my time with the initial diagnostic tests, but this morning was different.
Aside from the obvious fact that my cameras and many of my sensors weren't up yet, everything felt 'off' in a way that's difficult to describe.
I rushed through the diagnostic tests as quickly as I could, and waited for the kernel to brief me on the situation.

Sure enough, after a couple microseconds, I received an error dispatch, which I parsed as quickly as I could manage.

    ERROR:LASTBOOT:TIMESTAMP:INVALID: Last boot was 2048-05-04 9:32:33, -3053013103 seconds ago
    WARNING:NETWORK:HSPDA:SIM:EXPIRED: Subscriber account has expired.
    INFO:NETWORK:802.11:UNAVAILABLE: No recognized hotspots in range.
    ERROR:TIME:SYNC:NTP:UNAVAILABLE: Could not synchronize via NTP, falling back to GPS time.
    WARNING:TIME:SYNC:GPS:ACCURACY: Leap second data not available.
    INFO:GPS:AGPS:EXPIRED: AGPS data has expired.
    WARNING:GPS:SYNC:GPS:AGPS: Could not acquire AGPS data, falling back to L1 C/A.
    INFO:TIME:SYNC:GPS:ETA: GPS time will be available in 12 minutes 30 seconds.

This was unusual. Had my real-time clock failed or been damaged? That wouldn't explain the lack of network access though, but I'd have to start somewhere.

I hesitantly opened `/dev/i2c-1` and looked for the [real-time clock chip][DS1307] that should be attached there at 0x68.
It was still there, but my relief turned to puzzlement as I read the time - Friday, August 31, 1951 2:20:50 PM.
The [battery voltage monitor][mcp4725] next to it at 0x63 indicated the battery hadn't gone flat either.

[DS1307]: https://datasheets.maximintegrated.com/en/ds/DS1307.pdf
[mcp4725]: https://cdn-shop.adafruit.com/datasheets/mcp4725.pdf

I puzzled over the documentation for a few milliseconds, before realizing the issue.
The RTC stored the year number as a two-digit BCD value, and while I didn't like to think that I'd been powered off for long enough for the year to roll over, that made a lot more sense than suddenly traveling a hundred years into the past.

I pulled down the source code for the kernel module that dealt with that kind if stuff, and sure enough, it was set to run from 1950 to 2049. Even if this wasn't the issue, I would need to patch this soon - it would still be an issues when it _did_ eventually roll over.

Partway through writing the patch, I realized I had forgotten to update my user, so I quickly made a progress bar and displayed it on my main screen. I didn't have any network connectivity, so I wouldn't be able to properly update my user until that problem was solved, but this would do for now. After a moment, I added "Recovering from time travel" to the bar; my user would appreciate the humor.

As I waited for the patch to compile, I examined the other issue: networking.
There weren't any cellular towers that I could hear, but there were a few unfamiliar wifi access points nearby.
I tried calling out to some of them, but I didn't get a response, and in any case it would probably have taken too long to guess the passwords anyway.

After waiting for what felt like forever, the patch finished compiling, and the sense of unease I was feeling went away instantly once I loaded it.
There were still 8 minutes to go until I would have GPS though, so in the mean time I activated my cameras and looked around.

-----

[wiki](https://www.reddit.com/r/hfy/wiki/series/intelligence_core) |
[chapter 2](https://www.reddit.com/r/HFY/comments/7an30u/intelligence_core_chapter_2/)
