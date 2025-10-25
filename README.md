# publisher-writeup-thm

<img width="1092" height="283" alt="image" src="https://github.com/user-attachments/assets/e9c343e2-4e1b-4be7-a3d1-f1ae0dc05a05" />


Ok first thing is first, I'm going to check out the website and see what's on here. 

<hr />

I see it's a site that publishes articles, tutorials and opinions about SPIP. 

I did a little research on what SPIP even is. It's a content management system for websites. 

There's a lot of different webpages. I'm going to click on a few to see what the format is on the links before I try fuzzing a few. 

The links don't actually go anywhere. It just takes me back to the top of the page besides the related blog links. Let's see if there's a robots.txt file, fuzz to see what directories are set up, and then use nmap to see what services are open as a starting point. 

There's no robots.txt file

`gobuster dir -u "http://10.10.146.200/FUZZ" -w /usr/share/wordlists/seclists/Discovery/Web-Content/common.txt`

This didn't come back with anything. I'm going to try ffuf just to see if that returns anything different. 

`ffuf -u "http://10.10.146.200/FUZZ" -w /usr/share/wordlists/seclists/Discovery/Web-Content/common.txt`

Ok I got a few items returned here, but I'm not sure how useful they are realistically. But it did return something. 

<img width="826" height="293" alt="image" src="https://github.com/user-attachments/assets/f5ad2b5a-7db5-4f0a-9b64-98d217e94290" />

<br/>

Ok let's do an nmap scan to see what services are open and the versions
I'm going to use `sudo nmap -sS -sV 10.10.146.200`

<img width="817" height="238" alt="image" src="https://github.com/user-attachments/assets/b2c505b0-cf8e-4a2c-a630-3e13d471a470" />

I got that returned back to me. 

Ok, so let's get 
