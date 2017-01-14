---
layout: article
title: "GreenfootKara - Solutions Chapter 5"
date: 2012-10-03 00:00
updated: 2014-03-08 00:00
slug: greenfoot-kara/chapter5-solutions
github: https://github.com/marcojakob/code.makery.ch/edit/master/collections/library/greenfoot-kara-en-chapter5-solutions.md
published: true
prettify: true
comments: true
sidebars:
- header: Articles in this Series
  body:
  - text: "Introduction"
    link: /library/greenfoot-kara/
    paging: Intro
  - text: "Background Info"
    link: /library/greenfoot-kara/background/
    icon-css: fa fa-fw fa-info
  - text: "Chapter 1: First Steps"
    link: /library/greenfoot-kara/chapter1/
    paging: 1
  - text: "Chapter 2: Program Flow"
    link: /library/greenfoot-kara/chapter2/
    paging: 2
  - text: "Chapter 3: Variables"
    link: /library/greenfoot-kara/chapter3/
    paging: 3
  - text: "Chapter 4: Sokoban Game"
    link: /library/greenfoot-kara/chapter4/
    paging: 4
  - text: "Chapter 5: Methods"
    link: /library/greenfoot-kara/chapter5/
    paging: 5
- header: Solutions
  body:
  - text: "Solutions Chapter 5"
    link: /library/greenfoot-kara/chapter5-solutions/
    icon-css: fa fa-fw fa-check-square-o
    active: true
- header: Downloads
  body:
  - text: scenarios-chapter-5-solutions.zip
    link: https://github.com/marcojakob/greenfoot-kara/releases/download/v2.1.1/scenarios-chapter-5-solutions.zip
    icon-css: fa fa-fw fa-file-archive-o
  - text: Page as Word File
    link: /library/convert-web-page-to-word/
    icon-css: fa fa-fw fa-file-word-o
languages: 
  header: Languages
  collection: library
  item: greenfoot-kara
  part: chapter5-solutions
  active: en
---

#### <i class="fa fa-check-square-o"></i> SOLUTION TASK 5.01: Baking a Cake

<pre class="prettyprint lang-java">
public class MyKaraIO extends KaraIO {
	
	public void act() {
		drawRectangle(21, 4);
		
		stop();
	}

	public void drawRectangle(int width, int height) {
		int i = 0;
		while (i &lt; height) {
			putLeafs(width);
			turnAround();
			multiMove(width);

			// Go to next line.
			turnRight();
			move();
			turnRight();

			i = i + 1;
		}
	}

	public void putLeafs(int count) {
		int i = 0;
		while (i &lt; count) {
			putLeaf();
			move();
			i = i + 1;
		}
	}

	public void multiMove(int steps) {
		int i = 0;
		while (i &lt; steps) {
			move();
			i = i + 1;
		}
	}

	public void turnAround() {
		turnLeft();
		turnLeft();
	}
}
</pre>


***

#### <i class="fa fa-check-square-o"></i> SOLUTION TASK 5.02: Candles on Cake

<pre class="prettyprint lang-java">
public class MyKaraIO extends KaraIO {
	
	public void act() {
		drawRectangle(21, 4);
		drawCandles(10);
		
		stop();
	}

	public void drawCandles(int count) {
		int i = 0;
		while (i &lt; count) {
			move();
			turnLeft();
			putLeafs(3);
			turnAround();
			multiMove(3);
			turnLeft();
			move();
			i = i + 1;
		}
	}

	public void drawRectangle(int width, int height) {
		// ...
	}

	public void putLeafs(int count) {
		// ...
	}

	public void multiMove(int steps) {
		// ...
	}

	public void turnAround() {
		// ...
	}
}
</pre>


***

#### <i class="fa fa-check-square-o"></i> SOLUTION TASK 5.03: Candles for Age

<pre class="prettyprint lang-java">
public class MyKaraIO extends KaraIO {

	public void act() {
		drawRectangle(21, 4);

		int age = intInput("How old is your grandmother?");
		drawCandles(age / 10);
		
		stop();
	}

	public void drawCandles(int count) {
		// ...
	}

	public void drawRectangle(int width, int height) {
		// ...
	}

	public void putLeafs(int count) {
		// ...
	}

	public void multiMove(int steps) {
		// ...
	}

	public void turnAround() {
		// ...
	}
}
</pre>


***

#### <i class="fa fa-check-square-o"></i> SOLUTION TASK 5.04: Layered Cake

<pre class="prettyprint lang-java">
public class MyKaraIO extends KaraIO {

	public void act() {
		int age = intInput("How old is your grandmother?");
		drawLayers(age / 10 - 5);
		
		stop();
	}

	public void drawLayers(int layers) {
		int currentWidth = 21;

		int i = 0;
		while (i &lt; layers) {
			drawRectangle(currentWidth, 2);
			move();
			move();

			currentWidth = currentWidth - 4;
			i = i + 1;
		}
	}

	public void drawRectangle(int width, int height) {
		// ...
	}

	public void putLeafs(int count) {
		// ...
	}

	public void multiMove(int steps) {
		// ...
	}

	public void turnAround() {
		// ...
	}
}
</pre>


