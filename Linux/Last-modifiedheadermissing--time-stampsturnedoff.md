The wget -N switch does work, but a lot of web servers don't send the Last-Modified header for various reasons. For example, dynamic pages (PHP or any CMS, etc.) have to actively implement the functionality (figure out when the content was last modified, and send the header). Some do, while some don't.

There really isn't another reliable way to check if a file has been changed, either.
