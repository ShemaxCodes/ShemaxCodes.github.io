---
layout: post
title:      "Thoughts on the CLI Gem Project "
date:       2020-05-15 14:01:16 +0000
permalink:  thoughts_on_the_cli_gem_project
---


The goal of this blog post is to shed light on how to approach the project with a few of my thoughts and experiences during the process of completion.

I've finally finished my CLI Gem Project and I couldn't be happier! I built a simple gem called "Best Episodes" that gives you the Top 10 best episodes of the show, The Office, with more information on the episode selected by the user. I made the gem for super fans, like me. This was one of the toughest things I've ever had to do in my life, but it feels good to see your code come to life! If I could sum up my experience (from beginning to end) in a few gifs, these would be it.

![](https://media.giphy.com/media/1VV5mivAbIHSSiKXL9/giphy.gif)
![](https://media.giphy.com/media/LRVnPYqM8DLag/giphy.gif)
![](https://media.giphy.com/media/gHhz5ZqkY8rzyWUiKw/giphy.gif)
![](https://media.giphy.com/media/5tgVJmQBd2vBIm7l6B/giphy.gif)

Completing this project taught me to do a few things and I want to pass them along to you: 

1. Use the unlimited resources you have to research old labs, redo some of those labs, and review object orientation before completing the project.
2. Asking for help during the project isn't a sin. You may be nervous and feel outside of your comfort zone, but ask anyway. Trust me. 
3. Don't give up, because you could be right at the point of a breakthrough. 
4. Did I say research already, because that was key for me(still is). Study, study, study. 
5. Binding.pry is your friend 


Before I began, I watched Avi's Daily Deals walkthrough to gain ideas on how to approach this cli gem project. I also had other tabs open to the blogs of other Flatiron students' projects. This allowed me to be confident in the setup of my ide - how to install gems, which gems needed to be installed, and how to set up my scraper, objects, and cli files. 
(I'll post the links to some of those at the bottom of this blog.) 


# There were some challenges

 I ran into issues installing the nokogiri gem, due to the version of Ruby I had installed on my computer being a higher version than it wanted. The terminal let me know this by the error that popped up whenver I tried to install the gem. So, I had to delete Ruby and reinstall an older version for it to work. 
 Once, my gems were installed and my environment was set up, it was time to place code inside of each file. When you install the bundle gem, it comes complete with each file you need to begin your project. So, I was good there. 
 However, once I created and began working in my scraper file, I noticed that the information that needed to be scaped couldn't be done with one selector. That was a minor challenge, compared to others I came across later, but still a challenge. With advice from my instructor (who is awesome, by the way), I figured out a way to scrape each piece of information and place it into one line of code, by storing each piece of info into a variable, and storing those variables into an array. 

```
def self.scrape_episode_list #Scrapes each episode title with Season & Episode Number
            ep_ten = get_page.css("#YWH273QDXVBTLBLL4ALSVSNUGU").text
            ep_nine = get_page.css("#AO3JILON3REBZJVWSRGDX3A3AE").text
            ep_eight = get_page.css("#3MNBSGSUDRBYXATINLS5UN6BAY").text
            ep_seven = get_page.css("#QYJALQAZQVDABILM7ZYPMCGSM4").text
            ep_six = get_page.css("#AGSSJRGXQBGK7GWJ7KZZNO4V5Y").text
            ep_five = get_page.css("#C7ZH5AVICVFJVHC2NGNJSLYXDA").text
            ep_four = get_page.css("#Z2I6XDNCO5GBZCWZ47DXAATIGM").text
            ep_three = get_page.css("#SSH3W74PRNHQTOFIXFNJF6YZQY").text
            ep_two = get_page.css("#SB3RUAFS7NBHXJJHONEU7G2NEM").text
            ep_one = get_page.css("#ZUJRZJVXZNBXDNDDWQ5KUQU7GA").text
            title_array = [ep_one, ep_two, ep_three, ep_four, ep_five, ep_six, ep_seven, ep_eight, ep_nine, ep_ten]
        end 
```
Another challenge for me, was my objects file. This forced me to review object orientation and iteration through arrays. Google, some of other developers on Twitter, and my instructor really helped out with this one. I had been trying not to reach out for help, because I needed to know the information anyway. That was a fail. I Googled as much as I could and while I did get something out of it, it wasn't all I needed to progress. This is why I stressed earlier on the importance of reaching out for help when needed. Don't be afraid, and if you are, then do it while you're afraid. I had tweeted that it was time for me to step out of my comfort zone and asked other flatiron students or rubyists for help. The tweet was shared by Flatiron, seen and shared by other developers, and some reached out to help. All of this allowed me to progress in my project and I finally reached the end -- working on the cli file. 

# Success 

There were times during this process where I felt a strong sense of imposter syndrome. However, remembering that this is only the beginning and knowing everyone is impossible, brought me back down to Earth. Even though there were some challenges, there were successes as well.What I consider a success in my process, was finally being able to break down my thoughts to figure out which direction I should go in my code. It was different coding in an environment that didn't already have specs completed to tell me whether my code is passing or failing. This also gave me more practice in using `binding.pry`. I've used it when completing labs, but not as often as I did here, since there wasn't a "suggestion" given to me in my terminal. In the end, I enjoyed building this gem and it has taught me many things. I wish you well on your journey in completing your project!













Helpful Blogs:
* (https://medium.com/@lisaychuang/my-first-ruby-cli-gem-travel-inspiration-8f7cf5026b3d)
* (https://medium.com/@ingbillyjoseph/how-to-build-a-cli-gem-data-2650a733d16d)
* (https://vannawinland.myportfolio.com/cli-gem-project/)



