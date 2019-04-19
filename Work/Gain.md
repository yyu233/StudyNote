## Gain ##
Work: 
1. Learnt from senior engineer: for fixing bugs or solve a problem, try to see if there is a pattern. 
2. Read the history of commits may give you some hints.
3. Whenever stuck at something, ask for help. Always utilize resources around you.
4. Listen how other engineer communicate. Catch the technical key terms and remember. 
5. Deploying changes on real machine. Check the environment required. 
6. A product can use other company's product. There may need a conversion between different company products. 
7. Remember to check the version of programming language and developing system. (Different version may have different syntax and may have compatiablity issue)
8. Usually high-level design is challenging and interesting. It consumes more time than just coding. It sometimes needs other teams to get involved and other company if new design will use this company's product. 
9. Now thinking development as a result driven process. Maintainbility, scalabilty, efficiency, security. Using other framework and new technologies, what is the time cost for learning and refactoring code base. (That's why we need spend time reading new tech blog or git hub project to explore possiblity of new tech. Sometimes we need support from community.)       
10. Think about data flow. Who is the producer? Who is the consumer? Where to store data? Persistency and Capacity. Receipe, Configuration.  
11. While waiting for the lab request to be complete, just try to borrow if possible from your colleagues.... 
12. Maintainability is very important. If the team needs to update or add new features in the future, it should not be too hard or requrie a huge amount of work to refactor the code base.
13. How much runtime dependencies does a third party package requires? 
14. **Challenge happens when thinking an issue in large scale. It becomes more complicated and easily out of control. (i.e. parallel working)**     
15. Am I aware of what I am doing? Do I have an expected result in my mind for the progam? Can I understand the log written by others? How can I make a log readable to other people? 
16. When the program stops, what about the life cylce of other dependencies?     
17. Awareness of information security. (When is it sensitive and risky for company, partner and customer data?) Awareness of conflict of interest (Is what I and my client are doing potentially threantening my company's interest?) 
18. Our perception about a thing is vague. That means unawareness of the levle of our understanding. Sometimes knowledge we receive is high level and abstract. It is merely the outline of a picture. Most college material and courses touch on the surface due to various limitation. Digging into it and explore every detail will fill out the picture and make one's understanding more comprehensive and solid. I hope college should introduce a general course like engineering thinking (enlightening students to think about why we need certain thing. what is its full capability? what is the trade-off? how to integrate it? etc.). Should help students to shift from a level 1 learner to a thinker.     
19. I think a good way to test how much you master a thing is by looking at how much you can describe a thing. One's understanding can go horizontally, vertically and divergently.    
20. Read other people's code **iteratively**: first time understand what the code is doing. play around and test it; second time simulate the author's thinking process (why he or she came up with this implementation? evaluate the possible overhead and corner case. Avoid thinking the original code is doing something redundant or stupid. Maybe there are some underlying reasons that I don't catch at first glance. Wait for the "Aha" moment.); third time think about how I can rewrite the implementation. 
21. Project and work can be abandoned. The reason can be any: short of fund; manager left; the current solution does not work (this is something we should reflect on.  There must be some improvement we can do at decision-making stage). Bear in mind, always prepare for changes.  
    
Problem Solving: 
1. Simplifying is the lord.... 
2. Desigining algorithm needs to consider the real life case. The alogrithm could be very complicated, but it may not be necessary to apply for the real life problem. The complexity of alogrithm will depend on how accurate we want the result to be for the specific case.
3. Try to avoid extra overhead. 

Common Questions: 
1. Where is the specific file located? (We may need to document the file strucutre and briefly explain what each directory contains) 
2. What does the term mean in the context of the product? (We need to keep a list of definition of technical terms)
3. What is the data flow of the applicaiton? 
4. How should we deploy and run the application? 
5. Why do we need this program? When is it called? How is this program implemented? 

Industial Reflection: 
1. What are the persistent needs in market? 
2. What are the obstacles for innovation? 


Stand-up Meeting: 
1. Video conference, check volume, rememebr to mute. 
2. State who you are, the ticket number you are working on to give others the context of your work. 

Investigate on Defects: 
1. Perform additional tests and show the impact of the defect.    

Write log:    
1. Specify the caller function name.    

Make Changes: 
1. Consider the scope and the impact of the changes. Will it affect other functionalities? Communicate with other teams.    
2. Are the changes based on the latest version of code base? 

Congiure application:
1. Consider teh scope. Is it repository-wide? Is it applicaiton user wide? Is it system wide? 

Development: 
1. Make sure the file format on your development enironment is consistent with the targeted format.  
2. Learnt how to register RHEL system with RedHat and attach different subscription. 
3. Learnt how to use ansible-lint to check best practices of ansible
4. Learnt using jq to test the validity of a json file.   
5. Generally, for a simple input, the more specialized a command utility is, the faster it is for processing the input. It also depends on if we pipeline the command utility. Time complexity matters with large inputs.      

Demo: 
1. Check voice volume and connection. Make sure other people can hear you and read your screen.
2. Snooze slack and chatting app. 
3. Silent cell phone.    
4. Make sure the font size of what you are presenting is comfortable and easy to read. 
5. Close any irrevalent web page. (Also bookmarks). 
6. Mute when people in your room are talking. 
7. Perpare a backup plan (i.e. use screenshot of your development result if demo goes wrong)   
8. Skip discussion and sync up after demo (especially for video streaming, because most of time have no clue who is talking to whom.... when some people ask quesiton, they don't clearly mention the person they are talking to. Have no clue whether the quesiton is directed to you or someone else... Not all the people understand the rule of demo. Even though they may understand, they may forget... So just chill, do your part...)  

Development:
1.  Leave contact information and version number to let other team easily identify the owner and the responsiblity of the file.   









