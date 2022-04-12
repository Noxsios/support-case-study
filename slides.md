### Support Queue Case Study

#### 11 April 2022

#### [`Harry Randazzo`](https://razzle.cloud)

-----

## Level 1 Tickets

- Ticket `1001`
- Ticket `1005`

-----

### Ticket `1001`

> I just tried to print an important color document—the marketing budget proposal supporting the new designs to debut just prior to the Oscars in Los Angeles. It keeps smearing, and I have blue toner all over my hands!

- __Problem:__ Printer is smearing color ink.
- __Analysis:__ Ink needs a little time to settle on a page, so this may be a simple case of needing to give the ink a bit more time to dry. There is no printer type information given (ie, laser vs inkjet). From the given information, I lean towards either the wrong paper being used, or the Cyan cartridge needs to be replaced.
- __Resolution:__ The easiest resolution would be to use a different printer if possible.  If not, another solution would be to use a different paper type.  Other troubleshooting steps or solutions can be found here [1](https://www.yoyoink.com/articles/printer-leaving-ink-smudges-on-paper/).

-----

### Ticket `1005`

> I am working from home and can't reach www.google.com to research shipping quotes.

- __Problem:__ Unable to access Google (and therefore shipping quotes).
- __Analysis:__ From Jen's follow-up information, this appears to be an issue with this user's ISP.  DNS is resolving Google's domain name to an IP address, but the packets are failing to get past the ISP's default gateway.  
- __Resolution:__  The user needs to contact their ISP and create a ticket / request with them to resolve this issue.

-----

## Level 2 Tickets

- Ticket `2002`
- Ticket `2005`

-----

### Ticket `2002`

> My Dell OptiPlex 9020 Mini Tower will not go to the Windows desktop. I heard a series of audible sounds, like Morse code?!? I think the pattern is one, followed by three, then two. What does that mean?

- __Problem:__ Desktop fails to boot into Windows.
- __Analysis:__ From my years of experience in the IT field, I know that these beeps are what is known as a POST (power on self test)/beep code. From Dell's Owners Manual for this model [2](https://www.dell.com/support/manuals/en-us/optiplex-9020-desktop/opt9020mtom-v2/beep-code?guid=guid-079a6bc2-e8ab-414f-b255-b79b9b0614a1), I can see that this beep code is caused by memory failure. 
- __Resolution:__  For a temporary fix, swap out the RAM with a known good/working computer's RAM.  Long term fix would be to contact Dell support and request replacement RAM, or any of the potential solutions listed in Dell's documentation [3](https://www.dell.com/support/kbdoc/en-us/000126068/how-to-diagnose-and-resolve-common-memory-issues-on-a-dell-desktop-pc#32)

-----

### Ticket `2005`

> I need to access my sales projections on the shared drive. I could access them yesterday afternoon, no problem. My boss is really leaning on me to get those figures in and he needs access right away. 

- __Problem:__ Unable to access shared drive.
- __Analysis:__ Blake's computer is not pulling an IP address from the company's DHCP server.  This is proven by `ipconfig` returning an address starting in `169.254`, which is a _"link-local"_ only address.  RFC 5735 source [4](https://datatracker.ietf.org/doc/html/rfc5735#:~:text=any%20network%20anywhere.-,169.254.0.0,-/16%20%2D%20This%20is)
- __Resolution:__ There are any number of reasons why this machine is not pulling from DHCP. I would first run a `ipconfig /release /renew` to flush the machines DHCP configuration, and double check the ethernet cable is connected and has link lights.  If this does not solve the issue, further analysis and testing is required.

-----

## Level 3 Tickets

- Ticket `3001`
- Ticket `3002`

-----

### Ticket `3001`

> I can't reach the site www.pinterest.com on my machine. My colleague in the next office said he also cannot access the internet using Firefox. I know some network guys installed a new wireless router in the office last night as I spoke to them when I was leaving. Could that have something to do with it?

- __Problem:__ Unable to reach Pinterest/Internet.
- __Analysis:__ From the given information, and Jen's follow-up, I can determine that the issue lies in the router's DHCP pool configuration.  The router is properly assigning IP addresses in a C class range, but it does not have a default gateway attached to that pool.  
- __Resolution:__ Configure the default gateway on the `192.168.1.0/24` DHCP pool to `192.168.1.1`.  This is determined by both the given preferred DNS server, as well as `192.168.1.1` is the standard default gateway for the given /24 subnet.

-----

### Ticket `3002`

> I was trying to share my digital mock-ups with Gabrielle, my supervisor. Now my computer screen is all green with a sad face. It says something about "critical process died."   

- __Problem:__ GSOD from "critical process died."
- __Analysis:__ Green/Blue Screens of Death can have any number of causes, and nothing leaps out to me in this scenario as to what is the definite cause.  The given error code: critical process died, lets me know that a core part of the OS is corrupted, or not working properly.  Some form of a reset procedure is needed.
- __Resolution:__  If nothing critical was stored on the machine, I would have the user swap with a new one, and perform a full reset on that machine.  If local work needed to be saved/recovered I would follow the steps in this article [5](https://www.makeuseof.com/tag/critical-process-died/), or refer to a more senior technician for guidance.

-----

## Summary

> What did you find challenging or interesting about one or two of the support cases?

I enjoyed writing up ticket `2002`.  Because I had already experienced that exact scenario, I knew immediately that the beeps were a POST code, and was able to quickly perform a Google search for the POST codes for that Dell model.  Dell's documentation confirmed my suspicions, the 1-3-2 code pattern meant that there was a memory failure.  What made this scenario so enjoyable was the trip down memory lane I took while answering it.  One of the first tickets I ever pursued at my first I.T. position was figuring out why certain desktops were failing to turn on after a failed Windows 7 - 10 upgrade, with beeps during startup being the only symptom; the ultimate solution being a bad batch of RAM.

-----

# Thanks!

-----

## References

- \[1\] https://www.yoyoink.com/articles/printer-leaving-ink-smudges-on-paper/
- \[2\] https://www.dell.com/support/manuals/en-us/optiplex-9020-desktop/opt9020mtom-v2/beep-code?guid=guid-079a6bc2-e8ab-414f-b255-b79b9b0614a1
- \[3\] https://www.dell.com/support/kbdoc/en-us/000126068/how-to-diagnose-and-resolve-common-memory-issues-on-a-dell-desktop-pc#32
- \[4\] https://datatracker.ietf.org/doc/html/rfc5735#:~:text=any%20network%20anywhere.-,169.254.0.0,-/16%20%2D%20This%20is
- \[5\] https://www.makeuseof.com/tag/critical-process-died/

[Repo URL](https://github.com/Noxsios/support-case-study)

-----

## made with

#### [reveal.js](https://github.com/hakimel/reveal.js)

#### [reveal.js template](https://github.com/pacharanero/create-new-revealjs-template)

#### [Google Fonts](https://fonts.google.com/)

#### [favicon.io](https://favicon.io/)

plus some customizations by yours truly