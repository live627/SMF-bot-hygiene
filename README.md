# SMF Bot Hygiene

## Overview:
This is our sample robots.txt file, and the portion of .htaccess that we use to restrict access to bots.

Everybody's site is a bit different; we are offering these as starter packs for folks running SMF sites.  

## robots.txt Notes & Criteria:
* Robots.txt is voluntary; only "good" crawlers adhere to it.  It is still immensely helpful, though, because there are lots of links crawlers shouldn't attempt to load.  Robots.txt can thus drastically reduce unnecessary site hits for the "good" bots.  
* Our site does not allow guests to see attachments, so they are restricted here.
* We restrict msg level queries here.  This is actually kinda important, as msg links load the whole page of the topic the msg is on.  So, if a page of a topic has 30 msgs on it, the crawler will otherwise load that same page 30 times as it follows each link on the page, which is extremely wasteful.  Note this has proven to drastically reduce Google site requests.
* End user functions are restricted, e.g., profile & notification activity, posts, modifications, likes, etc.  There is no reason for crawlers to attempt any of these, so let them know.
* Admin functions are restricted.
* Search functions are restricted.  They should get that info off of the topics themselves.
* Yes, I know Google does not honor crawl-delay, but I can hope.

## .htaccess Notes & Criteria:
* Our site attempts to allow true search engine crawlers that honor robots.txt.  Even international crawlers, as we support folks from all over the world.
* Crawlers that are not for search engines will get blocked, e.g., AI crawlers are blocked.  Social media crawlers are blocked, e.g., Facebook, TikTok, etc.  
* Crawlers that try to remain anonymous, e.g., by disguising the user agent, are blocked.
* Crawlers that do not honor robots.txt are blocked.
* To constuct this list, we started with the useragent list from this site: https://github.com/mitchellkrogza/nginx-ultimate-bad-bot-blocker/blob/master/_generator_lists/bad-user-agents.list
* We removed some valid international crawlers from that list, and have added many new ones, primarily social media sites & AI bots.  
