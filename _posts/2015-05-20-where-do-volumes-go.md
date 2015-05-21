---
layout: post
title: Where Do Volumes Go?
unlisted: true
---

## Task
> 1. Using the TAQ data, compute the market shares for the different stock exchanges for a representative sample of stocks (it should include GOOG, BAC, and then a representative sample of other stocks, the size of the sample can depend on what's feasible computationally).
> 
> 2. Focus on calendar year 2014, and compute volumes and market shares for each exchange for each trading day, dividing the day into the opening auction, regular trading, closing auction, and after-hours trading.

## Data
The data consisted of all trades from **01-Jan-2014 to 31-Dec-2014**.

The trades covered the symbols: **BAC, GOOG, BHP, BRKA, FE, RSH, SLV, T, XOM**.

A trade's time of day was inferred from Sale Condition as follows:
<table>
  <thead>
    <tr>
      <th>Time of Day</th>
      <th>Sale Condition</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Open</td>
      <td>O, Q</td>
    </tr>
    <tr>
      <td>Close</td>
      <td>M, 6</td>
    </tr>
    <tr>
      <td>After-Hours</td>
      <td>T, U</td>
    </tr>
    <tr>
      <td>Regular</td>
      <td>Everything else</td>
    </tr>
  </tbody>
</table>

## Overall Look at Exchange Market Shares
[Over all trades, the volumes were distributed across exhanges as such.](http://rcharts.github.io/viewer/?a2c6f9b03902566cfb76)
<table>
  <thead>
    <tr><th>Exchange</th><th>Proportion</th></tr>
  </thead>
  <tbody>
    <tr><td>BATS</td><td>.05971</td></tr>
    <tr><td>BATS Y</td><td>.03509</td></tr>
    <tr><td>CBOE</td><td>.0008565</td></tr>
    <tr><td>Chicago</td><td>.006891</td></tr>
    <tr><td>Direct Edge A</td><td>.03483</td></tr>
    <tr><td>Direct Edge X</td><td>.07810</td></tr>
    <tr><td>FINRA</td><td>.3828</td></tr>
    <tr><td>NASDAQ</td><td>.005666</td></tr>
    <tr><td>NASDAQ OMX</td><td>.0960</td></tr>
    <tr><td>NASDAQ OMX BX</td><td>.03797</td></tr>
    <tr><td>NASDAQ OMX PSX</td><td>.005196</td></tr>
    <tr><td>National</td><td>.002492</td></tr>
    <tr><td>NYSE</td><td>.1824</td></tr>
    <tr><td>NYSE Arca SM</td><td>.07202</td></tr>
    <tr><td>NYSE MMKT</td><td>.00005679</td></tr>
  </tbody>
</table>

Most symbols had similar profiles in exchange market share. [To illustrate, stocks BHP, FE, and XOM were chosen since their volumes were at comparable scales.](http://rcharts.github.io/viewer/?c0e1fc17977fa20a3994)

[Only GOOG had a exchange market share profile which differed somewhat noticeably.](
http://rcharts.github.io/viewer/?1e2ef2392dcfe731ef83) (SLV also had a slight difference, with no NYSE representation.)

[We can also look at the way volumes were spread out over exchanges based on Time of Day.](http://rcharts.github.io/viewer/?ba03ed4250a3839722c5)

## Exchange Volumes and Market Shares Over 2014
The following graphs illustrate the extent of day-to-day consistency for the trends in the last rChart.

With so many exchanges, it may be helpful to amalgamate categories:
![Regular Hours Market Share](https://github.com/TeddyCho/TeddyCho.github.io/blob/master/_posts/img/Regular2014.png)
We see similar exchange market shares for both the opening and closing auctions:
![Opening Auction Market Share](https://github.com/TeddyCho/TeddyCho.github.io/blob/master/_posts/img/Open2014.png)
![Closing Auction Market Share](https://github.com/TeddyCho/TeddyCho.github.io/blob/master/_posts/img/Close2014.png)
After-Hours trading has a different profile for exchange market shares:
![After-Hours Market Share](https://github.com/TeddyCho/TeddyCho.github.io/blob/master/_posts/img/After-Hours2014.png)

## Some Notes
Running my code on the above data, consisting 64209422 rows, took 495 seconds on a 2.4 GHz/4GB laptop.

Some trades had an exchange code which did not correspond to anything listed in the [spec sheet](www.nyxdata.com/doc/224904).

<div class="message">
  Howdy! This is an example blog post that shows several types of HTML content supported in this theme.
</div>

Cum sociis natoque penatibus et magnis <a href="#">dis parturient montes</a>, nascetur ridiculus mus. *Aenean eu leo quam.* Pellentesque ornare sem lacinia quam venenatis vestibulum. Sed posuere consectetur est at lobortis. Cras mattis consectetur purus sit amet fermentum.

> Curabitur blandit tempus porttitor. Nullam quis risus eget urna mollis ornare vel eu leo. Nullam id dolor id nibh ultricies vehicula ut id elit.

Etiam porta **sem malesuada magna** mollis euismod. Cras mattis consectetur purus sit amet fermentum. Aenean lacinia bibendum nulla sed consectetur.

## Inline HTML elements

HTML defines a long list of available inline tags, a complete list of which can be found on the [Mozilla Developer Network](https://developer.mozilla.org/en-US/docs/Web/HTML/Element).

- **To bold text**, use `<strong>`.
- *To italicize text*, use `<em>`.
- Abbreviations, like <abbr title="HyperText Markup Langage">HTML</abbr> should use `<abbr>`, with an optional `title` attribute for the full phrase.
- Citations, like <cite>&mdash; Mark otto</cite>, should use `<cite>`.
- <del>Deleted</del> text should use `<del>` and <ins>inserted</ins> text should use `<ins>`.
- Superscript <sup>text</sup> uses `<sup>` and subscript <sub>text</sub> uses `<sub>`.

Most of these elements are styled by browsers with few modifications on our part.

## Heading

Vivamus sagittis lacus vel augue rutrum faucibus dolor auctor. Duis mollis, est non commodo luctus, nisi erat porttitor ligula, eget lacinia odio sem nec elit. Morbi leo risus, porta ac consectetur ac, vestibulum at eros.

### Code

Cum sociis natoque penatibus et magnis dis `code element` montes, nascetur ridiculus mus.

{% highlight js %}
// Example can be run directly in your JavaScript console

// Create a function that takes two arguments and returns the sum of those arguments
var adder = new Function("a", "b", "return a + b");

// Call the function
adder(2, 6);
// > 8
{% endhighlight %}

Aenean lacinia bibendum nulla sed consectetur. Etiam porta sem malesuada magna mollis euismod. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa.

### Lists

Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Aenean lacinia bibendum nulla sed consectetur. Etiam porta sem malesuada magna mollis euismod. Fusce dapibus, tellus ac cursus commodo, tortor mauris condimentum nibh, ut fermentum massa justo sit amet risus.

* Praesent commodo cursus magna, vel scelerisque nisl consectetur et.
* Donec id elit non mi porta gravida at eget metus.
* Nulla vitae elit libero, a pharetra augue.

Donec ullamcorper nulla non metus auctor fringilla. Nulla vitae elit libero, a pharetra augue.

1. Vestibulum id ligula porta felis euismod semper.
2. Cum sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus.
3. Maecenas sed diam eget risus varius blandit sit amet non magna.

Cras mattis consectetur purus sit amet fermentum. Sed posuere consectetur est at lobortis.

<dl>
  <dt>HyperText Markup Language (HTML)</dt>
  <dd>The language used to describe and define the content of a Web page</dd>

  <dt>Cascading Style Sheets (CSS)</dt>
  <dd>Used to describe the appearance of Web content</dd>

  <dt>JavaScript (JS)</dt>
  <dd>The programming language used to build advanced Web sites and applications</dd>
</dl>

Integer posuere erat a ante venenatis dapibus posuere velit aliquet. Morbi leo risus, porta ac consectetur ac, vestibulum at eros. Nullam quis risus eget urna mollis ornare vel eu leo.

### Tables

Aenean lacinia bibendum nulla sed consectetur. Lorem ipsum dolor sit amet, consectetur adipiscing elit.

<table>
  <thead>
    <tr>
      <th>Name</th>
      <th>Upvotes</th>
      <th>Downvotes</th>
    </tr>
  </thead>
  <tfoot>
    <tr>
      <td>Totals</td>
      <td>21</td>
      <td>23</td>
    </tr>
  </tfoot>
  <tbody>
    <tr>
      <td>Alice</td>
      <td>10</td>
      <td>11</td>
    </tr>
    <tr>
      <td>Bob</td>
      <td>4</td>
      <td>3</td>
    </tr>
    <tr>
      <td>Charlie</td>
      <td>7</td>
      <td>9</td>
    </tr>
  </tbody>
</table>

Nullam id dolor id nibh ultricies vehicula ut id elit. Sed posuere consectetur est at lobortis. Nullam quis risus eget urna mollis ornare vel eu leo.

-----

Want to see something else added? <a href="https://github.com/poole/poole/issues/new">Open an issue.</a>
