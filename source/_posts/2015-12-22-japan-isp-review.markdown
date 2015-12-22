---
layout: post
title: "Japanese ISP review"
date: 2015-12-22 10:30:02 +0900
comments: true
categories: 
---

# Introduction
This page contains a review of four of the big internet service providers in Japan, all based on NTT fiber. All of the ISPs showed approximately the same behavior during off-peak times, but during the peak time slot of 9 p.m. to midnight on weeknights they showed **vastly different performance**. The measurements below indicate that many ISPs in Japan are doing **extremely heavy packet shaping** during peak usage periods, presumably to cut costs on infrastructure. With the exception of OCN (which is fantastic), I found all of the ISPs to be unusable, and strongly caution against using them.

このページではNTT光回線をご利用して、４つのプロバイダーをレビューさせていただきます。夜間帯以外には差がほとんどなかったということで、21時～24時の夜間帯のみの測定や評価を発表します。下記のデータによって、日本ではビデオストリーミングやp2pのトラフィックシェーピングを非常に厳しく行っているプルバイダーが大勢いるという結論ができるでしょう。この４つのプロバイダーの中で夜間帯にOCN以外のISPは全て使えないぐらい遅かったです。レビュー内容自体は英語ですが、誰かに役に立てば嬉しいと思っていますので、是非ご参考ください。

# Choice of ISPs
These are the ISPs that I measured. I encourage any readers of this to send me their own reviews for inclusion.

* Asahi.net
* Biglobe
* Yahoo
* OCN
 
## Motivation
When I first moved into my current apartment in 2013, I signed up with Asahi.net as my provider because they were the cheapest one that didn't look dodgy. The service quality was fine, and they actually had *really* good customer service, so I didn't have any reason to change. Then one day in September 2015, I got a notice in the mail that the cost was going to increase from 550yen to 700yen from December. Shortly after that, I noticed that *the quality of service dropped significantly*, to the point that my internet actually became unusable.

I therefore decided to change ISP in the hope that I could fix my internetz. I had to try *3 different ISPs* until I found one (OCN) that was acceptable for my purposes. All of the other ISPs are doing such heavy traffic shaping on streaming video content and p2p that they are simply unusable. Since you have to pay for a whole month of usage for every ISP that you sign up with, I was able to switch between all four ISPs in real-time to evaluate their relative service quality. During this process I decided to take some actual measurements, and publish the data here online for the benefit of the next generation of Otaku.

## Testing methodology
Unfortunately a lot of people on the internet seem to believe that their speedtest.net linespeed results are a good figure of merit for evaluating how good their ISP is. In fact, many ISPs do heavy traffic shaping (i.e. limit the speed of some traffic such as video and p2p), and depending on when and what you use the internet for, the actual quality of service that you experience may vary greatly. Therefore rather than simply looking at the Ookla speed test results, it is far more useful to do a "stress test" that unveils the **worst case** quality of service.

To this end, I have benchmarked each of the ISPs using the follow four tests done between 9 p.m. and 11 p.m. (the peak usage time slot) on the 21st December 2015 from my house in Setagaya-ku, Tokyo. Similar measurements done on different days gave very similar results, so I think this data is probably pretty representative of the worst case performance of these ISPs within the Tokyo 23 wards at the time of writing.

