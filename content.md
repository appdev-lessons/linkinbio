# Link in bio

Some social media apps, in particular Instagram, do not allow you to include links to other pages in posts. The only place you can include a URL is in your bio, and you can only include one. This soon led to a trend of people promoting something with a post, but including "Link in bio!" in the caption. They would then update the solitary link in their bio to the latest thing they wanted to promote.

Soon, a bunch of services cropped up that allow people to manage multiple links in a single, mobile-friendly page; and include a link to that page in their bio. The most popular of these is [Linktree](https://techcrunch.com/2020/10/26/linktree-raises-10-7m-for-its-lightweight-link-centric-user-profiles/), but there are many others.

Linktree has many users, from media companies to celebrities to, most likely, some of your friends — and maybe even you? Here are some examples:


HBO's Instagram bio:

<!-- ![](assets/linkinbio/linkinbio-hbo-profile.jpg){width="480"} -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1686178969/linkinbio-hbo-profile_iqaukm.jpg)

And HBO's list of links:

<!-- ![](assets/linkinbio/linkinbio-hbo-linktree.jpg){width="480"} -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1686178970/linkinbio-hbo-linktree_czyen1.jpg)

Katy Perry's Instagram bio:

<!-- ![](assets/linkinbio/linkinbio-katyperry-profile.jpg){width="480"} -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1686178969/linkinbio-katyperry-profile_clvqs0.jpg)

And Katy Perry's list of links:

<!-- ![](assets/linkinbio/linkinbio-katyperry-linktree.jpg){width="480"} -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1686178970/linkinbio-katyperry-linktree_xq72ik.jpg)

---

In this project, we're going to build our own mobile-friendly list of links that we can include in our social media profiles or anywhere else that we like. [Here's mine](https://rag.hu):


<!-- ![](assets/linkinbio/linkinbio-raghu-final.jpg) -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1686178972/linkinbio-raghu-final_hukzvw.jpg)

There are several benefits to writing our own rather than using a service like Linktree:

