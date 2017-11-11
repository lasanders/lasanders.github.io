---
layout: post
title:      "This is just the beginning"
date:       2017-11-11 16:53:24 -0500
permalink:  this_is_just_the_beginning
---


Reading through the cli-data-gem-assessment-v-000, I felt a wave of panic. Could I actually build this? I took a deep breath and plunged right in. As I worked through the gem, I realized I could do it. I enjoyed it so much, that I spent extra days just playing around with different ideas. The following is the process I used to create my gem, per Avi's video instructions.

1. **Plan my Gem - imagine interface:**
  I created an interface to look for shopping deals on Revolve and Shopbop.
  I decided that my user would type site-deals to run gem.
  I listed one brand from each website. 
  The user will be asked to select the brand if they'd like to see more information.
	The gem will return the brand, the article of clothing, the price, and a link to the page.
2. **Start with project structure**
  I used Bundler to generate and name my gem - bundle gem site-deals.
  This created lib, bin, rake, README, gemspec files that I tailored to my gem's information.
3. **Start with entry point** 
  I typed, run site-deals and created a site_deals file in bin folder.
4. **Force that to build CLI interface**
  I defined an execution point - the file where people will run program (./bin/site_deals).
  To make sure everything was working, I typed a simple string ("hello") and hoped it would be returned. Yay! it worked.
5. **Stub out Interface**
  I created a CLI class file (SiteDeals::CLI).
	This creates a new instance of controller CLI. 
  In bin/site_deals file, I linked lib/site_deals/cli and lib/site_deals/version.
  I set up a generic code as a place holder before I got the actual information I needed.
	I set the call method, which starts the gem. It will list_deals, then menu, then goodbye.
6. **Start making things real - we need brand name, url, price and article of clothing**
  I created individual instances with properties. I added attribute accessors and code for instances.
  I reconstructed the menu and list_deals methods to set instance variable @deals and set @deals = the_deal.
  I reconstructed the self.today method to make the first and second deal real - to show actual daily deals.
  I replaced our fake data by scraping Shopbop and Revolve, and returned deals based on that data.
  I created a new class method Scrape_Deals - that searches to both Revolve and Shopbop to find the brands on sale, extract properties, and instantiate a deal.
  I added dependencies to gem.spec file - add pry, Nokogiri, add 'require' nokogiri to site_deals.rb.
7. **Test the Gem**
	Upon testing I realized there were a few mistakes, for instance I linked the url to a picture the first time, so I fixed that. 
	I also tested the Gem on 2 different days to make sure it was, in fact, returning different deals.
	
	And now I have a working gem!