0. Ookla speed test results to a server in Kanto (tests base linespeed results)
0. Ookla speed test results to a server in San Jose, California (tests uplink international traffic capacity)
0. Time taken to download the 1.1GB [Ubuntu-15.10 torrent](http://www.ubuntu.com/download/alternative-downloads) (tests traffic shaping of p2p content). Note: this test is completely legal, and many linux distributions use p2p to release new versions.
0. Maximum video streaming quality (1080p HD|720p HD|480p|360p) that can be acheived from the Anime streaming site [Crunchyroll](http://www.crunchyroll.com/hunter-x-hunter/episode-1-departure-x-and-x-friends-584886) (tests traffic shaping on international streaming video sites). Note: it's necessary to use a "smart DNS" to access this site, or in my case I used the Google Chrome plugin "Crunchyroll unblocker"

## Notes about cost
Since I've been living in my apartment for more than 2 years, I no longer get the discounts like 2年割, so all of the prices that I give are the non-discounted versions. In Japan you have to pay a monthly usage cost to NTT to use their fiber optic network. In my case that costs 3750yen/month + tax for the "マンションタイプ・ミニ" plan, which means there are 3 - 6 other people in my building with an NTT fiber contract. In addition to this monthly fee to NTT, you have to have a separate contract with an ISP that provides the backbone from NTT to the rest of the internet. The costs I give here are for the ISP portion of the cost of my internet connection.

Another thing that I should mention is that the cancellation fee of most of these ISPs is free (i.e. you can join, test it, and then cancel immediately and only have to pay the first month usage fee), but you often have to actually **call them** on the telephone and explicitly request a contract that you can cancel for free. With Yahoo and Biglobe I made the silly mistake of doing it on the internet, and it looks like I'll have to pay a 5000yen fee to each of them for cancelling.

## Measurement results
Now to the actual review. I'll give the measurement results in alphabetical order of the ISP names.

### Asahi.net
0. Cost: 700yen/month + tax
0. Linespeed to Tokyo: 82Mb/s down | 62Mb/s up
0. Linespeed to California: 45Mb/s down | 91Mb/s up
0. Ubuntu Torrent download time: **Did not connect** = 0Mb/s @ 21:30
0. Max usable Crunchyroll video quality: 720p (sometimes stopped to buffer)

{% img /images/isp/asahi-2140-ca.png %}

Video streaming was working a lot better for Asahi.net than it did on previous testing days, but still not great, and as you can see they have completely blocked torrent usage during these peak usage times. 

**Overall rating:** D for blocking the Linux torrent.

### Biglobe (NEC)
0. Cost: 1200yen/month + tax
0. Linespeed to Tokyo: 93Mb/s down | 94Mb/s up
0. Linespeed to California: 25Mb/s down | 92Mb/s up
0. Ubuntu Torrent download time: **Did not connect** = 0Mb/s @ 21:30
0. Max usable Crunchyroll video quality: 480p (sometimes stopped to buffer)

{% img /images/isp/biglobe-2131-ca.png %}

This is the first ISP that I changed to after Asahi. Their line speeds are pretty good, but unfortunately they seem to do the heaviest traffic shaping out of all the providers that I tried. 

**Overall rating:** D for blocking the Linux torrent.

### OCN (NTT)
0. Cost: 700yen/month + tax
0. Linespeed to Tokyo: 91Mb/s down | 80Mb/s up
0. Linespeed to California: 42Mb/s down | 94Mb/s up
0. Ubuntu Torrent download time: 3.5 minutes = 42Mb/s @ 21:10
0. Max usable Crunchyroll video quality: 1080p (perfect)

{% img /images/isp/ocn-2117-ca.png %}

Finally! This was the last ISP that I tried, and I was very impressed. Download and upload speeds were excellent. The line speed to California was 42Mb/s during peak traffic times, international streaming video was smooth with no buffering at all, and the ubuntu torrent downloaded at the same rate as the line speed. From this testing I would have to conclude that they do little to no traffic shaping, and they have probably invested **a lot** into maintaining strong uplink international traffic capacity. The only limit that I'm aware of with OCN is that they apparently have a 30GB/day download limit. 

**Overall rating:** A because of the excellent quality of service and low cost

### YahooBB (Softbank)
0. Cost: 950yen/month + tax
0. Linespeed to Tokyo: 33Mb/s down | 44Mb/s up
0. Linespeed to California: 5Mb/s down | 81Mb/s up
0. Ubuntu Torrent download time: 12 minutes = 12.2Mb/s @ 22:00
0. Max usable Crunchyroll video quality: 360p (sometimes stopped to buffer)

{% img /images/isp/softbank-2154-ca.png %}


I had read good things on the internet about Yahoo in Japanese saying that they do very little traffic shaping, so decided to give me a try after the disappointment with Biglobe. I had actually used them for a few years in my previous apartment with good results, so I had high expectations. Unfortunately, while they indeed seemed to do very little packet shaping, their base line speed was so terrible that this point was rather meaningless. Video streaming was the worst out of all of the ISPs, and while the torrent at least worked, a 5Mb/s international linespeed is simply unacceptable.

**Overall rating:** F for the poor uplink

## Summary
### Rankings
* OCN: **A**
* Asahi.net: **D**
* Biglobe: **D**
* Yahoo BB: **F**
 
### Points of interest
* OCN was by far the best provider that I tried
* All of the other providers were rubbish
* The service cost appears to be uncorrelated with the service quality
* Aggresive traffic shaping is a big problem with Japanese ISPs


