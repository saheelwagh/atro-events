. They are HTML-only templating components with no client-side runtime. You can spot an Astro component by its file extension: .astro.

Astro components are extremely flexible. Often, an Astro component will contain some reusable UI on the page, like a header or a profile card. At other times, an Astro component may contain a smaller snippet of HTML, like a collection of common <meta> tags that make SEO easy to work with. Astro components can even contain an entire page layout.

The most important thing to know about Astro components is that they don’t render on the client. They render to HTML either at build-time or on-demand using server-side rendering (SSR). You can include JavaScript code inside of your component frontmatter, and all of it will be stripped from the final page sent to your users’ browsers. The result is a faster site, with zero JavaScript footprint added by default.

When your Astro component does need client-side interactivity, you can add standard HTML <script> tags or UI Framework components.

Component Structure
An Astro component is made up of two main parts: the Component Script and the Component Template. Each part performs a different job, but together they provide a framework that is both easy to use and expressive enough to handle whatever you might want to build.

Astro uses a code fence (---) to identify the component script in your Astro component. If you’ve ever written Markdown before, you may already be familiar with a similar concept called frontmatter. Astro’s idea of a component script was directly inspired by this concept.


Component Props
An Astro component can define and accept props. These props then become available to the component template for rendering HTML. Props are available on the Astro.props global in your frontmatter script.

Here is an example of a component that receives a greeting prop and a name prop. Notice that the props to be received are destructured from the global Astro.props object

---
// Usage: <GreetingHeadline greeting="Howdy" name="Partner" />
const { greeting, name } = Astro.props;
---
<h2>{greeting}, {name}!</h2>
---
import GreetingHeadline from './GreetingHeadline.astro';
const name = 'Astro';
---
<h1>Greeting Card</h1>
<GreetingHeadline greeting="Hi" name={name} />
<p>I hope you have a wonderful day!</p>

Named Slots
An Astro component can also have named slots. This allows you to pass only HTML elements with the corresponding slot name into a slot’s location.

Slots are named using the name attribute:

---
import Header from './Header.astro';
import Logo from './Logo.astro';
import Footer from './Footer.astro';

const { title } = Astro.props;
---
<div id="content-wrapper">
  <Header />
  <slot name="after-header" />  <!--  children with the `slot="after-header"` attribute will go here -->
  <Logo />
  <h1>{title}</h1>
  <slot />  <!--  children without a `slot`, or with `slot="default"` attribute will go here -->
  <Footer />
  <slot name="after-footer" />  <!--  children with the `slot="after-footer"` attribute will go here -->
</div>
---
import Wrapper from '../components/Wrapper.astro';
---
<Wrapper title="Fred's Page">
  <img src="https://my.photo/fred.jpg" slot="after-header" />
  <h2>All about Fred</h2>
  <p>Here is some stuff about Fred.</p>
  <p slot="after-footer">Copyright 2022</p>
</Wrapper>