- We can use our own custom domain name for it; rather than `linktree.com/raghubetina`, notice that my URL is simply `rag.hu`.
- We don't have to pay. Linktree has a free tier with limited design options, but if you want access to the fun themes, analytics, or to remove the Linktree branding, you have to subscribe to their $5/mo or $9/mo plan.
- We have all the power of CSS at our fingerprints to customize the design. Linktree, like all "no code" tools, limits you to a set of pre-defined constraints that you have to work within. Not so if you're writing the code yourself.
    
    For example, if you [click through to mine](https://rag.hu/), you'll notice a lot of touches that aren't available options even on the paid Linktree plans: an animated background, a "frosted glass" effect on the links, etc.
- It's just plain fun!

Let's get started.

## Load assignment

Click the button to load the assignment:

LTI{Load Link in bio assignment}(https://grades.firstdraft.com/launch)[S9ymPy6WCsn18gLbByVbZQ7k]{vfdtzJb5bLYqYwuqgeRKpc5d}(7)[Link in bio Project]

Follow the instructions from the "Hello, World" HTML Lesson to:

* [fork the assignment](https://learn.firstdraft.com/lessons/106-hello-world#fork-the-project-repository), leaving the name alone so that you end up with a new `github.com/<your-username>/links` repository; and
* [create a Codespaces workspace](https://learn.firstdraft.com/lessons/106-hello-world#start-your-first-codespace).

## Getting started

* Once you are in the Codespaces workspace, you can run `rackup` as usual at the bash prompt to start the `puma` web server and begin adding files and viewing the changes in your live app preview. More about opening your [live app preview with `rackup` here](https://learn.firstdraft.com/lessons/106-hello-world#rackup-your-live-application-preview).

* Create a file called `index.html` in the root folder. Add the text "My link in bio" to that `index.html` file and make sure that it shows up when you refresh your app preview.

* [Make a commit and push the changes](https://learn.firstdraft.com/lessons/106-hello-world#git-commit-and-push) to publish the new `index.html` file on the `<your-username>/links` repo.

* In a bash prompt in the terminal tab, you can [already run `rake grade`](https://learn.firstdraft.com/lessons/125-using-rake-grade) to see a few simple specs that will be automatically graded. 
  * Just be sure to copy-paste the access token you got when you clicked the "Load assignment" button. If you closed that tab and need to get the token again, just click the "Load assignment" button again to open the interface (no need to do any forking this time).

Remember to commit early and commit often, occasionally pushing your changes to publish them on GitHub for safekeeping.

## First things first — the content

To start with, we need content. You'll probably want to gather:

- A profile picture for the top of the page. This doesn't have to be an image of you; it can be anything. [Unsplash](https://unsplash.com/) is a great resource for high quality stock images if you don't want to use an image of yourself.
- The URLs of your social media profiles. I used my GitHub, LinkedIn, Instagram, and Twitter pages.
- A list of links you want to share. I used a handful of essays and short stories that I find myself sharing with people often. [Here are some examples that you can peruse for inspiration](https://clickydrip.com/linktree-examples/).
- A thumbnail image for each link. I used a few strategies to find an image for each link:
    - [Search Google images](https://images.google.com/) and look for one hosted on wikimedia.org.
    - Searched [Unsplash](https://unsplash.com/) for a relevant image.
    - [Generate an image with AI](https://dezgo.com/).

I downloaded the image and then uploaded it to my Codespaces workspace by drag-and-dropping it into the root folder.

If you want to, you can use fake placeholder images and links for everything, but I encourage you to gather real content. It'll be more fun, you'll end up with a page that you can actually use on your social media profiles, and you'll have a good piece for your portfolio.

## Basic HTML Structure

Let's add our images, copy, and links into the `<body>` of our page. I wrapped each block of content in a `<div>` for now, to create some separation. I also gave each `<div>` a `class=""` attribute; since we haven't written any CSS yet, they don't do anything, but they help me remember what each `<div>` represents. Something like this:

```html
    <body>
      <div class="banner">
        <img src="profile-pic.jpg" alt="Raghu Betina headshot">
      </div>

      <div class="name">
        Raghu Betina
      </div>

      <div class="social-icons">
        <a href="https://github.com/raghubetina" target="_blank">
          GitHub
        </a>

        <a href="https://www.linkedin.com/in/raghubetina/" target="_blank">
          LinkedIn
        </a>

        <a href="https://www.instagram.com/raghubetina/" target="_blank">
          Instagram
        </a>

        <a href="https://twitter.com/raghubetina" target="_blank">
          Twitter
        </a>
      </div>

      <div class="link">
        <img
          src="https://www.ycombinator.com/assets/ycdc/yc-og-image-0cfa80cac837d64d9b4f0705950000b66906ac032791376bd721f246fafcc7b4.png">

        <a target="_blank" href="http://paulgraham.com/startupideas.html">How to Get Startup Ideas
          — Paul Graham</a>
      </div>

      <div class="link">
        <img src="/thumbnails/typography.jpg">

        <a target="_blank"
          href="https://practicaltypography.com/typography-in-ten-minutes.html">Typography in ten minutes — Matthew
          Butterick</a>
      </div>

      <div class="link">
        <img
          src="https://media.newyorker.com/photos/59096d451c7a8e33fb38e4ca/16:9/w_1280,c_limit/071210_r16884_p646.jpg">

        <a target="_blank" href="https://www.newyorker.com/magazine/2007/12/10/the-checklist/">A
          Life-Saving Checklist — The New Yorker</a>
      </div>

      <!-- Etc, for as many links as you want -->
    </body>
```

Of course, I also have the standard HTML boilerplate (`<html>`, `<head>`, `<body`) in order to make it a valid document. As a reminder:

* A `.html` document has 1 `body` and 1 `head` tag. (only 1 of each)
* Think of it like a person. I can’t see what’s going on inside your head, but I can see your body.
* We put things like links, titles, and rules in the head. What gets rendered in the browser goes in the body.

```html
<!DOCTYPE html>
<html>
  <head>
    <!-- where we tell the browser how to process the document: -->
        <!-- what title to put in the browser tab -->
        <!-- what style sheets to load -->
        <!-- what language to use -->
          <!-- we will always use a character set called UTF-8 -->
          <!-- UTF-8 allows for all languages as well as things like emoji -->
  </head>
  <body>
    <!-- content displayed to user (i.e. the stuff from the code block above) -->
  </body>
</html>
```

Two things to notice about my `<body>` content:

- I'm using the `target="_blank"` attribute on any links that I want to open in a new tab.
- For images that I am serving from my own root folder:
    - I created a subfolder called `thumbnails` to help keep things organized, and moved the images there.
    - When referencing the URL of the image in a `src=""` attribute, I start with a leading slash (which, as we know, indicates the root of the codebase) — e.g.:

        ```html
        <img src="/thumbnails/typography.jpg">
        ```

At this stage, your page technically serves its purpose — a collection of links people can click on — but it probably looks terrible, [like this](https://rag.hu/01-content).

## HTML Validator

If at any point your HTML breaks, or you suspect you e.g. forgot a closing tag but can't find it, [the W3C HTML Validator](https://validator.w3.org/#validate_by_input) might come in handy. Paste in your entire HTML document and click "Check", and it will give you a list of feedback. Some of them are yellow warnings and can be safely ignored for now, but any critical mistakes (like missing closing tags or quotation marks) will show up as red errors.

For example, if you run your HTML through the validator right now (try it), it will display a bunch of errors because we don't have `alt=""` attributes on our `<img>`s. These are important to include for accessibility reasons, and just in case the image breaks for some reason (i.e. the URL changes). We should add [descriptive alternative text](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#accessibility_concerns) for each image.

## View Source

You should try to type out your page yourself — avoid copy-pasting. Making mistakes, fixing them, and developing your own muscle memory is important.

That said, _after_ you've attempted it yourself, you can View Source (Windows: <kbd>Ctrl</kbd>+<kbd>U</kbd> or Mac: <kbd>Command</kbd>+<kbd>Option</kbd>+<kbd>U</kbd>) on any of my example intermediate pages to see my code.

## Sizing images

Now, let's start to make the page look better. Let's add a `<style>` element inside the `<head>` of the document so that we can begin applying CSS. We won't use an external stylesheet for now, since we're only planning to apply this CSS to a single page. Maybe we can start by giving the `body` some breathing room with top and bottom padding:

```html
<style>
  body {
    padding-top: 40px;
    padding-bottom: 40px;
  }
</style>
```

Let's start by sizing the profile picture. We need to give it a class so that we can apply CSS rules to it — let's call it `banner-image`:

```html
<div class="banner">
  <img src="profile-pic.jpg" alt="Raghu Betina headshot" class="banner-image">
</div>
```

Then, let's make the banner image 128 pixels by 128 pixels:

```css
<style>
  .banner-image {
    width: 128px;
    height: 128px;
  }
</style>
```

Unless your original image was exactly square, this probably will look squished when you check out the results. To solve this problem, we can use [the `object-fit` property](https://developer.mozilla.org/en-US/docs/Web/CSS/object-fit):

```css
.banner-image {
  width: 128px;
  height: 128px;
  object-fit: cover;
}
```

It's quite common to see circular profile pictures. If you want to, set a large `border-radius` to achieve that:

```css
.banner-image {
  width: 128px;
  height: 128px;
  object-fit: cover;
  border-radius: 128px;
}
```

I didn't use one on my profile picture, but you should feel free to get creative with [borders](https://developer.mozilla.org/en-US/docs/Web/CSS/border), as well.

Similarly, let's size all of the thumbnail images as 48px by 48px:

```css
.thumbnail {
  width: 48px;
  height: 48px;
  border-radius: 48px;
  object-fit: cover;
}
```

Don't forget to add the class to the relevant `<img>` elements. Now, your page should look [something like this](https://rag.hu/02-size-images) — much better.

## Basic colors

Let's add some color to make it easier to see how much space each element is occupying. We'll, at a minimum, need a color for the background of the entire page and for each link.

You can come up with your own palette, or you can use [Happy Hues](https://www.happyhues.co/), a nice set of curated color palettes.

I used [this palette](https://www.happyhues.co/palettes/10). I used the background color, headline color, button color, and button text color like this:

```css
body {
  background-color: #004643;
}

.name {
  color: #fffffe;
}

.social-icons a {
  color: #fffffe;
  text-decoration: none;
}

.link {
  background-color: #f9bc60;
}

.link a {
  color: #001e1d;
  text-decoration: none;
}
```

As you can see, I also removed the underlines from links with `text-decoration: none`.

Notice that I used the [descendant combinator](https://developer.mozilla.org/en-US/docs/Web/CSS/Descendant_combinator):

```css
.link a {
  /* ... */
}
```

This selector targets only `<a>` elements that are descendants of elements with class `link`. This is a handy alternative to adding a new class to all of the elements I'm interested in targeting.

<aside markdown="1">
If you want to become a pro at writing CSS selectors, I recommend an interactive tutorial/game called [CSS Diner](https://flukeout.github.io/). If you make it through all 32 levels, you'll be better than most front-end developers at writing advanced CSS selectors. In addition to making it easier to style your own pages, knowing how to write advanced selectors will pay dividends if you're interested in doing any web scraping.
</aside>

My page now [looks like this](https://rag.hu/03-basic-colors).

## Layout

Now, for the interesting part — laying out the elements where we want them on the page.

### Overall page layout

Since this is a relatively simple, single-column layout, we could stay in the normal flow mode and achieve most of the positioning that we want with `margin` and `padding`.

But let's use `display: flex` instead. It will make it much easier to do things like vertically center the text within each link's box.

First, I'll wrap all of our content — the `div.banner`, the `div.name`, the `div.social-icons`, and all of the `div.links` — within a new parent `<div>` with a class called `items`. This will make it easier for me to position and size everything uniformly. Then I will switch the layout mode of the new `div.items` from the default normal flow to `flex`:

```css
.items {
  display: flex;
}
```

If you try that and refresh your page, you'll see that all of the elements are now horizontally side-by-side. This is because the default `flex-direction` is `row`. Let's switch the `flex-direction` to `column` to lay them out vertically again:

```css
.items {
  display: flex;
  flex-direction: column;
}
```

If you refresh, you'll see the layout is vertical again. When we're using `display: flex` mode, we can use the `gap` property to provide some breathing room between each child element, rather than having to add `margin`:

```css
.items {
  display: flex;
  flex-direction: column;
  gap: 30px;
}
```

On laptop screens, the buttons are running all the way to the edge of the screen, which isn't very attractive. Let's set a `max-width` of around 640px (you choose a value that looks good to you):

```css
.items {
  display: flex;
  flex-direction: column;
  gap: 30px;
  max-width: 640px;
}
```

### Layout for each link

Within each link, it would be nice if:

- The thumbnail and text were vertically centered within the box.
- The text was horizontally centered in the space remaining next to the thumbnail.

`display: flex` to the rescue!

#### Vertically centering with align-items

We can vertically center child elements with the `align-items` property:

```css
.link {
  background-color: #f9bc60;
  display: flex;
  align-items: center;
}
```

If you refresh, the thumbnails should be lined up nicely with the link text.

#### flex-grow

Next, let's center the text of each link. I'm going to expand the existing rule that we have for `.link a`. Can we simply add `text-align: center` and call it a day?

```css
.link a {
  color: #001e1d;
  text-decoration: none;
  text-align: center;
}
```

If you refresh, you'll see that didn't work. Why?

To make it easier to see things while I am working on layouts, I often use the following hack:

```css
* {
  border: thin red solid;
}
```

This puts a thin red border around every element. Your page should now look something like this:


<!-- ![](/assets/linkinbio/linkinbio-before-flex-grow.png) -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1686178967/linkinbio-before-flex-grow_pos2of.png)

We can see that the `<a>` elements are only just wide enough to fit their content, so centering within them isn't doing anything. Instead, we want the `<a>` element to occupy all of the available space to the right of the thumbnail.

To achieve, this we can use [the `flex-grow` property](https://css-tricks.com/almanac/properties/f/flex-grow/):

```css
.link a {
  color: #001e1d;
  text-decoration: none;
  text-align: center;
  flex-grow: 1;
}
```

Now the `<a>` element grows to fill any available space, while the `<img>` element stays the same size (it still has the default value for `flex-grow`, which is `0`). And our text should be nicely centered since we already added the `text-align`.

#### justify-content

Now let's take care of centering the profile picture and name, as well as putting some breathing room between the social links.

Flexbox has [a wonderful property called `justify-content`](https://css-tricks.com/almanac/properties/j/justify-content/) that will help with all of these things:

```css
.name {
  color: #fffffe;
  display: flex;
  justify-content: center;
}

.banner {
  display: flex;
  justify-content: center;
}

.social-icons {
  display: flex;
  justify-content: space-around;
}
```

You could also use the same technique to center the `div.items` within the `<body>`:

```css
body {
  display: flex;
  justify-content: center;
}
```

But then we again need to tell the child elements to grow to take up all available space with `flex-grow`:

```css
.items {
  display: flex;
  flex-direction: column;
  gap: 30px;
  max-width: 640px;
  flex-grow: 1;
}
```

Our page layout should now look solid!


<!-- ![](assets/linkinbio/linkinbio-finished-layout.jpg) -->
![](https://res.cloudinary.com/dmxgp9oq2/image/upload/v1686178969/linkinbio-finished-layout_unknay.jpg)
{: .bleed-full }

Let's add a little bit of padding inside our `div.link`s:

```css
.link {
  background-color: #f9bc60;
  display: flex;
  align-items: center;
  padding: 5px;
}
```

It should now be safe to remove the `* { border: thin red solid; }` hack, unless you want to continue playing with layout, padding, etc.

Our page now looks [something like this](https://rag.hu/04-layout).

## Deploy!

Similar to "Hello, World", you have three options for deployment of your static app:

1. **Render.com**. This company offers a free tier without the need for a credit card. However, on the free tier web services are automatically spun down after 15 minutes of inactivity, so new visitors may experience a long delay when visiting your page.

2. **Fly.io**. This company requires a credit card for identity verification, but includes enough free allowance to run an app without any restrictions.

3. **GitHub Pages**. This option is completely free and does not require a credit card, but it will only work for static websites.

We recommend #1, Render.com, but you can choose any of them (or all of them, to see how they differ). Depending on which option you choose, find the appropriate next lesson on Canvas to deploy the "Link in bio" web site.

## This is the end of the required portion

This is the end of the required portion of this assignment. 

* Run `rake grade` in the bash prompt and make sure all the specs pass to get full credit. 
* In Canvas, submit the URL of your deployed app, either `.fly.dev` or `onrender.com` or `.github.io` (_not_ your Codespaces live app preview URL). If you are willing to share your creation, please also include "Add me to the showcase" in the submission text area.

## Make it your own

Now that we have the basics up and running, it's time for you to get creative and make it your own! You can continue to make changes, commit, and push them to deploy. We aren't grading for anything particular, so just have fun with it.

Here are a bunch of resources for you to explore:

### Fun design resources

The following are a collection of neat tools that will help you create interesting backgrounds, generate gradients and shadows, find font pairings, etc.

Glance at each one and pick one or two to integrate into your design. If you want to bounce ideas on things you can integrate, chat with an instructor.

Once you've picked something to add, try to figure out how to integrate it on your own; ask lots of questions when you get stuck.

#### Icons

To use Font Awesome icons (for example, for your LinkedIn/GitHub/Twitter/etc links), first include this in the `<head>` of your document:

```html
<!-- Connect Font Awesome -->
<script src="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.1/js/all.min.js"></script>
```

Then peruse [the icon list](https://fontawesome.com/search?m=free) and copy-paste the code examples into your HTML.

#### Fonts

- [The Ultimate Collection of Google Font Pairings (Displayed Beautifully with Classic Art)](https://heyreliable.com/ultimate-google-font-pairings/)
- Reading: [Typography in Ten Minutes](https://practicaltypography.com/typography-in-ten-minutes.html)

#### Images

- [Unsplash](https://unsplash.com/): Search engine for free stock images.
- [Dezgo](https://dezgo.com/): AI image generation.
- [Image Optimizer](http://www.imageoptimizer.net/): Reduce your images' filesize in case they're taking too long to load.
- [Clippy](https://bennettfeely.com/clippy/): Create geometric masks for your images.
  
#### Color palettes

- [Happy Hues](https://www.happyhues.co/)

#### Shadow generators

- [CSSMatic's Box Shadow Generator](https://www.cssmatic.com/box-shadow)

#### Gradient generators

- [Vivid Gradient Generator](https://learnui.design/tools/gradient-generator.html)
- [Easing Gradients](https://larsenwork.com/easing-gradients/)

#### Patterns

- [CSS Background Patterns](https://www.magicpattern.design/tools/css-backgrounds)
- [Repper](https://repper.app/)
- [Pocoloco](https://pocoloco.io/)

#### Generative art

- [Silk](http://weavesilk.com/)
- [Haikei](https://app.haikei.app/)
- [Tabbied](https://tabbied.com/select-artwork)
- [Broider](https://maxbittker.github.io/broider/)

#### Filters

- [https://css-tricks.com/almanac/properties/b/backdrop-filter/](https://css-tricks.com/almanac/properties/b/backdrop-filter/)
- [https://css-tricks.com/almanac/properties/f/filter/](https://css-tricks.com/almanac/properties/f/filter/)

---

### Always be committing

Be sure to make lots of git commits along the way as you work! Have fun ☺️
