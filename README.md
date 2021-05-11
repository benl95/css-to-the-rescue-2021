# CSS to the Rescue @cmda-minor-web 2020 - 2021

# Assignment

For the assignment I'm creating an interactive restaurant menu for a ramen shop.
The menu has an interactive cover with animations in a japanese theme.

-  [Live version](https://ramen-shop-css.netlify.app/)

# CSS Techniques used:

-  Flexbox
-  Grid
-  Responsive units (em, rem, vw, vh)
-  Gradients
-  Filters
-  Pseudo-elements
-  Transform
-  Clamp()
-  Min()
-  Max()
-  CSS Variables
-  Animation

# Restrictions and contexts

## Restrictions

-  2 Colors used
-  Responsive without media queries

## Context

-  Print-stylesheet
-  Prefers-reduced-motion

# Resit (Aanvulling)

In the first version of my menu I was writing a lot CSS code to style elements
without understanding the core concepts of CSS. This resulted in CSS code where
I styled each individual element, which is unecessary because of the inheritance
of of CSS. I also didn't use CSS variables which made my code really difficult
to maintain and adjust. The webpage also wasn't responsive enough because I
mainly used flexbox in combination with px and rem for the sizing units.

For the resit I decided to use the following techniques in CSS to make the page
reponsive without media queries and easier to adjust the code:

-  CSS Grid
-  CSS Variables
-  Clamp()
-  Min()
-  Max()
-  Vw/Vh

<details>
<summary>CSS Grid</summary>
<br>
I never worked with CSS Grid before and mainly used Flexbox for responsiveness for responsiveness because I was most comfortable with that.
For the resit I did some research on CSS Grid and tried to implement it into my menu. I was suprised how much easier it is to make a webpage responsive by using CSS Grid.

```html
<section id="ramen">
	<header>
		<h2>Ramen</h2>
	</header>
	<article>
		<h3>Hakata Shoyu Ramen</h3>
		<p>Pork based ramen topped with egg, charsiu, spring onions</p>
		<div>&euro; 14,95</div>
	</article>
	<article>
		<h3>Hakata Shio Ramen</h3>
		<p>Pork based ramen topped with egg, charsiu and bamboo shoots</p>
		<div>&euro; 14,95</div>
	</article>
	<article>
		<h3>Sesame Chicken</h3>
		<p>
			Chicken based ramen topped with egg, chicken charisu and spring onions
		</p>
		<div>&euro; 12,95</div>
	</article>
</section>
```

```css
main > section {
	display: grid;
	grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
	gap: 1em;
	width: clamp(16rem, 60vw, 70rem);
	border: var(--border);
	padding: var(--section-padding);
	border-radius: 3px;
	margin: var(--base-margin);
}
```

<details>
<summary>CSS Variables</summary>
<br>
</details>
Using CSS Variables made it much more easier for me to adjust my code and make changes on the fly. I will defenitely be using this from now on

```css
:root {
	--red: #ff0001;
	--black: #000000;
	--max-width: 1024px;
	--h2-font-size: clamp(1rem, 10vw, 2rem);
	--article-spacing: 0.5rem 0 0.5rem 0;
	--text-font: 'Montserrat', sans-serif;
	--header-weight: 600;
	--border: 1px solid var(--black);
	--section-padding: 0.6rem;
	--base-margin: 1rem 0 1rem 0;
	--nav-margin: 0 1rem 0 1rem;
	--sun-width: 2rem, 20vw, 6rem;
	--sun-height: 2rem, 7vh, 8rem;
	--max-vw: 100vw;
	--max-vh: 100vh;
}
```

</details>

<details>
<summary>Clamp()</summary>
<br>
I mainly used clamp() to make the font-sizes responsive based on the size of the viewport. I also used this technique to make the width of containers responsive. A really useful technique for responsiveness!

```css
article * {
	margin: var(--article-spacing);
	font-size: clamp(0.8rem, 5vw, 1rem);
}

main > section {
	display: grid;
	grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
	gap: 1em;
	width: clamp(16rem, 60vw, 70rem);
	border: var(--border);
	padding: var(--section-padding);
	border-radius: 3px;
	margin: var(--base-margin);
}
```

</details>

<details>
<summary>Min() and Max()</summary>
<br>
To make my mountain responsive I used the Min() and Max() and this made it so much easier! I was struggling to make my mountain responsive in my first version, but these functions were really helpful!

```css
section > span:nth-child(2) {
	display: block;
	width: 10vw;
	border-left: max(13vh, min(15vw, 21vh)) solid transparent;
	border-right: max(13vh, min(15vw, 21vh)) solid transparent;
	border-bottom: 15vh solid var(--black);
}
```

</details>

<details>
<summary>View width/View height</summary>
<br>
To make my elements reponsive for mobile as well I experimented with View width and View height. Using these sizing units made it much easier for me to make it responsive for mobile.

```css
section > span:nth-child(2) {
	display: block;
	width: 10vw;
	border-left: max(13vh, min(15vw, 21vh)) solid transparent;
	border-right: max(13vh, min(15vw, 21vh)) solid transparent;
	border-bottom: 15vh solid var(--black);
}
```

</details>

End result for the resit:

<img src="https://user-images.githubusercontent.com/43675725/117831674-164d1400-b275-11eb-86f5-560b1bb25526.png" width="800" height="800">

# Process

## Week 1

Chosen assignment: Zen Garden Personal goal: create shapes and try to animate
them

Before starting with the assignment I went on Pinterest to find some inspiration
for a design. I knew I already wanted to do something with Japanese food and
eventually I chose a few ramen menus/posters to base my design off and try to
recreate certain things I saw in CSS.

-  [Pinterest inspiration board](https://nl.pinterest.com/benlangenberg987/door-mij-bewaard)

The next day I started experimenting with `clip-path` to create different
shapes. Using clip-path I managed to create a ramen bowl with chopsticks on top.
I also animated the ramen bowl by using `keyframes`.

I experimented with the following CSS techniques for the first time:

-  Keyframes/animations
-  Creating shapes with clip-path
-  Using pseudo-elements

## Week 2

At the start of week 2 I conceptualized a bit and I had the idea to create a
cover for the menu. On the cover I will mainly be experimenting with CSS and try
to do all sorts of crazy stuff. With this in mind I looked at things I could try
to recreate in CSS and I managed to create Mt. Fuji with a cloud hovering
besides it as well!

For the menu I wanted to implement the imperial Japanese flag in the design and
I recreated it using `radial-gradient` and `repeating-conic-gradient`

I decided to remove the chopsticks from the ramen bowl and use that circle as a
rising sun instead. Using `animations` I made the sun rise from behind the
mountain to recreate the effect of a rising sun.

During this week I experimented with the following CSS techniques:

-  Filter()
-  Radial-gradient
-  Repeating-conic-gradient
-  Using a japanese font
-  Transform()

## Week 3

In the last week finished the cover and the last thing I had to do was create
the menu for the actual dishes. Creating the menu was particularly tedious in my
opinion because my elements were nested and I had to get my head around using
the correct CSS selectors to select a element in CSS.

A personal goal of mine was to try to create some kind of pattern using CSS as
well. By making a wavy line using `pseudo-elements` I managed to create a wavy
line that resembles a noodle strand.

The final version looks as follows:

![A-template-for-a-responsive-restaurant-menu](https://user-images.githubusercontent.com/43675725/109826216-dc3f1080-7c3a-11eb-976e-924ebb10f871.png)
