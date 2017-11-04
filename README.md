Independent Work Day
======
By: Dawson Mortenson

Date: 11/3/2017

The A.M.
------
I kicked off the morning by running through a list of my unexplored coding related concepts, frameworks, and services. I spent well over an hour skimming the surface of each one to get a better idea of what I would be able to accomplish in the next 8..err 7ish hours and from that I narrowed my choices down to 3: Vue.js, data structures/algorithms, and AWS. While it was tempting to delve into a new framework I wasn't sure if having a day's worth of knowledge for a given framework would benefit me. The data structures and algorithms could be super useful for whiteboard interviews and gaining a better understanding of programming in general. I came some promising resources that I purchased from [Udemy]("https://www.udemy.com/learning-data-structures-in-javascript-from-scratch/"). After realizing that interviews for a Junior Web Developer position might not have questions on those concepts I thought more about what I would be working on as a Jr. Developer. Most web companies don't host their own websites and one of the most popular, versatile hosting service these days is AWS. I've had an interest in figuring out how to use it for a while now, but they offer a lot and it is overwhelming to login and have 50+ types of instances and hundreds, if not thousands, of settings at your disposal.

![SOOO many choices](screenshots/aws-1.png?raw=true "The many, many options you have for firing up AWS services.")

I spent the remainder of the morning setting up an account via [GitHub's Student Developer Pack]("https://education.github.com/pack") that came with a $150 credit in addition to the the 12 months of open access to the free tier that Amazon offers. I ended up skimming through a few of their [10 minute tutorials]("https://aws.amazon.com/getting-started/tutorials/") before heading over to the documentation. Each of their services had manuals that were nearly 1000 pages long. I'm not a huge fan of text heavy documentation. I like when I know what I'm reading is actually accomplishing something and after reading the 'getting started' section for EC2s I hadn't accomplished enough to want to continue and decided to turn to other resources.

The P.M.
------
After lunch I hunkered down and tried to get something working. I learned more about what AWS is and how its services worked in unison to provide the ultimate, scalable hosting solution. After figuring out that an EC2 instance was the best route for a simple server I followed a tutorial that set one up. I was now able to login into my remote server. While it had a public DNS I was unable to connect to it through my browser without some sort of web server running. I found a package 'httpd' that was supposed to boot up an apache webpage server and show me a test page. Unfortunately it did nothing. I mean it was running, but I couldn't view my static page over the internet. After messing around with various settings and configuring an elastic IP all I had accomplished was permanently disconnecting my ssh connection to my remote server. The great thing about these instances is that you can spin them down as fast you can spin them up without any penalty. So I tossed out the one I had messed up and started over. (Note: I later discovered that setting up an elastic IP changes the public DNS I was using to connect to it.) I found another [tutorial]("https://www.nczonline.net/blog/2011/07/21/quick-and-dirty-spinning-up-a-new-ec2-web-server-in-five-minutes/") on setting up a simple web server on an EC2 and learned about security protocols that you can setup for each instance. By default the only inbound connections allowed are via port 22 for sshing into the server. You have to manually configure any additional tcp ports for inbound requests, including port 80 for http requests. This time my server was up and running with a simple static page.

![AWS Apache Test page](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/images/apache_test_page2.4.png)

Now I wanted to attach a domain name that I had received from Namecheap via the Developer Pack earlier in the morning to my new EC2 server. Just as my first attempt with the web server, I failed and broke something and ended up scrapping the instance. After firing up another instance I set out to get an Angular application up and running. It didn't take long to install nvm, node, and the cli onto my EC2. Everything was going smoothly until trying to serve it. The server was up, but there was nothing displayed in the browser. Then it occurred to me that by default the angular app was running on port 4200 and my server only allowed inbound requests on 80. I promptly added a rule for port 4200 and sure enough it worked. After some googling I learned how to change Angular's default port to 80 to avoid accidentally compromising my EC2 by exposing the port 4200. Still wanting to link my server to my domain name I followed another [tutorial]("http://techgenix.com/namecheap-aws-ec2-linux/") that goes over AWS Route 53 and I believe it works now (it takes 24-48 hours for changes to take effect so we'll see).

#### Great AWS Resources

* [30 Minute Intro to Basic AWS Services](https://www.youtube.com/watch?v=ubCNZRNjhyo)

* [A Beginner's Course I wish I would've started with (Costs $$)]("https://www.udemy.com/learn-aws-the-hard-way/")

* [Good explanation of EC2s]("https://www.youtube.com/watch?v=lZMkgOMYYIg")

* [HackerNoon Nodejs AWS tutorial]("https://hackernoon.com/tutorial-creating-and-managing-a-node-js-server-on-aws-part-1-d67367ac5171")

* [EC2 vs Elastic Beanstalk]("https://stackoverflow.com/questions/25956193/difference-between-amazon-ec2-and-aws-elastic-beanstalk")

Other Preparation I Need (Q2 & Q3)
------

* A better portfolio of polished projects. I have a bad habit of not going back and working on old projects because the new ones are usually much more interesting. I feel like my portfolio has few projects I would be proud to show off to a potential employer.
* I feel unprepared for a developer interview. I have had many interviews in the past and they've always gone well, but this type of interview feels like it will be a lot different and I'm not sure how to prepare myself to fit the expectations of the interviewer.

Proof
------

* I learned how to use AWS to host an Angular application. I expect to use my new knowledge to build out and host my portfolio. This will be something I can present a future employer with confidence.

* I started searching the web for resources regarding interviewer's [expectations]("https://www.reddit.com/r/webdev/comments/5wqbxy/junior_front_end_dev_interview/") for junior developers and [tips]("https://www.reddit.com/r/cscareerquestions/comments/6g589z/junior_software_developer_interview_tips_please/") on how to succeed.

* [EC2 Angular App]("ec2-34-211-238-146.us-west-2.compute.amazonaws.com") and hopefully a link after 24-48 hours [dawsonmortenson.me]("http://www.dawsonmortenson.me")
