

Astro was designed to make styling and writing CSS a breeze. Write your own CSS directly inside of an Astro component or import your favorite CSS library like Tailwind. Advanced styling languages like Sass and Less are also supported.

Astro <style> CSS rules are automatically scoped by default. Scoped styles are compiled behind-the-scenes to only apply to HTML written inside of that same component. The CSS that you write inside of an Astro component is automatically encapsulated inside of that component.


External Styles
There are two ways to resolve external global stylesheets: an ESM import for files located within your project source, and an absolute URL link for files in your public/ directory, or hosted outside of your project.

