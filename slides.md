### Support Queue Case Study

#### 11 Apr 2022

#### [`Harry Randazzo`](https://razzle.cloud)

<small>Press the play button below to start the audio.</small>

-----

Navigate using your arrow keys. If you see a &#8681; in the bottom right nav there is content below. Try it now!

---

## Nice!

To view all slides press the `ESC` key, otherwise press `>` to move to the next slide.

-----

## Level 1 Tickets

- Ticket `1001`
- Ticket `1005`

-----

### Ticket `1001`

> I just tried to print an important color document—the marketing budget proposal supporting the new designs to debut just prior to the Oscars in Los Angeles. It keeps smearing, and I have blue toner all over my hands!

- __Problem:__ Printer is smearing color ink.
- __Analysis:__ Ink needs a little time to settle on a page, so this may be a simple case of needing to give the ink a bit more time to dry. There is no printer type information given (ie, laser vs inkjet). From the given information, I lean towards either the wrong paper being used, or the Cyan cartridge needs to be replaced.
- __Resolution:__ The easiest resolution would be to use a different printer if possible.  If not, another soultion would be to use a different paper type.  Other troubleshooting steps or solutions can be found here [1](https://www.yoyoink.com/articles/printer-leaving-ink-smudges-on-paper/).

-----

### Ticket `1005`

> I am working from home and can't reach www.google.com to research shipping quotes.

- __Problem:__ Unable to access Google (and therefore shipping quotes).
- __Analysis:__ ISP is down.
- __Resolution:__

> TODO COME BACK

-----

## Level 2 Tickets

- Ticket `2002`
- Ticket `2005`

-----

### Ticket `2002`

> My Dell OptiPlex 9020 Mini Tower will not go to the Windows desktop. I heard a series of audible sounds, like Morse code?!? I think the pattern is one, followed by three, then two. What does that mean?

- __Problem:__ Desktop fails to boot into Windows.
- __Analysis:__ From my years of experience in the IT field, I know that these beeps are what is known as a POST (power on self test)/beep code. From Dell's Owners Manual for this model [2](https://www.dell.com/support/manuals/en-us/optiplex-9020-desktop/opt9020mtom-v2/beep-code?guid=guid-079a6bc2-e8ab-414f-b255-b79b9b0614a1), I can see that this beep code is caused by memory failure. 
- __Resolution:__  For a temporary fix, swap out the RAM with a known good/working computer's RAM.  Long term fix would be to contact Dell support and request replacement RAM. [Source](https://www.dell.com/support/kbdoc/en-us/000126068/how-to-diagnose-and-resolve-common-memory-issues-on-a-dell-desktop-pc#32)

-----

### Ticket `2005`

> I need to access my sales projections on the shared drive. I could access them yesterday afternoon, no problem. My boss is really leaning on me to get those figures in and he needs access right away. 

- __Problem:__ Unable to access shared drive.
- __Analysis:__ Blake's computer is not pulling an IP address from the company's DHCP server.  This is proven by `ipconfig` returning an address starting in `169.254`, which is a _"link-local"_ only address.  RFC 5735 source [3](https://datatracker.ietf.org/doc/html/rfc5735#:~:text=any%20network%20anywhere.-,169.254.0.0,-/16%20%2D%20This%20is)
- __Resolution:__ There are any number of reasons why this machine is not pulling from DHCP. I would first run a `ipconfig /release /renew` to flush the machines DHCP configuration, and double check the ethernet cable is connected and has link lights.  If this does not solve the issue, further analysis and testing is required.

-----

## Level 3 Tickets

- Ticket `3001`
- Ticket

-----

### Ticket `3001`

> I can't reach the site www.pinterest.com on my machine. My colleague in the next office said he also cannot access the internet using Firefox. I know some network guys installed a new wireless router in the office last night as I spoke to them when I was leaving. Could that have something to do with it?

- __Problem:__ Unable to reach Pinterest/Internet.
- __Analysis:__ From the given information, and Jen's follow-up, I can determine that the issue lies in the router's DHCP pool configuration.  The router is properly assigning IP addresses in a C class range, but it does not have a default gateway attached to that pool.  
- __Resolution:__ Configure the default gateway on the `192.168.1.0/24` DHCP pool to `192.168.1.1`.  This is determined by both the given preferred DNS server, as well as `192.168.1.1` is the standard default gateway for the given /24 subnet.

-----

### Ticket Title + `number`

> scenario

- __Problem:__
- __Analysis:__
- __Resolution:__

-----

## Summary

> What did you find challenging or interesting about one or two of the support cases?

-----

# Thanks!

-----

## References

- \[1\] https://www.yoyoink.com/articles/printer-leaving-ink-smudges-on-paper/
- \[2\] https://www.dell.com/support/manuals/en-us/optiplex-9020-desktop/opt9020mtom-v2/beep-code?guid=guid-079a6bc2-e8ab-414f-b255-b79b9b0614a1
- \[3\] https://datatracker.ietf.org/doc/html/rfc5735#:~:text=any%20network%20anywhere.-,169.254.0.0,-/16%20%2D%20This%20is
- 

[Repo URL](https://github.com/Noxsios/support-case-study)

-----

## made with

#### [reveal.js](https://github.com/hakimel/reveal.js)

#### [reveal.js template](https://github.com/pacharanero/create-new-revealjs-template)

#### [Google Fonts](https://fonts.google.com/)

#### [favicon.io](https://favicon.io/)

plus some customizations by yours truly