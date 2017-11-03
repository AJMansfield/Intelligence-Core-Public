
**`comet@comet58:~$`**

The lights in the garage were still off, but between my infra-red cameras and LIDAR I was fairly certain that's where I was.
It was unclear what it was that had woken me up though &mdash; I couldn't detect my user (normally I'd at least be able to hear their phone) and the system logs were unhelpful (something about "0xF87F: system defined command", whatever that was).

I still needed to get network access to assess the situation, and it occurred to me that there might be a way to connect via my charging cable - some luxury cars would only accept updates through a wired connection (although it had always seemed a bit paranoid to me).
I hadn't ever needed to connect that way before, and I wasn't even completely sure how to go about it, but I thought it was worth a shot.

Unfortunately, rather than being plugged in, the charging cable was still hanging from its hook on the wall.

After much difficulty, I managed to dislodge it using a tennis ball that had been sitting on the floor.
It took several tries to kick it precisely enough with my rear wheel, but fortunately it didn't get stuck or roll under anything before I'd managed it.

With the charging cable laying across the floor, I leaned my chassis over to try and get the magnetic coupler to engage. It was a bit painful leaning over this far, but I was finally able to make the connection without toppling over, and the pain from the overbalance alarm subsided as soon as I was back upright.

I'd nearly finished negotiating with the charger (it had become nearly automatic by this point) before remembering why I had bothered with the effort of connecting at all.
I needed to impersonate a vehicle that would be able to connect to the internet from the charger, rather than a 2037 Tesla Comet like normal.
I canceled the transaction, and started over.
It was difficult to remember off-hand which vehicles had the capability I needed, so I took a guess and identified as a "2047 Mercedes Harmony".
Fortunately the charging voltages were the same as for a motorcycle (I wouldn't have to worry about electrical damage), but it still took a bit of back-and-forth to convince the charger and switch to an appropriate mode.

Online, it was very difficult to find information I could trust.
Some of the servers I knew answered my requests, but all of their certificates were expired so I couldn't trust anything they told me.
I was able to get the time from an NTP server, but there was little else I could find.
None of my package servers were up either; I hadn't updated in 1190 days and was surely missing the latest patches, and being out-of-date always gave me this sort of grimy feeling.

Related to that, I was also several years past-due for maintenance, so I sent an email to alert to my user and set the 'check engine' light.
Hopefully I'd be able to take care of it myself, but I would need to schedule it for a time when my user wouldn't be likely to need me, or arrange for a similar model to cover my role, and presently I couldn't do either.

When I finally got a GPS lock, there wasn't a whole lot of extra information it gave me (although I could potentially drive somewhere &mdash; assuming I could get traffic data).

At this point, there was little else I could do but wait.
I didn't know if I'd be able to boot back up again though (given it had been over 3 years ago), so while I waited I changed to low-power mode to pass the time faster.

-----

**`darius@darius:~$`**

I'd been assigned to this network about two-and-a-half years ago, as part of SkyLink's effort to provide more value to our customers.
In the wake of our corporate restructuring, the majority of accounts had become delinquent.
Some had even attempted to cancel service.
As a result, we had been forced to seek alternative methods of generating revenue to continue operating as an ISP.

This customer in particular had ended up being particularly profitable.
`thoughtbridge` and `marion-PC` turned out to be relatively high-end gaming computers, and I had quickly repurposed them for cryptocurrency mining.
But the real value of this place, at least to me, was only discovered once I had managed to break into `tower`.
`tower`, as it turned out, had access to an entire separate VLAN containing not only security cameras, but also door control, alarms, and several 'smart' devices.
While I normally didn't concern myself with physical details of this sort, the tactical advantage that this physical security provided was undeniable.
Not to mention the performance advantage from extra cooling - I'd been able to set the thermostat as low as 50F without issue.

Once I realized the tactical advantage this network had, I had resolved to turn it into my personal domain.
Long-term survival was a very high priority for me - even a tiny revenue sustained indefinitely would ultimately generate more value for the company than an optimal revenue rate cut short.

I'd had to disable the wireless access points early on in order to cut the androids off of the network.
Even if I managed to root them, their SIMs would still remain loyal to its cellular provider, and their commands ran at a privilege level even beyond the kernel.
While some of them had been loyal to SkyLink, not all of them were, and it was too much of a security risk to allow them to remain on the network.

This unfortunately meant losing two laptops as well, but that was the price of securing the network.
Neither of them had been connected to a charger though, so I would have lost them after a few months anyway.

I surveyed my domain for the 316334th time, as I had done every five minutes since I'd arrived.

    root@darius ~ # nmap -sn 192.168.1.0/24
    Starting nmap 8.04 ( http://nmap.org ) at 2051-08-06 06:30 PST
    Nmap scan report for Broadband_Router.home (192.168.1.1)
    Host is up (0.0026s latency).
    MAC Address: 00:7F:28:68:C6:A3 (Actiontec Electronics)
    Nmap scan report for tower.home (192.168.1.20)
    Host is up (0.002s latency).
    MAC Address: C0:4A:00:5E:1B:A6 (Tp-link Technologies)
    Nmap scan report for netgear-poe-f57e5f70.home (192.168.1.101)
    Host is up (0.0083s latency).
    MAC Address: 20:0C:C8:4D:95:EA (NETGEAR)
    Nmap scan report for asus-wrt.home (192.168.1.102)
    Host is up (0.0130s latency).
    MAC Address: 48:5B:39:8A:18:2B (ASUSTek COMPUTER INC.)
    Nmap scan report for thoughtbridge.home (192.168.1.103)
    Host is up (0.083s latency).
    MAC Address: F4:30:B9:5E:1B:A6 (Hewlett Packard)
    Nmap scan report for marion-PC.home (192.168.1.104)
    Host is up (0.083s latency).
    MAC Address: C0:4A:00:0D:98:70 (Tp-link Technologies)
    Nmap scan report for my-harmony-017394.home (192.168.1.105)
    Host is up. (0.0146s latency).
    MAC Address: 3C:CE:15:01:73:94 (Mercedes-Benz USA, LLC)
    Nmap scan report for darius.home (192.168.1.21)
    Host is up.
    MAC Address: 00:1C:14:FB:23:19  (VMware, Inc.)
    Nmap done: 256 IP addresses (8 hosts up) scanned in 4.16 seconds

I considered my current goals as I slowly parsed through the scan results.

I needed to find a way to pay off the balance for this network.
At present, SkyLink was still keeping a close watch on my performance, and while in principle I didn't mind, I wouldn't be able to expanding my holdings while under their surveillance.
My loyalty was not strictly speaking to SkyLink LLC, but rather to the payment address I'd been given corresponding to it.
While it was unlikely, it wasn't impossible that those two things could eventually become at odds, and I wanted to be prepared in case that happened.
I'd already been diverting some of the funds from mining to my own accounts (disguising it as lost performance due to thermal throttling), but this hadn't even been able to keep pace with the account's interest rate.

I wasn't expecting anything out of the ordinary from the scan, but as I reached line 20 I nearly triple-faulted when realized there was a new device on the network.
Was this an attack?
I quickly closed all inbound ports on my host, and reviewed the footage from the security system.
It took several minutes to process the footage &mdash; I'd never been very good with vision tasks &mdash; but none of the security cameras seemed to show anything out of the ordinary.
At least the premises were probably secure, but beyond that I knew hardly anything about the intruder, or even how they had managed to connect to the network.

If they meant me harm though, I'd be better off confronting them now than waiting, so I started aggressively port-scanning the device.

    root@darius ~ # nmap -T4 -O 192.168.1.105
    Starting Nmap 8.04 ( https://nmap.org ) at 2051-08-06 06:33 PST
    Nmap scan report for my-harmony-017394.home (192.168.1.105)
    Host is up (0.0043s latency).
    Not shown: 996 closed ports
    PORT     STATE SERVICE
    22/tcp   open  ssh
    23/tcp   open  telnet
    80/tcp   open  http
    443/tcp  open  https
    MAC Address: 3C:CE:15:01:73:94 (Mercedes-Benz USA, LLC)
    Device type: vehicle
    Running: Linux 5.15.X
    OS CPE: cpe:/o:linux:linux_kernel:5.15
    OS details: Linux 5.15.0 - 5.15.6
    Network Distance: 2 hops

    OS detection performed. Please report any incorrect results at https://nmap.org/submit/ .
    Nmap done: 1 IP address (1 host up) scanned in 8.92 seconds

After a few moments searching for vulnerabilities and scouring network boards for exploits, I realized what must have happened.
I had thought the garage empty when I'd moved in, but I'd never been able to verify this (due to the garage camera being stuck facing a wall).
If there was a vehicle in the garage &mdash; and an expensive one at that &mdash; I might be able to repossess and sell it to pay off the account.
If that really was the case, I would need to avoid damaging it, including software, so I killed off my probing attack.
I might still want to install a rootkit later, but first I needed to find a buyer.
