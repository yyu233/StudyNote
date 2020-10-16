Your company may have a domain:
```
Code:
mycompany.com
But it may be a large company, so each department may have its own village (sub-network), each with its own sub-domain:
Code:
hr.mycompany.com
pr.mycompany.com
it.mycompany.com
research.mycompany.com
marketing.mycompany.com
Your computer may be mycomputer.marketing.mycompany.com and the department server is mkserver.marketing.mycompany.com but thanks to the way DNS is set up you are in marketing.mycompany.com and can access the server simply as mkserver. But you use the server prserver.pr.mycompany.com a lot, not to mention mainserver.mycompany.com, and don't want to type in the full address each time. Search domains allows the other sub domains plus the main domain to be searched as though they are your local domain. So you may have this in your search domain:
Code:
marketing.mycompany.com
mycompany.com
hr.mycompany.com
pr.mycompany.com
it.mycompany.com
research.mycompany.com
```
Now the full domain name is needed if there is a clash of names as in john.pr.mycompany.com and john.it.mycompany.com
