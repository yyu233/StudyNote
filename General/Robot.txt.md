A robots.txt file tells search engine crawlers which URLs the crawler can access on your site. This is used mainly to avoid overloading your site with requests; it is not a mechanism for keeping a web page out of Google. To keep a web page out of Google, you should block indexing with noindex or password-protect the page.

What is a robots.txt file used for?
A robots.txt file is used primarily to manage crawler traffic to your site, and usually to keep a file off Google, depending on the file type:

robots.txt effect on different file types
Web page	
You can use a robots.txt file for web pages (HTML, PDF, or other non-media formats that Google can read), to manage crawling traffic if you think your server will be overwhelmed by requests from Google's crawler, or to avoid crawling unimportant or similar pages on your site.

Don't use a robots.txt file as a means to hide your web pages from Google search results.

If other pages point to your page with descriptive text, Google could still index the URL without visiting the page. If you want to block your page from search results, use another method such as password protection or noindex.

If your web page is blocked with a robots.txt file, its URL can still appear in search results, but the search result will not have a description. Image files, video files, PDFs, and other non-HTML files will be excluded. If you see this search result for your page and want to fix it, remove the robots.txt entry blocking the page. If you want to hide the page completely from search, use another method.

Media file	
Use a robots.txt file to manage crawl traffic, and also to prevent image, video, and audio files from appearing in Google search results. This won't prevent other pages or users from linking to your image/video/audio file.

Read more about preventing images from appearing on Google.
Read more about how to remove or restrict your video files from appearing on Google.
Resource file	You can use a robots.txt file to block resource files such as unimportant image, script, or style files, if you think that pages loaded without these resources will not be significantly affected by the loss. However, if the absence of these resources make the page harder for Google's crawler to understand the page, you should not block them, or else Google won't do a good job of analyzing pages that depend on those resources.
Understand the limitations of a robots.txt file
Before you create or edit a robots.txt file, you should know the limits of this URL blocking method. Depending on your goals and situation, you might want to consider other mechanisms to ensure your URLs are not findable on the web.

robots.txt directives may not be supported by all search engines
The instructions in robots.txt files cannot enforce crawler behavior to your site; it's up to the crawler to obey them. While Googlebot and other respectable web crawlers obey the instructions in a robots.txt file, other crawlers might not. Therefore, if you want to keep information secure from web crawlers, it's better to use other blocking methods, such as password-protecting private files on your server.
Different crawlers interpret syntax differently
Although respectable web crawlers follow the directives in a robots.txt file, each crawler might interpret the directives differently. You should know the proper syntax for addressing different web crawlers as some might not understand certain instructions.
A robotted page can still be indexed if linked to from other sites
While Google won't crawl or index the content blocked by a robots.txt file, we might still find and index a disallowed URL if it is linked from other places on the web. As a result, the URL address and, potentially, other publicly available information such as anchor text in links to the page can still appear in Google search results. To properly prevent your URL from appearing in Google search results, password-protect the files on your server, use the noindex meta tag or response header, or remove the page entirely.
