Wget is also able to download an entire website. But because this can put a heavy load upon the server, wget will obey the robots.txt file.

 wget -r -p http://www.example.com
The -p parameter tells wget to include all files, including images. This will mean that all of the HTML files will look how they should do.

So what if you don't want wget to obey by the robots.txt file? You can simply add -e robots=off to the command like this:

 wget -r -p -e robots=off http://www.example.com
As many sites will not let you download the entire site, they will check your browsers identity. To get around this, use -U mozilla as I explained above.

 wget -r -p -e robots=off -U mozilla http://www.example.com
A lot of the website owners will not like the fact that you are downloading their entire site. If the server sees that you are downloading a large amount of files, it may automatically add you to it's black list. The way around this is to wait a few seconds after every download. The way to do this using wget is by including --wait=X (where X is the amount of seconds.)

you can also use the parameter: --random-wait to let wget chose a random number of seconds to wait. To include this into the command:

wget --random-wait -r -p -e robots=off -U mozilla http://www.example.com
