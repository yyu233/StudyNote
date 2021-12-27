The server-side rendering approach is perfect for delivering static content, such as WordPress blogs. It’s also good for SEO because the crawlers can easily read the generated content.

However, modern websites are highly dependent on AJAX. On such websites, content for a particular module or a section of a page has to be fetched and rendered on the fly.

Therefore, server-side rendering doesn’t help much. For every AJAX-request, instead of sending just the required content to the client, the approach generates the entire page on the server. This process consumes unnecessary bandwidth and also fails to provide a smooth user experience.

A big downside to this is that, once the number of concurrent users on the website rises, it puts an unnecessary load on the server.

Client-side rendering works best for modern dynamic AJAX-based websites.

However, we can leverage a hybrid approach, to get the most out of both techniques. We can use server-side rendering for the home page and for the other static content on our website and use client-side rendering for the dynamic pages.
