BQ


|Dive Deep|<p>[Stock market forecasting multi-processing](#stock-market-forecasting-multi-processing)</p><p>[Miss deadline_Couldn’t finish tasks before deadline](#miss-deadline_couldnt-finish-tasks-before-deadline)</p>|
| :-: | :- |
|Go beyond expect|[Stock market forecasting multi-processing](#stock-market-forecasting-multi-processing)|
|**Challenging / Proudest**|<p>[News sort speed in Cmind](#news-sort-speed-in-cmind)</p><p>[Stock market forecasting multi-processing](#stock-market-forecasting-multi-processing)</p>|
|**Tight deadline**|<p>[Use New York Times API to get more training data (news heading)](#use-new-york-times-api-to-get-more-training-data-news-heading)</p><p>[Data Science course import package](#data-science-course-import-package)</p>|
|**took the lead**|[NEU Project arrangement](#neu-project-arrangement)|
|**Lots of deadlines**|[Lots of deadlines](#lots-of-deadlines)|
|**Customers didn’t require but like**|[Most frequently searched keywords](#most-frequently-searched-keywords)|
|**Help others / something outside of your responsibility**|<p>[Help intern debug (date sort problem)](#help-intern-debug-date-sort-problem)</p><p>[Conflict with teammate](#conflict-with-teammate)</p>|
|**Conflict or disagree with mng / do without permission**|[Design complicated Email notification function](#design-complicated-email-notification-function)|
|**Negative feedback**|<p>[Data Science course import package](#data-science-course-import-package)</p><p>[Web Tools project’s searching feature should have a autocomplete function](#web-tools-projects-searching-feature-should-have-a-autocomplete-function)</p>|
|**Biggest mistake / Time you fail**|[Cmind news trending 太多lines在chart里，客户不喜欢](#cmind-news-trending-太多lines在chart里客户不喜欢)|
|**Out of your comfort zone**|[Learn react for the internship](#learn-react-for-the-internship)|
|**Disagree / Conflict with teammate**|[Conflict with teammate](#conflict-with-teammate)|
|**Unclear/ambiguous/ no sufficient data**|[AwesomeRushB Author Editor develop](#awesomerushb-author-editor-develop)|
|**How do you learn new Tech / Learn new things for projects / out of comfort zone**|<p>[Learn react for the internship](#learn-react-for-the-internship)</p>|
|**New approach**|<p>[Stock market forecasting multi-processing](#stock-market-forecasting-multi-processing)</p><p>[Figma for personal Project AwesomeRushB](#figma-for-personal-project-awesomerushb)</p><p>[Use New York Times API to get more training data (news heading)](#use-new-york-times-api-to-get-more-training-data-news-heading)</p>|



## strength and weakness
strength: I am a quick learner
Weakness: due to my undergraduated experinence, I believe that there are still some area that I didn't know.... But I am willing to solid my fundation all the time

## Stock market forecasting multi-processing
That would be my stock market forecasting system. In order to train our model, we definitely need a large volume of data. **So we grab nearly 30 years of news data from New York times API**, considering the volume is huge, and we can get pretty much information just From the news headline, we choose to use this 30 years of news headline to be our data source and it's nearly one gigabyte of pure text data, which is a lot.

We need to clean and process data, to get accepted by model, while the model provides some parallel/multicore process, **the speed of processing raw data is slow.**

After doing some research, I actually found a way to multi core process the data processing port, but since the Jupyter notebook is an interactive interpreter, some function in the python package: multiprocessing.pool will not return our desired result.

We almost gave up the thought of multi-processing this part, because it works, but it's just very slow. I came up with a creative solution after deep diving into the solutions. I put the paralleled code outside of the Jupyter notebook, as a Seperate.py file, I pass the data art call that file in the notebook, it runs Outside of Juse notebook, then read and import the result back. **it works and it's almost 7 times faster than the old method.**

## Miss deadline_Couldn’t finish tasks before deadline 
When I was developing a new feature in my latest internship, We have a new feature that was pretty easy to implement, that's a add-on on previous built function, which is retrieve the news data from DB and display on the frontend page,  my manager ask me to estimate how long can it be done, since we already have a Working structure, just need to follow the previous code structure and do some changes, I said I can get it done by today. 

I got the feature done within the expected timeline, but when I'm doing the testing, **I found the frontend page will crash while testing some case, then I look through code and data further,  I found that the reason why crash is the some old news data stored in our DB are not validated and unified.** So the backend API I just implemented didn’t fully sanitize those old news data and just passed them to the frontend, So when it's trying to parse the unmatched data to the front function, the frontend will throw an error and stop running. 

Since the sanitize rules is a part of our previously built function, that means all of the add-on APIs in that function may have the same problem. While in the frontend we also have rules to sanitize user's input, **but considering in the future we might want this API to work without the frontend so sanitizing here is also needed.** I reported the situation to the manager and let him know the issue, then told him I'm not able to deliver it by today. He said he understood the situation, no worries, just go for it. The next day, I added some rules in all of the APIs inside of that function and fully tested them before I committed the code. He thought I did a pretty good job on that.

## Customer didn’t require but like it / beyond expectation
That was a project designed for local researchers, they used to use excel to record data in a long time and do the calculations all manually. Then since the metrics they're tracking is continues growing so they reach out to my professor hope we can design a system to help them to simplify their job, then my professor reachout to me and another classmate to see if we are interested on that, and we formed a team to do that. The main functions is to do CRUD for their data, and we also need to allowing them import their old data to the new system from their excel files. We also need to do statistics for them and generate various of results and Charts, so they can see the number or other metrics of bacteria or something is changing or not. Or the trend of them. We actually found they have lots of different sampling point, and the location data are all in latitude and longitude, it's hard to understand where the sampling point exactly is by just looking at this data, I think they definitely need to translate that to a point to something more human readable so we pluged in a third party map API, and we display all of the sampling point as a pin on that map, Once you Click on that pin, it will display the detailed data that sampling point collected and some button to view the Statistic data and charts calculated for that point. Our clients really love this feature and it's a suprise since they didn't except to have this. We are very happy to see they love it as well.

## News sort speed in Cmind
It was my latest internship. I was in charge of a new feature named portfolio, which allows the user to save their target company into a portfolio(favorites) list for easier browsing in the future. In this portfolio, we will show detailed information according to the companies the user added, such as recent news. The data team will grab the recent news for us and store them in to database, For the recent news feature, it would display 5 recent news for each company immediately, but there is a problem that the speed of fetching news is too slow, and the more companies there are, the slower the speed, sometimes it always consumes 7 sec.

My manager asked me to optimize the performance of news fetching in 3 days, cuz next week he wants to demo our website to a potential customer. 

Time is running out because all the news data was stored in the MongoDB, and the fetching function was implemented by my predecessor intern, he just fetched all the target data from DB and did the clean, filter, and sort function in the frontend, that consumes too much performance, so at the first, I decided to implement the clean and sort procedure in the MongoDB by overwriting the NoSQL query, so when the data is retrieved, it is the prepared data. Actually, the performance had been boosted and the time had been reduced to five seconds, but it was still not satisfactory. I reported the situation to my manager and he thought that was enough. I persuaded him that there was still one day left, so I could try to solve this. 

After researching many references online, I noticed that it already reached the limitation of mongoDB’s s performance cuz we had eighty thousand dataset. At the same time, I remembered that another team was working on the searching function for another feature, they utilized Elasticsearch for high-efficiency search, and they backed up the news data as well, which means that I could utilize ElasticSearch to optimize performance. I started to self-learn the ElasticSearch official document, try to implement it on the backend, and created RESTful API for the frontend, after fully testing, the current fetching speed became 1.5s, my manager was surprised and he told me that I did a pretty good job.
## NEU Project arrangement

**Situation**: When I was in my first semester in Northeastern University, I took a course named Application Engineering and Development which used Java to develop full-stack project.

**Task**: And the first project of this course was to develop an airline reservation system. I had two teammates in this project. But situation at that time is that we all didn’t any experience in developing project using Java, and both of them even didn’t learn any programming languages before. I was the only one who had programming experience in the team. So it was really hard for us to get started on the project. So I came up with an idea that I could take the lead of the project and try to finish the main class design, and they can focus on the easier part like UI design and some functions by using the API I finish. I was so confident that I could finish it myself within one week since I believed I have good understanding on programming language, and I am a fast learner. And they also trust me and then I start. And they just waited for me to complete the classes and then they could continue working on their part. **During** the time working on my part, I hardly discussed with them about the system requirements, and I just finished the class design by myself. And for some part that should be more complicated, like choosing seats, I just did it in a really simple way like adding a textbox for customer to type in and didn’t consider about the edge case like seats not available since I was afraid I wasn’t able to accomplish that. And I didn’t tell my teammates about that. After I finished my code, my teammates started working on their part. They had a lot of questions on my code. They couldn’t understand so many logics between the classes since they had fewer experience on coding, and they didn’t know what I was thinking since I hardly communicate with them. And they also have many disagreements on my design, and I didn’t meet their requirements. 

**Action**: I realized I made a big mistake at work. I didn’t meet their requirements and since they just had fewer experience I left them behind and never asked them for suggestions. So I set up a meeting with them to further discuss what they were thinking and what system requirements I missed. And I spent 2 days going through the code I finished and made sure them understand the logic. And I also created a Google doc to add classes and gave an explanation on each of the class and shared with them. And whenever we added something we will also keep the Google doc updated so that each of us can understand other’s work. 

**Result**: We finished our project in time and we all improved a lot in Java programming and teamwork. And after this experience, whenever I work with others, I will take my ownership and always be ready to help others. Also, I will always ask others’ thoughts and take their requirements into consideration. I noticed that ownership and customer obsession and earn trust are the critical leadership principals of Amazon and I will always stick to it.


## Data Science course import package
It happened when I was learning the Data Science course at Northeastern, I didn't have any ds foundation before I took this Class, and I chose to take it because of my personal interest. I think I have to try it first, then I'll find out if it's interesting for me or not. I didn't do well in the first few months, it has lots of math concepts as a foundation, and I'm not pretty good at it. In the midterm, I encountered some technical issues. One of my import packages continuously goes wrong. I tried to ask the professor for help but it took nearly 15 mins to fix. Professor said it's my responsibility to make sure it's running before the exam, and I'm glad to take the negative feedback, and I didn't get a great score in midterm, both because the question is challenging and the tech issue. I work very hard after midterm, especially in the area that I'm not geed at, Study with classmates to discuss those question I don't really understand l spend lots of time on my final project, it's Pretty successful and my professor said that topie is really interesting, that inspired me a lot. My efforts paid off, I did well in the final exam as well. Eventually I got an A on that course

## Lots of deadlines
That was my first semester since studying at Northeastern, that’s also the first time I step on the land of the US. Everything is new, and I have some learning curve.

I enrolled 2 classes in that semester (Application Engineering Development, and web design), at the final, I have bunch of deadlines, from exam, project, and the online assignment from some online courses on Coursera.

It is really challenging for me to study so many things in a different language environment, I have to manage well, I tried to use some time management tools like calendar and reminder to help me arrange tasks, by the way, they definitely helped me a lot, especially when you face several deadlines and feel confused or disorganized. So firstly, I list all the deadlines and exam dates in the reminder, then I prioritized them according to their important level, for example, AED was the required subject and pre course of some courses I wanna take in the next semester, it is the most important so I just set AED as the highest priority, for the Web design, because its due date was later than AED, and the project is relatively simple, so its priority is not too high. As for the online course, I noticed that there was an option to extend the deadline, so I would have more flexible time to pay attention on my campus project. Then I just arrange those tasks on my calendar so that they could notified me before the task start.

Besides that, I also sacrificed a lot of personal time to review those classes for a few hours, then change to another class, to adjust myself. I made my notes more concise to make sure I focus on the most important part.

The power of a single person is weak. I usually study with my classmates, they can often answer my questions, and when I am answering their questions, I get more familiar with this.

After meeting all of the deadlines, I am pretty happy with that cuz I know I already tried my best.

From this process, I found when I have too many tasks on my plate, I will feel stressful, but I usually spend a few minutes to outline a schedule, I found it's really important to take a step back and identify which task is priority, then use notes to remind me of the tasks I have to accomplish every day. And I think communicating well with other people in terms of timing is also a key to stay focused. 

## Most frequently searched keywords
It was my latest internship in the Cmind, at that time, I was in charge of the searching feature,  which allows the user to input the company’s name or ticker or CIK, and we will display the corresponding info for the user, such as the C-score(one score that computed by us with machine learning algorithms), recently news, news mention times change, and anything else.

Actually there was still a little problem with this page, not about the function, but design. because this page is a little bit tedious, there was only a search bar and search button placed in the center of the page, the rest of the page was just empty and blank. From the User Experience perspective, it is not a good design. Try to imagine a scenario that if there is a new user of our product, he / she probably feels confused about this page and doesn't know how to use it. At that time, it suddenly occurred to me that in the former infrastructure design part, our tech lead already let us record user behavior and search habits in the database, so can I do some work in this area? So, I just came up with an idea which is to set the recent trending keywords below the search bar. It also could be a reference for the user when he / she doesn’t have any search target.

After communicating with our UX designer and receiving positive feedback, I started to work on it. As our tech lead already let us record some user searching habits, so it is not hard for me to retrieve those data, then I  and I did a clean and statistics operation, then sorted them. Finally, I obtained the 10 most frequently searched keywords and dynamically displayed them below the search bar. 

My manager told me that he liked this part very much, and our client was surprised since he didn’t expect to have this. We are very happy to see he loves it as well.


## Help intern debug (date sort problem)
Sure thing, during my working and learning process, I always love to help my classmates or colleagues because you must want to be helped when you are in trouble as well right? I remembered when I was in my internship, another intern just reached out to me for some problems, cuz he was new here just for 1 week. He is a little bit timid and he really doesn’t know how to get things working. You know, working at a startup company, everyone is busy here and probably some of the experienced colleagues are part-time. You can definitely reach out to your colleagues for help but you don’t really know how fast they will reply.

` `He told me that he had been troubled for a long time on the data format, and asked for help from me. I had exactly some experience when I joined, I totally understood the situation he had, so I gave him a hand.

` `The thing is he was working on a table that will show the different info about each company in each row. Like the market value, stock price, and so on. So as we know, there should be a sort function for better user experience. Like sorting stock prices from low to high, or sorting by the date…….., but he always encountered a situation where sorting by date didn’t work.

I did a screen sharing with him to fix this bug, since the date about those companies was retrieved from our database, I just checked the original data without cleaning and filtering in the database. I found that some of the earlier date was stored as String format, that was definitely a big mistake!, otherwise u need to convert the String into a timestamp. So for the data, I just let him restore those data as date format, for the frontend, I just helped him write a temporary function for format converting. Once the data has been updated, there was no need to use that tmp function. An hour later, it runs as expected.

After that, we often discuss the bugs we met or the solutions to new feature, he also shared lots of decent ideas that helps me a lot.

so I do believe help others is a win-win



## Design complicated Email notification function

**S:**

**Cmind做notification，简述需求，提出冲突（mng要做one page design，但是我认为有潜在问题）**

That was my last internship in Cmind Ai, I was required to implement a notification setting  panel for a portfolio. For this setting panel, it allowed the users to track the data changes about the target companies user saved in their portfolio and get notification in time. For each company, there were 4 checkboxes, corresponding to 4 types of data needed to track. After meeting with the manager, he provided me with a design plan for this part. I was required to implement all the functions in one single page, however I thought that there were potential problems about one page design, so I didn't agree with his approach. 

**T:**

**我想做two page design，具体功能是什么，任务是调查两种哪种好，然后和mng达成共识**

From my perspective, I think we should have a two page design, for the first page, the user  only needs to consider which company they want to get notification from, for the second page, they can check the data type and change the value they want to be notified. Due to the limited deadline, the task I need to deal with is to research which of the two designs is more suitable for needs, and reach a consensus with the manager ASAP.

**A:**

**建对比列表，在figma实现demo，反复尝试，发现one page design公司多的话，很乱，跟mng开会说清楚**

Then I created a list for those 2 designs and made a comparison. Then I used Figma (a UX design tool) to implement those 2 demos and tried several times under different situations. During this process, I found that compared with 2 page design, even though 1 page design looks very concise and simple, it seems that all the information is on one page, which is more intuitive, but if the user saved more than 10 companies in this portfolio, and there would be 10 \* 4 = 40 checkboxes squeeze on one page, and it is very unclear and confused, and the user experience is not very good. But if we use 2 page design, the users only need to follow the flows we set for each page, and they only need to consider their needs based on the current page, that is more logical and efficient. I have summarized a document about my research result. Then I set up a brief meeting with my manager and took him to go through the 2 different demos, and told him whyI think the 2 page design is better than 1 page design.

**R:**

**达成共识**

After viewing my demo and summary, he understood me and trusted my approach was correct and we reached a consensus. He modified the design plan and I completed the work before the deadline and it proved to work well. After this conflict, I learned that communication is the best way to resolve the confilcts. 

1. 背景要铺的全面一点，换个思路去写
1. 虽然组员很少，但是我们每周四有all hand meeting
1. 强调cmind 是 start up
## Cmind news trending 太多lines在chart里，客户不喜欢

4 lines 可以提一下 为什么4条线是最好的

Situation:

The biggest mistake / fail I've made happened when I worked as an intern in Cmind. I got a requirement from a client about adding a new feature(news Trending visualization, which is to allow the user to search a keyword under the target company, then the News change related to this keyword and company will be displayed in the chart and at the same time, it will also show the news trending of the target company's competitors. ). So I documented requirements, worked with the data team, and released the update to the demo system on time. However, the client tried the new feature and didn't like it.

Task:

I diagnosed the feedback immediately. It turned out that I paid more attention to the details that the client requested us to add. There were too many colors and lines in the line chart, there were about at most 7 lines, which made the chart look dense, which would make users confused and hard to find the data they need.

Action:

I emailed the client immediately and asked if we could have an extended delivery date. Fortunately, the client showed understanding and agreed. Then I set up a meeting with the manager and my teammates, talked about the feedback and evaluated all possible interactions that users might take on the control panel and then documented the changes we were going to make. After discussion and evaluation, we decided to limit the control panel to only enable 3 most competitors as the default view, corresponding to 3 colors. We also provided users with options like they could customize the competitors they want to display. Throughout this process, the team members understood what happened and why the client was not happy. We brought up a lot of good options to build better user experience on the new feature. So instead of just telling the team to make changes directly, I earned other team members' trust by sharing client's feedback and working out the solution together.

Result:

Then we released an updated version to the demo system before the deadline, walked it through with the client and received good feedback. From this mistake, I learnt that I need to look at a problem from a global perspective, focusing on the details is not wrong, but it may lead to other problems. Only by considering all aspects and maintaining good communication with other teammates can we better meet the needs of customers and win the trust of teammates at the same time.
## Conflict with teammate
**S:**

Well, I have an interesting story to share. It happened when I worked for Cmind AI, which is a start-up fin-tech company. My manager asked me and one of my teammates to implement a new feature, in order to ensure that we are at the same progress and for better communication and learning, we decided to review each other’s code every two days. However I found out that he had some bad coding habits, which will cause confusions, even mistakes in the future developing task. He wrote all the code into one class, that class is super long, and each function is pretty long as well, therefore, I found there were lots of duplicated codes, just the variables passed in are different. For each function, he didn't even give any comments to those codes.

**T:**

So I just messaged him from the working channel. I told him that your code is working but it is too long, too complex. It’s not readable for anyone but you. I think It’s better to separate those codes into different classes, and extract major code segments which used more than one time and encapsulate them into independent reusable functions. He replied to me that he thought it was not a big problem because he thought we are not going to change those codes for a long period, as long as they are working, it should be fine.

**A:**

Actually he is just a Sophomore student and doesn’t have any experience in practice and working. As we know, there was definitely a huge difference between work and study, so it is pretty understandable that sometimes students like him don’t know the importance of decouple, because of lack of practical experience. Then I just set up a quick meeting with him, explained the importance of scalability, and made some examples to merge those duplicate codes into one reusable function and call them directly when needed. As for the comments, I told him that although comments don't seem to help running the code directly, and it takes time to write, but it could remind you and other colleagues of the major meaning of this code in a short time. Even it will be more helpful in future iterations and handovers. That is why This time spent is worth it.

**R:**

After the meeting, He is willing to take my advice. By refacting those codes, it gets easier to locate the functions, and it helps to reduce the redundant workload. The code review between us has also become smoother, and the progress of the entire project has become faster than before.

## Figma for personal Project AwesomeRushB


**S:**

That was my group project AwesomeRushB, which is a full-stack project with an Agile development method, Yeah we just wanna have a try to follow this standard development flow. and for me, I joined this team later and I was in charge of the front end part. Before that, they just started to conceive the whole project and design a simple UI.

**T:** 

**以前使用google doc做简单流程图，手动画UI，太费时间，效率不高。我想把课上学过的Figma介绍给大家。**

Due to the lack of the UI design member, and none of the other team members have corresponding UI design experience, there were not some standardized workflows and professional working tools. Before this time, they two just used google doc to generate some basic and simple flowcharts to demonstrate the major function of the current UI, for some more complex functions and interfaces, we just draw it manually in the google doc, yup, literally draw it. That would be time-consuming and ineffective, and because it was drawn manually, it lacks design standards. So even though the UI came out, I might still be confused about the component’s precise location, UI’s unified theme color, and so on. I think this is not professional, and we need a more standard way. So I want to introduce Figma (which is a design tool that I learned in UI & UX design course) to my teammates. This can not only reduce the design time but also ensure the stability and accuracy of those components.

**A:**

**创建使用文档，介绍优点，可以多人协作，然后快速实现了需求，开会展示，大家都很喜欢**

So at first, I just created a setup document about how to use it for my team. In this document, I not only introduced how to set up this application but also compared the new method with the previous one. And I demonstrated what the advantages of this software are, why this application could save time, and why we need a more professional tool. More importantly, this application can collaborate online with multiple people, which is more conducive to teamwork and will not miss any inspiration and ideas. Then next,  I just created a project in Figma, quickly implemented a demo UI for the login page, and added the reasonable jump logic with the easy-to-implement animation effects. I had a meeting with other teammates, showed them the demo, went through the document, and explained that the design tasks could be completed more efficiently and standardly. they agreed with me and let me quickly train them how to use it.

**R:**

Since we can collaborate online, we can quickly understand each other's ideas. Finally, we quickly completed the UI design work, and as for me, cuz I was responsible for the front-end part, I was able to write CSS code very accurately that reducing some unnecessary questions. 
## Use New York Times API to get more training data (news heading)
// 改进，重点说怎么面对tight deadline的，比如意识到还有三天，先是规划了一下时间，用晚上的私人时间学习web crawler和api相关的知识，然后简单测试，第二天一天编写fetching代码，并且处理，清洗，剩下的一天把数据丢到模型里面训练

**S:**

That was my data science course project, our target was trying to use news headlines to predict the stock price’ change. As we know, in some general situation, the more data sets, the more accurate the training results, but the current thing is, we need to prepare a huge volume of the data by ourselves and complete this project in one week.

**T:**

We Started to search related references online, tried to download some open-source news dataset. however, the data sets that can be downloaded on the Internet are very limited, and there are the following problems. The amount of data is too small, the data is too old, and there are a lot of garbled codes, which need to be cleaned up manually. Seeing that time flies, we haven’t made any progress, so we had to train our model with a super old 500M data set first. Just to make sure that our logic is on the right track and model could work. In fact, our model works perfectly, but because the amount of data is too small, the results are not desirable. Actually, I think I am the person who always want to do the best and always stick to high standards, so in order to get better results, I tried to find another way to get the target data sets. Even though there was not much time left.

**A:**

After browsing on the Internet, I found out that The New York Times officially provides developer an API, which could grab nearly 30 years of news data. But I have never used it, not sure if it could meet the demands, as the time flies, So I decided to sacrifice my personal time to self-learn some basic web crawler knowledge and try this approach. I registered an account on The New York Times developer platform and applied a token for API. It turned out that I have to send a request via API and token and waiting for the result sending back. In order to ensure we could get the better training result; I grab nearly 30 years news info. As the data was quite raw, we could not use them directly for our model and there were some details that I didn’t require, so after fetching, I did series of data cleaning job to make sure they fit our model, after my approaching, finally, we got nearly 2 gigabyte of pure text data, which is quite a lot and that is definitely enough for our model training.

**R:**

We completed the training before deadline, during the final presentation, we introduced how we obtain the news data, and made a comparison that result from large volume datasets was more ideal and precise! The professor agreed with our approach and told us that we did a pretty good job! From this experience, I learnt that as long as there is time left, never give up any possible opportunities, and When faced with complex problems, we should not lowered standards.




In order to train our model, we definitely need a large volume of data. **So we grab nearly 30 years of news data from New York times API**, considering the volume is huge, and we can get pretty much information just From the news headline, we choose to use this 30 years of news headline to be our data source and it's nearly one gigabyte of pure text data, which is a lot.




## Learn react for the internship
S:

When I worked as an intern in Cmind Ai.  My main job there is to develop the front-end part with ReactJS.  I have some experience on the Angular framework before cuz I learnt it from my course and used Angular to do some projects on the campus, but I have never used React before. I only have a week to learn this new technology, and then I will start to take over projects quickly.

T:

So I clarified my learning task: First of all, I want to review the basic conditions required by the React framework: HTML, CSS and Javascript. Learn the execution environment of React: Node.JS and the editor VS Studio. Then you have to learn the basic concepts and component structure in ReactJs. Finally, try to build a simple React App.

A:

First I review the basics. Every front-end developer starts their journey with three things: HTML, CSS, and JavaScript. HTML is the skeleton of a website and defines the structure of each component. CSS defines the style of each component, such as color, height, and width. JavaScript defines functions, what each part does (const, let, arrow function).For the environment, Node.js is the execution environment of JavaScript. I can manage packages through npm, and then use import and export to control modules. For the editor, VS studio is a good code compiler, it has a good interface, easy to add various plug-ins and is suitable for multiple languages. After reviewing the basics, I started to learn ReactJS following the official document. ReactJS is a JS library that can use reusable components to build front-end apps. There is a parent-child structure relationship between components, state can be used to control state within components, and props can be used to transfer parameters between components. The style of React is also controlled by CSS. After understanding the basics of React, I started to build a simple page based on the tutorial, including a menu bar, title, and different cards. (Create react app, build components, combine together, edit css, router to jump to detail page).

R:

After a week of learning, I can basically use react to build a website. So, I had a meeting with the UX team. to determine the basic style of the website, and implemented the project structure and welcome onboarding interface before the first review.

## Web Tools project’s searching feature should have a autocomplete function
**S:**

During my third semester, I was taking the Web tools & development course, for the final project, I chose the area I am most interested in, that was a web application allow user to browse and appreciate art online. After two weeks of continuous working on it, I completed this project before deadline. In order to ensure that everything will work well in the final presentation, I participated in the TA hours and tried to demo my project to get some advices. However, after viewing my demo, TA told me that there was a problem with my project, which might cause bad user experience.

**T:**

The TA just gave me negative feedback, he pointed out that even if my website was working, but I need to make some improvements to the search function to refine the user experience. Currently, the searching function is quite simple, it just allowed the user to type their keywords and press search button, then just wait for the searching results. However, nowadays, there was a user-friendly function for many websites’ searching feature, which is autocomplete search or searching suggestions. Especially for my website, searching function is still more important part.

After meeting with TA, I was willing to accept the TA’s feedback.

**A:**

In order to figure out the principle of autocomplete function, I started to search for relevant references online. I learnt that this could be implemented with AJAX, which allows web pages to be updated asynchronously by exchanging data with a web server behind the scenes. This means that it is possible to update parts of a web page, without reloading the whole page. So that’s why when the user types a keyword, the autocompleting content of the search box will change dynamically. Then I tried to implement a simple AJAX code according to the guidance of the JQuery’s documentation. For the autocompleting content, I just use the backend API that I already developed to get the candidates keywords, then match them with the target keyword using fuzzy strategy. 

**R:**

With those approaches, I almost done the autocompleting searching function, after trying several tests and adjusting the CSS code, it proved to work well, during this process, I also made a lot of progresses on the Front-end part. Even after I learned, now Fetch has replaced JQuery’s $.ajax,  the method I tried is no longer recommended. But I think this is a very good learning path, and lays a foundation for me to better master Fetch method, my efforts got paid off and From this process I learned that I should not be afraid of failures, whereas I should improve myself to satisfy customers to deliver results. 

## AwesomeRushB Author Editor develop
**S:**

This Spring, I was working on my personal project: AwesomeRushB, which is a web application that allow users share the articles about Data structure and Algorithms. I was mainly in charge of the front-end part. Because I joined our team later, so I got my first task is to develop an online editor for the users.

**T:**

Actually, the problem I was encountering is the ambiguous requirement, my other teammates have no experience of using React, so they didn’t know the specific development strategy, like how to implement an online editor, how to achieve the real-time rendering effects, and which of the editors should we use? For example, there were many different types of online editors, like Rich Text Editor, Markdown Editor, and so on. So, the task I need to deal with is figure out the specific developing direction. Not just implement an online editor.

**A:**

So, I just set up a meeting with my teammates to discuss the development direction, Firstly, we just analyzed the user needs. The main user group of our website is programmer, so for them, they were more like to use markdown to edit document, that’s the user habits. On the other hand, since it is a website that sharing algorithm and data structure, so the author will definitely insert some code blocks in the article to help understand, so Markdown has better support for code blocks, and its syntax is simple, so we decided to use the Markdown Editor. In addition, they originally want me to implement an editor from the beginning / zero. I said that there are many open sourced, perfect, easy-to-installed markdown editor on the Internet. Because we lack relevant practical experience, we may have some unexpected bugs if we develop by ourselves. So, for us, it is better to stand on the giant’s shoulder, which means just use online libraries. Moreover, many online libraries also support real-time rendering and reverse rendering, which means when we take the article out of the database, we can use this library to render into formatted html webpages, that definitely saved us a lot of time. After our discussion, we decided to use a library with a high degree of customization.

**R:**

The library worked pretty well, the style of the editor matches our web page design, at the same time, on the right side, the user can see the results of real-time rendering, which is a great help for editing articles. During this, it improves our development efficiency, and allow us to pay more attention on other functions.
