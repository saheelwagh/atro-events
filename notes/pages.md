Pages are files that live in the src/pages/ subdirectory of your Astro project. 
They are responsible for handling routing, 
data loading, and 
overall page layout for every page in your website.

Pages are files that live in the src/pages/ subdirectory of your Astro project. They are responsible for handling routing, data loading, and overall page layout for every page in your website.


Write standard HTML <a> elements in your Astro pages to link to other pages on your site. Use a URL path relative to your root domain as your link, not a relative file path.

For example, to link to https://example.com/authors/sonali/ from any other page on example.com:

Read more <a href="/authors/sonali/">about Sonali</a>.

A page must produce a full HTML document. If not explicitly included, Astro will add the necessary <!DOCTYPE html> declaration and <head> content to any .astro component located within src/pages/ by default. You can opt-out of this behavior on a per-component basis by marking it as a partial page.

To avoid repeating the same HTML elements on every page, you can move common <head> and <body> elements into your own layout components. You can use as many or as few layout components as you’d like.

Files with the .html file extension can be placed in the src/pages/ directory and used directly as pages on your site. Note that some key Astro features are not supported in HTML Components.



---
import MySiteLayout from '../layouts/MySiteLayout.astro';
---
<MySiteLayout>
  <p>My page content, wrapped in a layout!</p>
</MySiteLayout>



or a custom 404 error page, you can create a 404.astro or 404.md file in /src/pages.

This will build to a 404.html page. Most deploy services will find and use it.

Your Astro project code must be rendered to HTML in order to be displayed on the web.

Astro pages, routes, and API endpoints can be either pre-rendered at build time or rendered on demand by a server when a route is requested. With Astro islands, you can also include some client-side rendering when necessary.

In Astro, most of the processing occurs on the server, instead of in the browser. This generally makes your site or app faster than client-side rendering when viewed on less-powerful devices or on slower internet connections. Server-rendered HTML is fast, SEO friendly, and accessible by default.

