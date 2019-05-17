## Dockerfile ##

To build a docker image: ``` docker build <context> ```     
**\<context>** can be **PATH** which is directory on local registry or **URL** which is a Git repo location.  
       
To point to a Dockerfile anywhere in file system: ``` docker build -f <path> ```   

To tage a docker image into mutliple repos: ``` docker build -t <tag1> <tag2> <context> ```     

### Syntax ### 
```
# Comment 
INSTRUCTION arguments
```
Dockerfile **must start with a 'FROM' instruction**. The **FROM* instruction specifies the Base image from which you are building. **FROM** may only be preceded by one or more **ARG** instructions which declare arguments that are used in **FROM** line.   
**FROM** can appear multiple times within a single Dockerfile to create multiple images or use one build stage as as dependency for another. Each **FROM** instruction clears any state created by previous instructions.   

### Environment Variable ###
Environment variables are declared with the ENV statements.   
**variable_name** or **${variable_name}**    
**${variable:-word}** means that if **variable** is set then the result will be that value. If **variable** is not set then **word** will be that value. 
**${varialbe:+word}** means that if **variable** is set then word will be the result, otherwise the result is empty string. 

Environemnt variables are supported in following instructions in Dokcerfile: 

* ADD
* COPY
* ENV
* EXPOSE
* FROM 
* LABEL
* STOPSIGNAL
* USER
* VOLUME
* WORKDIRS





  

