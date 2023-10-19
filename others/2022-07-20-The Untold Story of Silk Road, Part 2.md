---
layout: post
toc: true
title: "The Untold Story of Silk Road, Part 2"
categories: 人物
tags: [Ross Ulbricht,Silk Road]
author:
  - Joshuan Bearman
---

![img](https://interactive.wired.com/www-wired-com__2015__05__silk-road-2/silk_road_mobile_pt2.jpg)

*Read part I of this story [here](https://www.wired.com/2015/04/silk-road-1/).*

## Thor

![chapter_1](https://interactive.wired.com/www-wired-com__2015__05__silk-road-2/chapter_11.svg)

*“I imagine that someday I may have a story written about my life and it would be good to have a detailed account of it.” —home/frosty/documents/ journal/2012/q1/january/week1*

THE DESCENT WAS stunning. Chris Tarbell, a special agent from the New York FBI office, was in a window seat, watching a green anomaly in a sea of blue as it resolved into Iceland’s severe, beautiful landscape. On approach to Keflavík International Airport, he could now see the city of Reykjavik coming into view. And just beyond that, perched on the edge of a moss-covered lava field: the massive matte-white box that housed the Thor Data Center. That’s why Tarbell and two US attorneys had come all this way. Thor was the home of a computer with a very important IP address, one that Tarbell and his FBI colleagues had discovered back in New York—the hidden server for a vast online criminal enterprise called Silk Road.

They’d been working on this case for months, as had federal agents across the country, in a wide-ranging digital manhunt for Dread Pirate Roberts: the mysterious proprietor of Silk Road, a clandestine online marketplace that functioned like an anonymous Amazon for criminal goods and services. Silk Road investigations had been launched by Homeland Security, the Secret Service, and the DEA office in Baltimore, where an agent named Carl Force had been working an undercover identity as a Silk Road smuggler for more than a year.

Tarbell and his team—known as Cyber Squad 2 (or CY2 for short and “the Deuce” for fun)—were relative newcomers to the case. The other agencies had dismissed the FBI, partly because of interagency bluster and partly because the traditional agents who thought casework was all guns and grime and grit had no respect for the eggheads from cybercrime. But in the midst of this enormous law enforcement effort—mostly fruitless so far—Tarbell and CY2 had found the first promising lead in the case.

Cybercrime agents spend a lot of time at their desks, and it was exciting to be in the field. Down below they could see Iceland’s fierce geology, all jutting rock built up from the water by volcanoes. Beneath the surrounding ocean are the massive cables that make the country an important location for web traffic; the island is nearly equidistant between North American and Europe, and its forbidding geography and climate reduce cooling costs and provide free geothermal power. One of the attorneys told Tarbell about Iceland’s tectonic forces—the North American and Eurasian plates, slowly tearing open a growing chasm. *Really puts you in your place*, Tarbell thought.

![Alt text](https://interactive.wired.com/www-wired-com__2015__05__silk-road-2/PQ_1.svg)

Once on the ground in Reykjavik, Tarbell and the lawyers met with their counterparts and explained why they’d come. Silk Road had eluded law enforcement for almost three years because it ran on Tor, a kind of cryptographic camouflage that made it nearly impossible to see the site’s users, vendors, or servers. Until Tarbell made a chance discovery.

His investigation had started entirely at his desk with virtual gumshoe diligence, poking around Tor’s IP publishing protocol and spending time on Silk Road looking for chatter about the site’s security. His lucky break came from a thread on Reddit: A user posted a warning that Silk Road’s IP address was “leaking”—visible to other computers. Dread Pirate Roberts (or DPR, as he was often called) had been alerted to the problem by a user but ignored the warning. Silk Road’s success was making DPR arrogant. He had let down his guard, confidently telling colleagues that the site would never be found.

Tarbell threw data at Silk Road, hoping to see the leak. He entered usernames with bad passwords (and vice versa) and pasted data into input fields—all the while using regular old freeware to analyze network traffic and collect the IPs communicating with his machine. Then he tested those. On June 5, 2013, after staring at IP addresses for hours, Tarbell pasted one of them—193.107.86.49—into a browser and suddenly there it was: the Silk Road Captcha field. He showed it to fellow agent Ilhwan Yum and to Tom Kiernan, the civilian computer technician who formed the technical backbone of the cybersquad. This was what the team had been waiting for: a misconfiguration somewhere on the site that revealed the real IP address of Silk Road, which Tarbell proceeded to trace all the way to the state-of-the-art facility in Iceland.

Tarbell had been to the island nation once before and knew some of the officials at the meeting. There was an Icelandic prosecutor present—Tarbell was mildly distracted by how attractive she was, with her fitted skirt, secretary glasses, and hair in a bun—and an attaché from the US embassy. It’s a delicate thing, making requests of another government—a US attorney had written up an official letters rogatory petition, requesting that Iceland honor the bureau’s investigative requests—but the Icelandic authorities were accommodating, and the meeting was over in an hour. Not long thereafter, an Icelandic police detachment entered the immaculate foyer of the Thor Data Center.



What kind of data center has a foyer? The kind that also has a gleaming glass front and a spotless floor and houses the world’s first zero-emission supercomputer. Cybercrime forensics often means untangling wires from machines stuck in some basement. Thor looked like the future. Past the foyer’s key card entry was a former airplane hangar in which sat a double-high shipping container, bright blue with silver ducts, full of servers. Inside were three rows of blades lined up floor to ceiling, flashing with blue lights. There was a chill in the air and the thrum of a thousand fans, all powered by Vulcan forces from the rock below. The Icelandic authorities found the correct box and discovered that it had a mirror drive, a duplicate set of contents. They pulled the mirror, returned to Reykjavik, and handed the drive to Tarbell. And just like that, he was holding Silk Road in his hand.

Even on first glance the site’s volume was surprising: On July 21, 2013, around the time Tarbell landed in Iceland, DPR’s account received 3,237 transfers totaling $19,459, which would give DPR an annualized income of more than $7 million. The data center also kept system logs for six months; they could see all the other computers that had recently communicated with this machine. It was an investigative windfall.

After returning to New York, Tarbell started unspooling the electronic threads that led from the Iceland machine to computers around the world. They looked at traffic recorded for port 22—the encrypted connection where admins log in—and discovered several non-Tor IPs: a backup near Philadelphia, a hosting proxy server in France, a VPN in Romania.

On the wall of the CY2 computer lab, Tarbell mounted an 8-foot sheet of plotter paper and constructed the classic crime investigation visual, with a skein of lines mapping the complicated relationship of leads and evidence. But rather than the traditional godfather surrounded by his capos, this chart centered around a server in Iceland and a sprawling cryptographic computer network.

Tarbell was a visual thinker; he liked to see the connections. One of those connections was to an IP address that was the last known login to the Silk Road VPN. Next to it Tarbell drew a question mark. A subpoena revealed the IP’s physical location: Café Luna, Sacramento Street, San Francisco.

## Joshua Terrey

![chapter_1](https://interactive.wired.com/www-wired-com__2015__05__silk-road-2/chapter_21.svg)

WHEN HOMELAND SECURITY agents showed up at Ross Ulbricht’s front door in San Francisco, his new roommates were surprised. They thought the quiet guy from Texas who’d just rented their extra room for a thousand bucks was named Joshua Terrey. The agents must have found that interesting, since Joshua Terrey wasn’t one of the nine names they’d found in a stash of fake IDs at the Canadian border customs office, all directed to this address and featuring Ross Ulbricht’s picture.

Ross had moved into this house after leaving Austin, where he’d grown up as a smart kid from a suburban family with an adventurous streak. Ross was handsome, charming, and always an overachiever, studying physics and engineering on scholarships. But he’d abandoned lab work to pursue an idea that brought together his technical smarts, entrepreneurial spirit, and newfound libertarian social philosophy: Silk Road. He’d come west, to the Mecca of startups, where he managed his powerful operation in secret.

Even though Ross had only recently moved into this sublet in West Portal, a neighborhood of single-family homes and strollers, he’d scored the master bedroom. His roommates thought that the guy named Josh, who had answered their Craigslist ad, was a currency trader. They did think it was weird that he had no cell phone, paid in cash, and was always on his computer. Neither friends nor family had any idea that Ross had a secret alter ego: Online he was Dread Pirate Roberts. Nor did they suspect that the young man who ran what began as a politically motivated black market had become the leader of a criminal organization, a ruthless operator who had decided to kill one of his employees as retribution for theft (and as a sacrifice necessary to protect his political objectives).

If Ross was nervous about being discovered when the Homeland Security agents interviewed him, he didn’t show it. He did not tell them he’d bought the colorful array of fake IDs so that he could covertly rent additional servers to deal with Silk Road’s exploding scale and security challenges. The IDs were high-quality counterfeits, holographic features and all. But now they were in the hands of the Homeland Security agents at the front door. Ross was polite but knew he could refuse any questions.

![Alt text](https://interactive.wired.com/www-wired-com__2015__05__silk-road-2/PQ_2.svg)

Before the agents left, Ross did volunteer that “hypothetically” anyone could have shipped drugs or fake IDs to him via a website called Silk Road. A strange thing to mention—and duly noted by the agents—but they weren’t there to talk about Silk Road, whatever that was. The agents left and took the fake IDs with them.

Ross was spooked by the visit. He moved again a short time later to another sublet, in the city’s Glen Park neighborhood, but decided to use his real name. One of his new roommates, Alex, liked Ross right away because he was charismatic and easy to talk to.

And, Alex observed, Ross’ focus was impressive. He wasn’t the type of guy to procrastinate watching cat videos on his Samsung 700z. He didn’t smoke or drink much, although he sometimes played his djembe, a west African drum and one of his few possessions. He never brought friends over and seemed not to have a single memento. Nor did Ross get mail. “Sometimes,” one roommate said to Alex, “I feel like Ross is hiding from someone.”

Still, they couldn’t have guessed that Ross, the new guy in their cheap share who liked giving hugs and hanging out shirtless, was sitting on their garage-sale furniture with that Samsung on his lap presiding over a criminal empire.

<video class="render-layer hide-mob hide-ipad hide-sm hide-med" data-js="parallaxTarget" data-play-on-scroll="" style="box-sizing: border-box; display: block; vertical-align: baseline; backface-visibility: hidden; perspective: 1000px; transform-style: preserve-3d; transform: translateZ(0px); max-width: 100%; transition: opacity 0.35s cubic-bezier(0.33, 0.66, 0.66, 1) 0s; width: 1730px;"></video>

## Uneasy Lies the Head

![chapter_1](https://interactive.wired.com/www-wired-com__2015__05__silk-road-2/chapter_31.svg)

“MONEY IS POWERFUL,” DPR wrote to the Silk Road faithful, “and it’s going to take power to effect the changes I want to see.” By that time, DPR was a millionaire many times over, but those resources, he told his followers, were for the revolution. Freedom, after all, needs financing.

DPR had founded Silk Road as a digital instantiation of the libertarian ideal: a frictionless marketplace where everyone had freedom as long as it didn’t impinge on someone else’s freedom. For DPR and the community that grew around him, Silk Road was about more than contraband; it was a movement. As Silk Road quickly grew, DPR’s pronouncements became more grandiose. He wrote that “every single transaction is a victory” in weakening the “thieving, murderous” state. What began as a belief in free choice came to sound like revolutionary dogma.

It made for ambitious business plans. DPR wanted to expand his liberty-fueled brand into an empire, with his own Silk Road–affiliated bitcoin exchange, credit union, and encrypted communication service. Buoyed by quick success, DPR shared the heady enthusiasm of the licit startup world. Whereas he’d once considered selling Silk Road for $1 billion, he told a reporter in a rare, encrypted chat interview that Silk Road was worth 10 figures, maybe 11.

But behind the scenes, Ross faced constant crises. There were technical problems, management issues, a quickly changing marketplace, and the volatility of bitcoin. There were scammers on the site. And even as Silk Road made more money, the cost to maintain it rose. Ross, feeling besieged from all sides, recorded his efforts in a log.

04/03/2013

*Spam scams have been gaining traction. Limited namespace and locked current accounts.*

Blackmail too was a problem. Hackers had figured out how to launch denial-of- service attacks on Silk Road, and DPR was forced to pay “protection” to the tune of $50,000 a week. In May 2013, hackers shut down the site for a week, and many users wondered if it was the work of a competitor. Atlantis, a new Tor-based illicit-goods bazaar, had just launched with a slick YouTube trailer and a group chat with reporters in which a spokesperson named Heisenberg offered the serious burn that Atlantis was the “Facebook to [Silk Road’s] MySpace.”

05/02/2013

*Attack continues. No word from attacker. Site is open, but occasionally tor crashes and has to be restarted.*

DPR’s own staff was growing, although it was hard to find reliable subalterns. Batman73—a dealer named Peter Nash in Australia—was a cokehead. Inigo ran the site’s book club, which DPR appreciated, but was the kind of guy who lived part-time on a boat, smoked a lot of weed, and was as organized as that lifestyle might suggest. DPR liked Libertas, though, and Smed was solid, offering rapid-response technical support.

05/03/2013

*Helping smed fight off attacker. Site is mostly down. I’m sick.*

The burden of leadership was getting to DPR, and his fluctuating moods played into the theory that the moniker was actually operated by multiple people. DPR encouraged this perception. In an interview with *Forbes*, he said that he was actually the successor to Silk Road’s creator. It worked. On Silk Road it became great speculative sport to decipher the many facets of DPR, with users believing they could even detect when the different DPRs took the reins.

“You are a busy guy. Actually I think you are going to kill yourself,” said a friendly message sent to DPR by a Silk Road vendor named Nob. “Take a vacation.” DPR believed that Nob was a Puerto Rican cartel middleman named Eladio Guzman, but he was in fact DEA agent Carl Force. Force had spent more than a year developing his undercover identity on Silk Road in an effort to get close to DPR. They’d become confidants, spending nights chatting at such length that DPR trusted Nob when he needed enforcement muscle.



It was Nob whom DPR hired to kill his employee, Curtis Green. Force then coerced Green into faking his own death as a ruse. Force was surprised to see DPR’s moral collapse up close, but then again, he’d seen this kind of thing before, during his younger DEA years in undercover. He too had experienced the temptations that came with a double identity. In fact, his secret life as a hard-partying operator had nearly destroyed his regular life. He’d left all that behind and recommitted himself to Christ. The Silk Road case was his first undercover role since those days, and it was a big one. Because of his tenure online as Nob, Force was able to carry out the supposed “hit” on Green, setting DPR up for a murder conspiracy indictment while at the same time cementing their relationship. Nob and DPR had become comrades-in-arms.

Now Nob wanted to capitalize on DPR’s apparent struggle. “You need a contingency plan,” Nob wrote. Force hoped that the mounting paranoia would eventually allow him to orchestrate what DPR would believe to be an escape—right into the arms of the DEA.

DPR confided his worries about “LE,” or law enforcement, not realizing that he was talking to the DEA. That might have been a lapse in judgment in a realm that was full of speculation about narcs and informants. But DPR wanted to believe his friend Nob. Silk Road, after all, was built on DPR’s confidence system. And besides, he was lonely. “I have no one to share my thoughts with,” DPR posted to the wider Silk Road community at one point. “Security does not permit it, so thanks for listening.”

05/26/2013

*Tried moving forum to multi .onion config, but leaked ip twice.*

DPR had also gotten lazy with his operational security. That diary he kept was a bad idea, for starters. Growing vanity had become a weakness. DPR’s self-taught programming was catching up with him as well, leaving holes in Tor’s invisibility cloak. And yet he would tell his admins there was nothing that could get traced back to them. When one user with a technical background private-messaged DPR to warn him that he should know the precise physical location of his servers, DPR brushed it aside. The tipster warned that the servers could be copied easily. Don’t worry, DPR said. The servers are secure.

## Labla

![chapter_1](https://interactive.wired.com/www-wired-com__2015__05__silk-road-2/chapter_41.svg)

BACK IN NEW York, Kiernan was busy re-creating the entire Silk Road system in their lab. Once it was configured, Tarbell and his team could access the system as superusers—seeing Silk Road as DPR—and learn the site’s mechanics, communications, and structure. It was thrilling, of course, to fire it up for the first time. They wondered what they would see. Tarbell could immediately appreciate DPR’s sense of industry, how hard he worked to expand and manage the site under incredible duress. Tarbell thought: *I guess he’s really earning that commission*.

It was impressive. Especially because Tarbell could tell that DPR was not a professional programmer. The server was a “noisy box,” clearly the work of an autodidact, a coding palimpsest that invited eventual discovery. The pseudo code was full of comments describing various technical experiments that were often run on the live server. Kiernan and Yum found the private messages, the forums, a bitcoin escrow account (from which DPR extracted his cut every Saturday night), and the main bitcoin server showing all vendor transactions.

They spent a lot of time in the lab, which they dubbed the War Room. It felt like college finals week in there, every day. The group would churn through Silk Road material, bringing lunch in from the deli downstairs and getting loopy by the afternoon, when Tarbell would call for a seltzer break and dance around with the bottle, singing the mellow gold classic “Afternoon Delight.” Over time the jokes got weirder, like when Yum put up a sign in the War Room that said: Lab1a. To the delight of the cybersquad, no one in the computer-illiterate realm of the FBI noticed that this was also leetspeak for some sensitive lady parts.

While Yum and Kiernan worked on the machines, Tarbell combed through 1,400 pages of DPR’s chat logs so as to really understand him. DPR was different things to different people, sometimes solicitous and businesslike, other times volatile and narcissistic. Eventually, he embraced murder as a necessary business practice.

![Alt text](https://interactive.wired.com/www-wired-com__2015__05__silk-road-2/PQ_3.svg)

Reading through DPR’s correspondence, Tarbell was surprised to find evidence of more hired assassinations, this time a response to blackmailers. It was a complicated scenario, but what Tarbell put together was that a user called FriendlyChemist was blackmailing DPR. Another user called Redandwhite, claiming to be a member of the Hells Angels, agreed to kill the blackmailer and, soon, others. For a handsome fee, of course.

DREAD PIRATE ROBERTS 3/27/2013 23:38

In my eyes, FriendlyChemist is a liability and I wouldn’t mind if he was executed … I have the following info:

Blake Krokoff

Lives in an apartment near White Rock Beach

Age: 34

Province: British Columbia

Wife + 3 kids

Always the businessman, DPR first invited the Hells Angels to become vendors on Silk Road, suggesting that Redand­white “read the wiki and forums.” Then the two got back to the cost of murder. Hit men apparently get a commission, according to this Hells Angel, if the target owes money. And if you want it to look like an accident, rates go up. A “clean hit” would cost about $300,000 (travel expenses included). DPR had sticker shock. After all, he’d only paid $80,000 for the Curtis Green hit. They haggled.

DREAD PIRATE ROBERTS 3/31/2013 8:59

Don’t want to be a pain here, but the price seems high. Not long ago, I had a clean hit done for $80k. Are the prices you quoted the best you can do?

REDANDWHITE 3/31/2013 11:16

I’m sorry, but we can’t do anything for that price. Best I can do is 150 and even that is pushing it.

In the interest of a “business relationship to be” the Hells Angels agreed to $150,000, or 1,655 bitcoins at the time. “Good luck and be safe” was DPR’s sign-off. The next day they debriefed.

REDANDWHITE 4/1/2013 22:06

Your problem has been taken care of … Rest easy though, because he won’t be blackmailing anyone again. Ever.

DREAD PIRATE ROBERTS 4/2/2013 00:55

Excellent work.

Tarbell had never seen anything like it. Here was a date- and time-stamped record of an entire criminal conspiracy as it unfolded. Turned out, Redandwhite told DPR, the blackmailer they killed was working with another guy known on Silk Road as Tony76, an infamous scammer. DPR didn’t hesitate to add him to the invoice. But Tony76 had housemates, and they were also involved. Maybe. Probably. Fine, DPR said. Get them too, and send photographic proof when the job is done. Meanwhile, DPR and Redandwhite spent some time troubleshooting the Hells Angels’ new chat app and privacy plug-in (“Please upload some screenshots of the settings”) while also planning and pricing (“no bulk discounts”) the next set of executions.

DREAD PIRATE ROBERTS 4/8/2013 18:50

I see your problem, you need port 9150, not 9151 … hmm … $500k in btc (3,000 @ $166/btc) has been sent to:

1MwvS1idEevZ5gd428TjL3hB2kHaBH9WTL

*A week later:*

REDANDWHITE 4/15/2013 10:11

That problem was dealt with.

Tarbell had been reading DPR’s correspondence in reverse order, and it was a strange thing, winding DPR’s life backward, from willing executioner back into idealist concerned with individual happiness. Some libertarian utopia, Tarbell thought. Although he wasn’t exactly surprised. All systems are vulnerable to corruption. Like the Internet itself, Tarbell thought, which began as a wonderful free prairie until people took advantage of that freedom. That’s why, he thought, it needed a sheriff. Up on Tarbell’s chart was an IP address with a name next to it: Frosty. This was an ID they’d found on the Iceland box. But they didn’t know what it meant until Yum and Kiernan cross-referenced it with some other evidence they’d collected. It turned out that the Silk Road servers had a login system that created one trusted computer for all the other machines, whose encryption keys all ended with frosty@frosty.



This meant that these computers shared one key friend, a single machine they could all talk to. Tarbell looked at his chart, festooned with a network topology. One of those nodes must be Frosty, and whoever sat at its keyboard was Dread Pirate Roberts.

As the case accelerated, Tarbell and his team started working long hours and weekends, jackets off, sleeves rolled up, long past the late dusks of summer. Tarbell actually loved that feeling on Friday at 5 pm when the air conditioner turned off automatically, the bullpen emptied and grew quiet, and he realized he’d been yelling all day but could now finally think.

Except that it was high summer. This being a federal building, the air-conditioning was on a timer. There’d be no circulation until Monday at 8:15 am. So by midday on Saturday, when the place was boiling, Tarbell would strip down to his underwear right at his desk.

The only room with constant air-conditioning was the lab, which had to be cooled because of the electronics. So one day, Tarbell and Yum made a desperate attempt to transport some of the chill to their desks using fans. It kind of worked. And there they sat in the middle of the FBI office, Tarbell sweating in his skivvies, with a football game on in the background and a series of fans stretching back to the well-cooled room where the ersatz Silk Road server hummed along, still keeping one key secret.

## Glen Park

![chapter_1](https://interactive.wired.com/www-wired-com__2015__05__silk-road-2/chapter_51.svg)

ROSS AND ALEX had become friends at the new house. Some nights they’d watch *King of the Hill* together, which reminded Ross of home, as it was a satire of a suburban Texas family like his own. Eventually Alex met that family when they all visited for a weekend. Ross’ parents seemed like nice folks who had raised a nice son. Settling into his room, Ross bought a few things to make life more comfortable: a lamp, a white leather couch from a garage sale, a standing desk for his Samsung. Online, however, things were less settled.

Across the country, Force, the DEA agent, was hoping to capitalize on DPR’s difficulties. He told DPR about “Kevin,” a supposed source of counter-intelligence on the growing Silk Road investigation. Nob explained that like all good cartel-affiliated players, he had “a guy on the inside,” a dirty Department of Justice employee on his payroll. Kevin, of course, was Force himself, and he had a lot of valuable information for DPR. Force told his supervisors that this informant game would make Nob seem omniscient and therefore more trusted. Citing Kevin, Nob fed DPR intel and predicted busts of Silk Road users and vendors. Things were getting dicey out there, Nob said. He pressed DPR on the need for a “30 seconds flat” escape plan, suggesting various itineraries.

DREAD: Can you explain to me why you chose this route?

NOB: Algeria does not extradite to the US.

NOB: Second you don’t want to take a plane out of your mother country.

Ross had in fact taken some preparatory steps. He flew to Dominica, a tiny tax haven island in the Caribbean, and started an application for “economic citizenship.” He tried to cultivate successors in case flight became necessary. DPR had created a special forum called Staff Chat for his elite admins, including Batman73, Inigo, and a newcomer called Cirrus. DPR told his admins how the pressure was getting to him, how he wanted time away. Even amid the rising chaos swirling around Silk Road, DPR started taking days off, leaving daily operations to his lieutenants. Ross spent a weekend with his old flame Julia, a free-spirited and sensual young photographer he’d met at a drum circle in grad school.

She flew in from Austin, and it felt like old times for the two of them, but also different. Ross still lived frugally in the Glen Park house, wore a faded red sweater all the time, and cooked his paleo diet, but he seemed happier. They had lots of sex, went dancing, and roamed the city, ending up one day on the cliffs overlooking the Pacific. In the distance, the Golden Gate Bridge rose beneath the lifting fog, catching the sun. Julia looked gamely over her shoulder at Ross and decided it was a good time to get topless. She rolled down her yellow sundress and Ross took photos. She didn’t care when a couple of hikers stumbled onto their soft-core pictorial. Ross stopped shooting and they ran off together, giggling, back toward the city.

Ross started spending more time with his housemates. One day he went to a nearby park with the girl who lived across the hall and hung out on the grass with her and her two long-haired Chihuahuas.

Marring the greenery, Ross noticed, was a piece of blue plastic stuck in a tree. A dedicated anti-litterbug, Ross climbed up to retrieve it. Back at the house he discovered he’d gotten a bad case of poison oak and needed plenty of calamine lotion for the spreading rash. He moped for days, still shirtless, but now bright red, standing out like a squad car’s flasher against his white leather couch.

<video class="render-layer hide-mob hide-ipad hide-sm hide-med" data-js="parallaxTarget" data-play-on-scroll="" style="box-sizing: border-box; display: block; vertical-align: baseline; backface-visibility: hidden; perspective: 1000px; transform-style: preserve-3d; transform: translateZ(0px); max-width: 100%; transition: opacity 0.35s cubic-bezier(0.33, 0.66, 0.66, 1) 0s; width: 1730px;"></video>

## ($curl_error )

![chapter_1](https://interactive.wired.com/www-wired-com__2015__05__silk-road-2/chapter_61.svg)

THE WHEELS OF the federal government grind slowly but exceedingly fine. As Ross had written in his diary in 2011, when Silk Road came to the attention of the US Senate, he knew he had awakened “the biggest force-wielding organization on the planet.” Two years later, Chris Tarbell was lying on his bed at home, with his wife, Sabrina, cooking in the other room and his kids tearing around the house so loudly he had to turn up his phone to hear the name: “Ross Ulbricht.”

Tarbell was on a conference call with the US attorney assigned to the case and an agent from Homeland Security Investigations named Jared Der-Yeghiayan. Der-Yeghiayan was stationed at the customs office in Chicago’s O’Hare International Airport and had been finding retail-size drug parcels in mail on foreign flights, all carefully wrapped, with customer service slips and return addresses to StudyAbroad.com. This, Der-Yeghiayan discovered, was a vendor on a thing called Silk Road.

Der-Yeghiayan familiarized himself with the site and learned Silk Road well enough to bust a low-level admin named Cirrus and persuade her to cooperate, allowing him to take over her account. Now Cirrus was rising through the ranks, becoming a trusted insider. Tarbell invited Der-Yeghiayan to New York to work with CY2.

Another new agent from the IRS, Gary Alford, had joined the conversation that day. As it happened, he’d been in Tarbell’s War Room earlier—Alford and the US attorney were working on a separate bitcoin case—and he’d taken a quick look at the chart. “Oh, that’s funny,” Alford said. He had worked with a different agency on Silk Road for a bit. “I had a lead in San Francisco,” he told the team. “I’ll look it up.”

![Alt text](https://interactive.wired.com/www-wired-com__2015__05__silk-road-2/PQ_4.svg)

He did and then explained to everyone what he’d found. Some months earlier, Alford had figured that whoever had started Silk Road had tried to drum up interest on regular websites with like-minded audiences. He searched for Tor URLs around the time of the site’s first appearance and found a mention in a Shroomery.org forum on January 27, 2011, days after the Silk Road launch. A user named Altoid talked up this exciting new “service that claims to allow you to buy and sell anything online anonymously.”

Googling elsewhere for the username Altoid revealed a question about database programming posted on Stack Overflow, dated March 16, 2013, asking, “How do I connect to a Tor hidden service using curl in php?” The email listed was *rossulbricht@gmail.com*. A minute later, that user changed the alias to Frosty.

The IRS didn’t know what any of this meant, so that’s where it ended. The info sat in a case file until dumb luck put Alford in Tarbell’s lab, whose wall was a map where all roads led to Frosty. Der-Yeghiayan ran the name Ross Ulbricht through the federal database and found the Homeland Security report on Ross’ fake IDs. A quick search for his last known address showed that he had lived half a block away from Café Luna, the San Francisco node on his chart (the site where an administrator had logged in to the Silk Road VPN).

Tarbell was ecstatic. Finally, here was the missing piece, the end of the digital trail. Tarbell thought it was funny that these clues were sitting out in the open. In the end, one of the best law enforcement tools was Google. It seemed clear that Ross had no idea Silk Road would become such a success and was careless early on. And in the era of informational perpetuity, you only have to be careless once.

A quick tour through Ross’ social media presence revealed a digital portrait with an incredible likeness to Dread Pirate Roberts’. His LinkedIn profile was full of the same libertarian rhetoric. On YouTube he’d favorited videos from the Mises Institute, the political touchstone beloved by DPR. On Google+ (where his profile described him as “spunky, funky, not so chunky”) he asked, “Anyone know someone that works for UPS, FedEx, or DHL?” In the lab, Kiernan found code on the Silk Road server that matched lines posted by Ross on Stack Overflow.

“We found the guy,” Tarbell told his department supervisor the next day.

They put in a request to the surveillance team to send two agents to San Francisco, to get eyes on Ross. They watched him, in that house he shared with Alex, working late on encrypted wireless. Sometimes he headed out with his laptop, like practically everyone else in San Francisco, and occupied a café table to work with coffee at his side.



An electronic wiretap on Ross’ email would require a court order—but at that point there wasn’t probable cause to search the account. So they decided to use the physical surveillance to see if they could line up Ross’ Internet usage with DPR’s activity on Silk Road. The activity matched; DPR and Ross were in lockstep. Every time Ross turned on his computer, DPR logged on to Silk Road. When he closed it, DPR logged out. Over weeks, the pattern was consistent. At his house, in cafés, in the morning or late evening, Ross and DPR were electronically aligned. When DPR would say he was taking the afternoon off, physical surveillance would watch Ross going to the park with his housemate and her Chihuahuas, lying on the grass, and getting poison oak by climbing into a tree to pull some blue plastic from the branches.

Tarbell started planning. This would be a complicated operation, seizing the site’s bitcoins undetected, taking control of Silk Road, and placing FBI people abroad—at the machine in Iceland and at another in France. Tarbell was also worried they might accidentally tip off Ross. He even wondered why Ross hadn’t bolted already. Der-Yeghiayan, online as Cirrus, was in DPR’s inner circle and knew that he was feeling extreme pressure. Tarbell thought Ross was clearly smart enough to get out while he could. In fact, Force, as Nob, was actively encouraging DPR to flee. Force had been sidelined, but his final play was to convince the digital kingpin to meet him at some airport, under the guise of providing safe passage, and take him into custody. To juice DPR’s flight instinct, Force pointed out that were he to be caught, prison would not be a safe place.

NOB: You are like one of my family. But I have to tell you that i have had several people killed who were sent to jail. It is very easy and cheap.

But Ross wasn’t going anywhere. His hubris had only grown, based on his belief in Tor and his own intellect. He thought he was invincible. Even as warning signs flashed all around him and the Feds loomed on the horizon, Ross told a potential employee that they would never get caught. “Realistically,” he said, “the only way for them to prove anything would be for them to watch you log in and do your work.”

On the evening of September 28, the FBI’s surveillance team watched DPR log off as Ross stopped working, closed his computer, left the house with his housemates, and headed for the beach.

## Stay Positive

![chapter_1](https://interactive.wired.com/www-wired-com__2015__05__silk-road-2/chapter_71.svg)

IT LOOKED LIKE a brochure for San Francisco living, a group of kids sitting around a campfire at Ocean Beach beneath a crescent moon, listening to their friend Ross play his djembe. This was the first weekend of Indian summer, that glorious time in San Francisco when everyone ventures outside and you can sit in the sand within sight of Golden Gate Park and listen to the dark waves crash on the shore. Alex opened champagne, and Ross drank Tecates and drummed along with a dude playing “Wonderwall” on a guitar in the distance.

Toward midnight, the soiree was interrupted by three cops who told them to kill their fire. No bonfires after 11, they said. The group brought the party back to their house in Glen Park, drinking on the balcony. The guys in the next house over were on their balcony too, sharing some sangria, and passed a glass to Ross. He picked up Clementine, one of his housemate’s Chihuahuas, and cradled her in his scarf like a baby in a sling, toting her around while still drinking. Ross was blotto—the only time Alex saw him drunk—and smiling.

“Let’s go inside and jam,” Alex said. And jam they did, with Alex on the piano, Ross knocking his djembe again, and some other friends singing. The music settled into a hypnotically repeating melody, as late night jams do, until everyone drifted back to their rooms or out the door. “Ha,” Ross said, hand on his drum. “I can’t keep time.”

Online, Ross’ stewardship of Silk Road was also off-balance. He recorded his troubles in his log. Law enforcement was trying to infiltrate the forums. Some big vendors were getting busted. He was hemorrhaging money, starting with a government seizure of $2 million that May from Mt. Gox, the world’s biggest bitcoin exchange, where some key Silk Road accounts were held. Unrelated, Redandwhite convinced Ross to give him $500,000 and then disappeared. Even his friend Nob was still making veiled threats about how easy he would be to kill in jail.

Amid the chaos, DPR did talk to Libertas, one of his most trusted admins, about taking over Silk Road in case of emergency, but he never gave him server access. As he tried to keep his fingers in the dike, DPR confided his worries to Cirrus, who by the end of September was briefing a massive FBI team in San Francisco alongside Tarbell and Kiernan on the looming arrest of Ross Ulbricht.

If Ross knew the noose was tightening, he didn’t show it. In the days after the Ocean Beach party, he worked at his standing desk and called Julia in Austin, telling her he was going to visit in November. She sent him sultry photos, naked and dancing, as a preview. That Monday night, Ross wrote in his diary: “Had revelation about the need to eat well, get good sleep, and meditate so I can stay positive and productive.”

## Mastermind

![chapter_1](https://interactive.wired.com/www-wired-com__2015__05__silk-road-2/chapter_81.svg)

THE DINING ROOM of the San Francisco Airport Marriott was nearly empty at 6 am on Tuesday, October 1, 2013, when Tarbell met Kiernan and Der-Yeghiayan for another mediocre breakfast. Tarbell hadn’t slept much since arriving in San Francisco two days earlier. He and his New York team were edgy, having been in position waiting on the right moment. There was, as usual, a bureaucratic complication. Silk Road was Tarbell’s case, but he and CY2 were visitors at the pleasure of the San Francisco FBI office, and it was their assistant special agent in charge who had, as cops say, “designed the arrest.”

In classic form, the local FBI wanted to mount a dramatic raid on Ross’ house. Tarbell didn’t like this idea. He was worried about repeating the mistake made during his first big cybercrime case, when they arrested a hacktivist named Jeremy Hammond in Chicago. There, a SWAT team charged into Hammond’s apartment throwing flash grenades, immediately alerting Hammond in the back room, who shut the lid of his laptop, encrypting it forever.

This kind of operation didn’t need SWAT, Tarbell thought. It required finesse. To prosecute a cybercrime you needed direct evidence, which centered around Ross’ machine. Tarbell wanted to get Ross *in medias res*, with “fingers on the keys,” as they say in the trade. Tarbell had read in DPR’s chats about how secure his system was, how one keystroke would erase it all. There was no margin for error. They needed complete surprise.

Still, the assault strategy remained in place. “Thank you for your input,” the local FBI supervisor had told Tarbell. “Now here is the plan.” There would be three SWAT teams, one for each floor of the house. They would hit at dawn, gaining “fluid entry.” They couldn’t promise, but they would try to catch Ross while he was online.

“These are the fastest SWAT teams,” the supervisor said.

“But it doesn’t matter,” Tarbell said. “No one is fast enough.”

The arrest had been scheduled already, but Tarbell kept asking to delay so that they could catch Ross at one of his cafés. They’d seen him out working once but didn’t have “assets in position.” Tarbell was granted one delay, but that was it.

“Your equity is used up,” the San Francisco chief said. “No more favors.”

The SWAT assault was scheduled for 5 am on Thursday. The entire tactical force—dozens of agents—had gathered at an FBI cybercrime facility an hour south in San Jose, prepping their final review.

![chapter_1](https://interactive.wired.com/www-wired-com__2015__05__silk-road-2/break440w.svg)TARBELL DIDN’T MAKE it to San Jose. He and Der-Yeghiayan stopped by the San Francisco federal court building to amend the search warrant for Ross’ house. Kiernan and another officer were still in San Francisco as well, near Ross’ house in Glen Park. They had stayed in position, hoping, praying that Ross would come walking out that door with his laptop bag over his shoulder.

Tarbell decided to meet his team at Bello Coffee & Tea, a place Ross frequented just next to the Glen Park Branch Library. It was 1 pm. Sitting on the bench outside the café, Der-Yeghiayan went on Silk Road as Cirrus and saw that DPR was also logged in. Physical surveillance said Ross was still at home. Tarbell worried that in this leafy patch of San Francisco, he and his completely cop-looking crew, sitting around one laptop, would stand out. The group scattered and tried to act casual. Der-Yeghiayan went to a nearby market but then noticed his computer was nearly out of juice. So he went back to Bello, only to find the place full, with no free outlets. Tarbell returned to the bench, getting a chance to do some more worrying.

![Alt text](https://interactive.wired.com/www-wired-com__2015__05__silk-road-2/PQ_6B.svg)

Halfway across the Atlantic, Yum was with the Icelandic authorities, poised to enter the Thor Data Center and “escalate privilege” over the Silk Road marketplace and bitcoin servers. Then the team in France would take over Silk Road’s redirect server. Tarbell barely noticed the pleasant afternoon, instead staring at his BlackBerry, monitoring the constant scroll of messages tethering this whole delicate operation together.

At 2:45 pm, Der-Yeghiayan saw DPR log off. A few minutes later, Tarbell heard from surveillance: They had eyes on Ross leaving his house. He was wearing jeans and his red sweater and walking east. And carrying his computer. “He’s on the move,” they said.

*Holy fuck!* Tarbell thought. *He’s coming*. CY2 scattered again, this time in a giddy panic, zigzagging for cover like in a game of hide-and-seek. Tarbell left Der-Yeghiayan, still holding his laptop, to head down the street in the direction of Ross’ house. He felt high from the adrenaline. He didn’t realize Ross was on top of their position. Tarbell was rereading Ross’ description from the surveillance team when he looked up and saw Ross heading directly toward him. It felt like slow motion, coming face-to-face with the man he’d been tracking for months, resolving him from digital obscurity into a real live person walking up Diamond Street. Tarbell worried he’d get made. He was trying to act all Mister Undercover, but, Jesus, did he look like a cop. Ross walked right past him toward the café.

![chapter_1](https://interactive.wired.com/www-wired-com__2015__05__silk-road-2/break440w.svg)FROM ACROSS THE street, Der-Yeghiayan saw Ross duck into Bello. This seemed promising; they’d been hoping he’d sit down somewhere and log on to Silk Road, giving them an opportunity for a red-handed arrest. But Ross quickly left. It was probably the lack of outlets, Der-Yeghiayan imagined, looking at his own computer, which now had only 22 percent battery power left. A scary number, as he had to be connected online to verify DPR’s presence. Ross walked into the library next door.

*Oct 1, 2013 2:53 pm*

*From: Chris Tarbell*

*Subject: Re: Ross Ulbricht*

By email, Tarbell alerted his team. That message cc’d the whole operational group, which was midbrief, preparing for their raid, when they learned that the little squad of out-of-towners had ventured off-piste and cornered their man in the Glen Park Library. “We got him,” Tarbell said when his supervisor called from New York. “I’ll call you back in 10 minutes.”

With Der-Yeghiayan’s dying laptop, they watched Ross log on as DPR, then navigate into the marketplace, then the forum, then the elite admin chat where Cirrus was waiting to say hello. Tarbell knew the chief down south had surely mobilized. Fifty tacked-out federal agents were racing up Highway 101.

The cavalry was coming, and Tarbell wanted to get Ross before sirens showed up.

Kiernan and another agent had been in the library when Ross walked in. He went right by them and continued unaware past the periodicals and reference desk, beyond the romance novels, and settled in at a circular table near science fiction, on the second floor. The other agent assessed the tactical landscape up there, which was tough: Ross was sitting in a corner, with a view out the window and his back toward the wall. There was no obvious approach. It was Kiernan’s job to get Ross’ laptop, and it looked tricky. “Your sole job is to get the laptop,” Tarbell had drilled Kiernan. “Get the laptop. That’s why you’re here. Get the laptop. And keep it alive.”

![chapter_1](https://interactive.wired.com/www-wired-com__2015__05__silk-road-2/break440w.svg)TARBELL AND DER-YEGHIAYAN joined the action in the library, taking a spot on the stairs at a landing. Der-Yeghiayan was alarmed at how fast his battery was draining, but he kept communicating with DPR, making sure he logged in to the admin panel. Tarbell peered over the last step but couldn’t see much. Somewhere in the stacks was the other agent, but Tarbell wasn’t sure where. Everyone was communicating electronically, trying to coordinate, caught blind by the moment. Minutes ticked past. Der-Yeghiayan and DPR still chatted. His battery dropped further. Tarbell heard from the plainclothes surveillance team—they were in the library too. Tarbell didn’t know where exactly, because he didn’t know what they looked like. (Such is the very low profile kept by field surveillance.) A few miles away, the giant squad of SWAT teams was approaching San Francisco. All the local supervisors were in that armada, so technically Tarbell was in charge here on the ground. He took a deep breath and sent a message: “Let the guy run if you have to, but don’t let that computer close.” This was the moment. Tarbell didn’t know it, but the surveillance agents had designed a new arrest on the spot. He had no idea what would happen when he took a deep breath and told everyone: Go.

What unfolded next was a piece of improvisational theater. At 3:14 pm, DPR was typing away, writing to Cirrus. Just then, a middle-aged woman and man came toward Ross, ambling along in the kind of semihomeless shuffle you might often see in a San Francisco library. “Fuck you!” the woman yelled when they were directly behind Ross’ chair. As if they were a deranged couple about to fight, the man grabbed the woman by the collar and raised his fist.

Ross turned around for just a second, during which a hand reached across the table and grasped Ross’ Samsung. The petite, unassuming young Asian woman sitting across from Ross this whole time was, to everyone’s surprise, also an FBI agent. Ross lunged for his machine, a hair too late, as she turned like a quarterback for a quick handoff to Kiernan, who appeared out of nowhere—as instructed—to get the laptop. It took less than 10 seconds. From afar, Tarbell was astonished by the elegant choreography of the whole thing. It looked like the police procedural version of a tight jazz quartet.

While Ross was cuffed, Kiernan immediately sat down with Ross’ PC. It was open. He could see everything. The machine ID was Frosty. Ross was logged in to Silk Road as an administrator under an account called /Mastermind.

Kiernan also saw that Ross was torrenting some television. Of all things, he was downloading a segment from the previous night’s *Colbert Report*—an interview with Vince Gilligan, creator of *Breaking Bad*. The series finale had just aired, and Gilligan talked about the central theme of the show, how ordinary people are capable of terrible things. It took just two years for Walter White to turn from good-natured science teacher to liar, murderer, and master of a drug empire. Had Ross not been arrested he would have watched Gilligan say that yes, of course, Walter was doomed from the start. And everyone knew it but him.

<video class="render-layer hide-mob hide-ipad hide-sm hide-med" data-js="parallaxTarget" data-play-on-scroll="" style="box-sizing: border-box; display: block; vertical-align: baseline; backface-visibility: hidden; perspective: 1000px; transform-style: preserve-3d; transform: translateZ(0px); max-width: 100%; transition: opacity 0.35s cubic-bezier(0.33, 0.66, 0.66, 1) 0s; width: 1730px;"></video>

TARBELL STOOD WITH Ross for the first time, searched him, and put him into a surveillance van, where he read him his rights. Ross showed only a slight quiver in his lip and asked to see the charges. Tarbell presented him the warrant for Ross Ulbricht, aka Dread Pirate Roberts, aka DPR.

The rest of the force started arriving, black Suburbans and SWAT vehicles with lights blazing. Soon there were uniforms everywhere. Even though Tarbell’s improvised bust was a complete success, cops are cops, and the local FBI was fuming at Tarbell’s departure from protocol. He and his team, considered computer dorks back home in New York, had the strange satisfaction of being called “fuckin’ cowboys” by a swarm of guys bristling with gear and guns. Tarbell took it as a compliment. Then he put Ross in an FBI cruiser bound for the local jail.

Tarbell called Yum in Iceland to set that phase in motion. Yum shut down communication between the machine in the Thor Data Center and all the others around the world and then simply “changed possession” of the bitcoins by redirecting the digital pointers—this is how ownership of the currency works—from Silk Road to an FBI account. And voilà: All your coins are belong to us.

In France they discovered a digital booby trap: To redirect the Silk Road site itself required a delicate data process that could shut the box down; if restarted, the server was programmed to delete its key, basically self-destructing. But the trap was discovered, and gingerly evaded, and the machine succumbed. Thereafter, the Silk Road welcome page read: THIS HIDDEN SITE HAS BEEN SEIZED BY THE FEDERAL BUREAU OF INVESTIGATION. Within minutes, Reddit erupted. “Is this a joke?” someone posted, along with plenty of WTFs.

The arrest was such a coup that the Justice Department wanted to publicize it. They’d planned on staging a press conference in Washington, with attorney general Eric Holder himself, to make a strong statement about the government’s ability to take on cybercrime. But, as it happened, Ross was arrested on day one of the dramatic government shutdown, when one of his heroes, Rand Paul, along with other senators, held the federal budget hostage over the debt ceiling and forced Washington to go dark. There would be no Holder, no press conference, no government at all to celebrate its defeat of this libertarian, lawless challenge. The only public notice of Ross’ arrest was the release of the FBI’s initial 39-page complaint signed by Tarbell, cementing his new public persona as DPR’s digital Van Helsing.

In the car, Tarbell and Ross found themselves alone in the backseat. Tarbell had read so much about him, it was kind of like seeing an old pal. Tarbell talked about Ross’ life in a way that made it clear how much he knew. Ross was talkative but cagey. He seemed relaxed, as if relieved. Not in being caught, but just being with someone who possessed his secret. In front of Tarbell, he could be both Ross and DPR. He admitted nothing to Tarbell, but after a natural pause in the conversation, Ross said, “I don’t suppose $20 million can get me out of this?” It might have been the most authentic moment in Ross’ life in more than two years.

“No,” Tarbell said. He couldn’t resist needling him. “Even if it could, what about this guy?” He pointed at the driver, another FBI agent. “Have to take care of him too, right? How much money do you have?”

Ross looked ahead as they weaved toward the jail.

![chapter_1](https://interactive.wired.com/www-wired-com__2015__05__silk-road-2/break440w.svg)IN A VAN that doubled as a mobile lab, Kiernan worked forensics on Ross’ computer. He quickly found a mountain of evidence: a list of all the Silk Road servers and the names Ross had purchased them under, 144,000 bitcoins (more than enough to cover that $20 million bribe), a spreadsheet showing Silk Road accounting (including a capital-equipment entry for the purchase of that very laptop), and those diaries Ross kept, which detailed his hopes, fears, and foibles in operating a vast criminal conspiracy.

Kiernan also found a file called emergency .txt, with an unrealized escape procedure:

*Destroy laptop hard drive and hide/dispose*

*Hide memory stick*

*Go to end of train*

*Find place to live on craigslist for cash Create new identity (name, backstory)*

At Ross’ house, agents found a USB drive containing some Silk Road programming, but beyond that, little else. When Alex and the other roommates got home, they found the warrant on the coffee table.

Alex visited Ross in jail. He expected him to be shaken, but Ross was the same as always. He would soon be transferred to New York to face a seven-count indictment. It was hard for Alex to believe that the new guy in the extra room, his pal, was also the guy described in that warrant. The thought of Ross being guilty of even tripping someone, much less ordering a murder, seemed unlikely. He was always such a chill dude.



## All Rise

![chapter_1](https://interactive.wired.com/www-wired-com__2015__05__silk-road-2/chapter_9B2.svg)

ROSS WAS ARRAIGNED in federal court in New York a few months later, still seeming pretty chill. He pleaded not guilty. Like Alex, Ross’ friends and family couldn’t believe the charges. They were first shocked, then incensed. There emerged a familiar refrain: Ross was such a nice guy. There must be some mistake. Ross’ lawyer, Joshua Dratel, a seasoned, high-profile defense attorney who took on tough cases, made the same argument. His letter asking for bail was a moving collection of testimonials on Ross’ behalf: “good role model,” “reputation for fulfilling his obligations,” “fearless embrace of making the world a better place for everyone.” But the judge, citing flight risk, denied bail altogether.

Online, Ross became a cause célèbre. The libertarian and cypherpunk communities naturally felt that their champion had been martyred. The charges were ginned up, they thought, retribution for Ross having the temerity to challenge the government itself. Many a Reddit thread overflowed with outraged chatter and meticulous analysis of what the community insisted was overreach, flawed evidence, or a frame job. A solidarity site appeared: Freeross.org.

Ross and his attorney prepared a defense that basically amounted to “Wasn’t me.” They chose to occupy that narrative gap of uncertainty made possible by the ambiguity of identity online. Dread Pirate Roberts was just pixels, they said. Everyone knew there were many DPRs, they argued, returning to the lore of Silk Road and the symbolism of the alias.

It was a powerful idea. In the months leading up to the trial, the defense created a speculative froth about the very nature of identity, suggesting that Silk Road was an ongoing mystery. After all, everyone loves a whodunit. The case became like a crowdsourced mystery theater, with so many potential question marks hidden in the numbers and code.

Then the trial started. And the conspiratorial mindset was no match for clear, hard, overwhelming evidence. The courtroom was packed with Ross’ family, supportive spectators, and press as the biggest cybercrime trial in years unfolded in the federal district court building in downtown Manhattan. But armed with hundreds of exhibits, the prosecutors for the US attorney’s office presented an efficient, detailed case. They showed the diaries. Der-Yeghiayan explained how they caught Ross logged in as /Mastermind. They read aloud from DPR’s chats, stored on Ross’ computer, presenting the odd spectacle of gray-suited government lawyers addressing the court with choice narrations like “Squid gave me the support link, just let me know when I have access.” Outside, a vigil of protesters held signs, some reading “FREE ROSS”.

![Alt text](https://interactive.wired.com/www-wired-com__2015__05__silk-road-2/PQ_6.svg)

Ross, who declined to be interviewed for this story, was not charged with any murders. The case involving Green, which came out of Baltimore, was a separate indictment. (It is still pending.) The New York case dropped the five other murders after further investigation revealed that the whole thing was likely an elaborate catfish-as-blackmail scheme that snookered Ross out of a lot of money. But in all cases, the prosecution argued, Ross believed he was executing people, even receiving photographic evidence faked to prove it. For dramatic effect, the prosecutors read aloud selections of Ross’ conversations where he sounded like a heartless mafia boss.

It was a quick trial, 13 court days, faster than expected. Observers were surprised at the volume and detail of evidence, the kind you rarely see. To the end, Ross’ lawyer, Dratel, claimed it was a case of mistaken identity. (Like most criminal defendants, Ross himself didn’t testify.) Or rather, a qualified case of mistaken identity. Dratel caused quite a stir in his opening statements by admitting that Ross had indeed started Silk Road, but then quickly sold it off to some other unnamed figure. The attorney also claimed that Ross was later duped by this savvy character back into Silk Road to take the fall as the FBI closed in. To account for the vast sum of bitcoin wealth, Dratel explained that Ross was just a good currency trader. Then Yum took the stand to demonstrate precisely how Ross received all the bitcoin commissions from Silk Road during the entire tenure of Dread Pirate Roberts.

Ross’ family was surprised to hear the admission that he’d created Silk Road. Reporters could see it on his mother’s face. Lyn Ulbricht was a sympathetic figure, a caring mother leading a vigil for her son. She was smart and articulate and had become a vocal public figure in support of Ross. Throughout the trial she maintained that the jury would set Ross free.

This was more than a mother’s love. Lyn, like many supporters, just believed Ross. Which was understandable, to some degree, as Ross’ story was one of fluid identity. The prosecution said that Lyn’s good-natured son had turned into someone else. Lyn said that this someone, if he or she even existed, had been projected onto her son. Ross said nothing and remained a willing cipher, allowing everyone to project an identity onto him: To Alex, Ross was the cool new roommate; to Julia, a passionate lover and inspiration; to his family, the perpetual Eagle Scout; to Force, an unlikely friend in the night; to Tarbell, a smart kid defeated by his own arrogance. To the Southern District of New York US attorney’s office, Ross was simply the criminal conspirator Dread Pirate Roberts.

The likeliest reality is that Ross was all of those things. The open-minded seeker who conscientiously tried to pluck trash from a tree was Ross. As was the feverish visionary creating a virtual empire at any cost. Neither truth invalidated the other. Ross and DPR can (and did) coexist.

Amid all the murder minutiae, it’s possible to lose sight of the young idealist who sat down and coded his way into history. He was right about the war on drugs: It is a failure. And Silk Road was a perfectly natural response. There was a lot to like in the site’s original idea of an economically mediated utilitarian society. It is still easy to appreciate that Ross, the one who believed in choice and happiness. “Our basic rules are to treat others as you would wish to be treated,” Ross wrote as DPR on Silk Road.



But it didn’t take long for Ross’ programmed utopia to resort to programmatic violence. It’s an age-old story, the bloom and wilt of revolution. After tearing down the establishment’s walls, the new regime soon realizes the rubble would make a fine set of gallows. Just as Tarbell thought, all systems are the same. At the beginning of Silk Road, what Ross created was just a system. Then, at a certain point, it became *his* system—at which moment the system was doomed.

Silk Road offers a neat political parable for the rising libertarian tide in Washington and the smug pride of today’s Silicon Valley, where self-appointed revolutionaries of all stripes believe their powers allow them to transcend traditional human boundaries, including their own mortality. In a way, Silk Road is the dark mirror of *The Social Network*, a wild technological success story taken to its logically extreme conclusion.

Force watched from afar in Baltimore. Having lost his big career case, he acknowledged that the FBI “won fair and square,” and he had left the DEA by the time the trial started. But Force had a lot of sympathy for the guy he’d spent so much time with in late-night chats. As a man who was saved from the temptations of undercover work, Force believed that everyone was a sinner. He also identified with Ross. “I’m no different than him,” Force said. “It easily could’ve went the other way.” No one is either perfectly good or perfectly evil. People occupy a space right on each side of the line. And sometimes, without knowing it, you switch sides.

Force’s words rang truer than anyone knew. In an incredible twist, Force, along with a Secret Service agent on his team, was also indicted and arrested this past March for running an elaborate series of rackets and thefts on Silk Road. The 95-page indictment alleged that they stole bitcoins from Silk Road and other exchanges (the digital equivalent of keeping the suitcase full of cash after a dockside heroin bust); pocketed $50,000 from DPR for intel services from “Kevin”; laundered at least half a million of that (some of which made it to Panama); and served a false subpoena on a digital currency exchange when they questioned his transactions and froze his account. It was, in fact, when all this came to the attention of the Department of Justice that Force left the DEA. “In retrospect,” Tarbell said when he heard about the investigation of Force, “it’s as if you found out at the end of *Breaking Bad* that Hank was dirty the whole time.”

In retrospect, a lot of Force’s story takes on a different light. Ironically, he had warned DPR about the danger of double identity, but if this indictment is true he seems to have fallen prey to it himself. Force allegedly operated online not only as Nob but had also created several other identities and used them to blackmail DPR with law enforcement information for at least $100,000. Like Ross, Force must have believed in the secrecy of Tor. During the sting operation with Curtis Green, Force even told Green he thought the Silk Road servers would never be found. But they were, and after they documented Ross’ misdeeds, they also revealed that it was Force and the Secret Service agent who had stolen $350,000 in bitcoins from Silk Road—the theft that led Ross to put the hit on Curtis Green. None of this emerged during Ross’ trial because Force’s case was at odds with the FBI investigation and part of a different indictment. But if true, Force’s fall mirrors the path of DPR. It was during the Green sting that Force took his first corrupt step, and DPR became a true criminal by ordering murder. Their simultaneous moral turns, so intertwined, reinforced the one theme that barely appeared during Ross’ trial: how easy it is to forget the solidity and consequences of the real world when you live online.

The jury in *USA v. Ulbricht* was out for barely four hours. And that included lunch. They returned to the assembled courtroom and read the verdict: guilty on all seven counts. Ross’ family looked stricken. A sympathizer stood up and yelled, “Ross is a hero!” Ross was led from the court. Outside, Dratel was set upon by reporters. He vowed an appeal. The press gaggle jockeyed for position and fired questions. Some were bloggers who sided with Silk Road. As news spread online, partisans continued the fight, arguing over the identity of Ross and Dread Pirate Roberts, echoing what Dratel said to the jury in his closing statement: The Internet is a place of confusion, where nothing is what it seems.

Ross returned to jail, where, his mother liked to explain, he had been teaching yoga to other prisoners and doing a lot of reading. Alex sent him a printout of the short story “Man of the Crowd” by Edgar Allen Poe. Alex thought it seemed fitting, as the story is about a man in detective mode following someone he calls a “genius of deep crime” through the streets. But there is confusion in the chase. And a hint that the pursuer realizes that the man he’s after is, in fact, himself. Yet this other self remains beyond his grasp, “like a book that cannot be read.” As night falls, the man finally gives up the pursuit and watches the unknowable shadow disappear into the crowd.

*This article includes reporting by Nick Bilton, whose book on the Silk Road case will appear in 2016.*

*This story appears in the June 2015 issue of WIRED.*