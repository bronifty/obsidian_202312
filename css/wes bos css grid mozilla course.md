- .container>.item{$}*10
```html
<div class="container">
      <div class="item">1</div>
      <div class="item">2</div>
      <div class="item">3</div>
      <div class="item">4</div>
      <div class="item">5</div>
      <div class="item">6</div>
      <div class="item">7</div>
      <div class="item">8</div>
      <div class="item">9</div>
      <div class="item">10</div>
    </div>

    <style>
      .container {
        display: grid;
        grid-template-columns: 200px 500px;
        grid-template-rows: 200px 100px 400px;
        gap: 20px;
      }
    </style>

```

- after the first 3 rows they size themselves via implicit grid

```html
 <body>
    <div class="container">
      <div class="item">1</div>
      <div class="item">2</div>
      <div class="item">3</div>
      <div class="item">4</div>
      <div class="item">5</div>
      <div class="item">6</div>
    </div>

    <style>
      .container {
        display: grid;
        gap: 20px;
        grid-template-columns: 200px 400px;
        grid-auto-rows: 50px;
      }
    </style>
```

```html
<div class="container">
      <div class="item">1</div>
      <div class="item">2</div>
      <div class="item">3</div>
      <div class="item">4</div>
      <div class="item">5</div>
      <div class="item">6</div>
    </div>

    <style>
      .container {
        display: grid;
        gap: 20px;
        grid-template-columns: 200px 400px;
        grid-auto-flow: column;
        grid-auto-columns: 100px;
        grid-auto-rows: 50px;
      }
    </style>
```

- auto keyword is the size of the content

```html
<div class="container">
      <div class="item">1</div>
      <div class="item">2</div>
      <div class="item">3</div>
      <div class="item">4</div>
      <div class="item">5</div>
      <div class="item">6</div>
      <div class="item">7</div>
      <div class="item">8</div>
      <div class="item">9</div>
      <div class="item">10</div>
      <div class="item">11</div>
      <div class="item">12</div>
      <div class="item">13</div>
      <div class="item">14</div>
      <div class="item">15</div>
    </div>

    <style>
      .container {
        border: 10px solid var(--yellow);
        display: grid;
        gap: 20px;
        grid-template-columns: auto 1fr;
      }
    </style>
  </body>
```
![](./auto.png)

- repeat
```html
<style>
      .container {
        border: 10px solid var(--yellow);
        display: grid;
        gap: 20px;
        grid-template-columns: 100px repeat(2, auto 1fr);
      }
    </style>
```


- item spanning
```html
<div class="container">
      <div class="item item1">1</div>
      <div class="item item2">2</div>
      <div class="item item3">3</div>
      <div class="item item4">4</div>
      <div class="item item5">5</div>
      <div class="item item6">6</div>
      <div class="item item7">7</div>
      <div class="item item8">8</div>
      <div class="item item9">9</div>
      <div class="item item10">10</div>
      <div class="item item11">11</div>
      <div class="item item12">12</div>
      <div class="item item13">13</div>
      <div class="item item14">14</div>
      <div class="item item15">15</div>
      <div class="item item16">16</div>
      <div class="item item17">17</div>
      <div class="item item18">18</div>
      <div class="item item19">19</div>
      <div class="item item20">20</div>
      <div class="item item21">21</div>
      <div class="item item22">22</div>
      <div class="item item23">23</div>
      <div class="item item24">24</div>
      <div class="item item25">25</div>
      <div class="item item26">26</div>
      <div class="item item27">27</div>
      <div class="item item28">28</div>
      <div class="item item29">29</div>
      <div class="item item30">30</div>
    </div>

    <style>
      .container {
        border: 10px solid var(--yellow);
        display: grid;
        gap: 20px;
        grid-template-columns: repeat(5, 1fr);
      }
      .item9 {
        background: mistyrose;
        grid-column: span 2;
      }
    </style>
```
![](./item-spanning.png)

- more spanning
	- implicit columns
```html
<div class="container">
      <div class="item item1">1</div>
      <div class="item item2">2</div>
      <div class="item item3">3</div>
      <div class="item item4">4</div>
      <div class="item item5">5</div>
      <div class="item item6">6</div>
      <div class="item item7">7</div>
      <div class="item item8">8</div>
      <div class="item item9">9</div>
      <div class="item item10">10</div>
      <div class="item item11">11</div>
      <div class="item item12">12</div>
      <div class="item item13">13</div>
      <div class="item item14">14</div>
      <div class="item item15">15</div>
      <div class="item item16">16</div>
      <div class="item item17">17</div>
      <div class="item item18">18</div>
      <div class="item item19">19</div>
      <div class="item item20">20</div>
      <div class="item item21">21</div>
      <div class="item item22">22</div>
      <div class="item item23">23</div>
      <div class="item item24">24</div>
      <div class="item item25">25</div>
      <div class="item item26">26</div>
      <div class="item item27">27</div>
      <div class="item item28">28</div>
      <div class="item item29">29</div>
      <div class="item item30">30</div>
    </div>

    <style>
      .container {
        border: 10px solid var(--yellow);
        display: grid;
        gap: 20px;
        grid-template-columns: repeat(5, 1fr);
      }
      .item9 {
        background: mistyrose;
        grid-column: span 10;
        grid-row: span 2;
      }
    </style>
```
![](./span-implicit-columns.png)

- grid-column is shorthand for grid-column-start and grid-column end; let's make it explicit in order to place the item in a specific location on the grid
```html
<div class="container">
      <div class="item item1">1</div>
      <div class="item item2">2</div>
      <div class="item item3">3</div>
      <div class="item item4">4</div>
      <div class="item item5">5</div>
      <div class="item item6">6</div>
      <div class="item item7">7</div>
      <div class="item item8">8</div>
      <div class="item item9">9</div>
      <div class="item item10">10</div>
      <div class="item item11">11</div>
      <div class="item item12">12</div>
      <div class="item item13">13</div>
      <div class="item item14">14</div>
      <div class="item item15">15</div>
      <div class="item item16">16</div>
      <div class="item item17">17</div>
      <div class="item item18">18</div>
      <div class="item item19">19</div>
      <div class="item item20">20</div>
      <div class="item item21">21</div>
      <div class="item item22">22</div>
      <div class="item item23">23</div>
      <div class="item item24">24</div>
      <div class="item item25">25</div>
      <div class="item item26">26</div>
      <div class="item item27">27</div>
      <div class="item item28">28</div>
      <div class="item item29">29</div>
      <div class="item item30">30</div>
    </div>

    <style>
      .container {
        border: 10px solid var(--yellow);
        display: grid;
        gap: 20px;
        grid-template-columns: repeat(5, 1fr);
      }
      .item9 {
        background: mistyrose;
        grid-column-start: 2;
        grid-column-end: 5;
      }
    </style>
```
![](./grid-column-start-end.png)

- now we can use the shorthand
```html
<div class="container">
      <div class="item item1">1</div>
      <div class="item item2">2</div>
      <div class="item item3">3</div>
      <div class="item item4">4</div>
      <div class="item item5">5</div>
      <div class="item item6">6</div>
      <div class="item item7">7</div>
      <div class="item item8">8</div>
      <div class="item item9">9</div>
      <div class="item item10">10</div>
      <div class="item item11">11</div>
      <div class="item item12">12</div>
      <div class="item item13">13</div>
      <div class="item item14">14</div>
      <div class="item item15">15</div>
      <div class="item item16">16</div>
      <div class="item item17">17</div>
      <div class="item item18">18</div>
      <div class="item item19">19</div>
      <div class="item item20">20</div>
      <div class="item item21">21</div>
      <div class="item item22">22</div>
      <div class="item item23">23</div>
      <div class="item item24">24</div>
      <div class="item item25">25</div>
      <div class="item item26">26</div>
      <div class="item item27">27</div>
      <div class="item item28">28</div>
      <div class="item item29">29</div>
      <div class="item item30">30</div>
    </div>

    <style>
      .container {
        border: 10px solid var(--yellow);
        display: grid;
        gap: 20px;
        grid-template-columns: repeat(5, 1fr);
      }
      .item9 {
        background: mistyrose;
        grid-column: 2/6;
      }
    </style>
```
![](./grid-column-shorthand.png)

- span 2 end at 6 (gives you span 2 starting from the end)
```html
<style>
      .container {
        border: 10px solid var(--yellow);
        display: grid;
        gap: 20px;
        grid-template-columns: repeat(5, 1fr);
      }
      .item9 {
        background: mistyrose;
        grid-column: span 2/6;
      }
    </style>
```
![](./span2-from-the-end.png)

- tell it where to start and how far to go
```css
.item9 {
background: mistyrose;
grid-column: 1 / span 2;
}
```
![](./column1-span2.png)

- full width
```css
.item9 {
        background: mistyrose;
        grid-column: 1 / -1;
      }
```
![](./full-width.png)

- offset from the end
```css
.item9 {
        background: mistyrose;
        grid-column: 1 / -2;
      }
```
![](./offset-from-end.png)

- grid-row
	- puts it out of order 
```css
.item9 {
        background: mistyrose;
        grid-column: 1 / -2;
        grid-row: 4 / span 2;
      }
```
![](./grid-row.png)

- take up the entire explicit grid with 1 / -1
```css
.container {
        border: 10px solid var(--yellow);
        display: grid;
        gap: 20px;
        grid-template-columns: repeat(5, 1fr);
        grid-template-rows: repeat(5, 1fr);
      }
      .item9 {
        background: mistyrose;
        grid-column: 1 / -1;
        grid-row: 1 / -1;
      }
```
![](./whole-grid.png)

- grid-column span 2 grid-row 1 negative 1
```css
.item9 {
        background: mistyrose;
        grid-column: span 2;
        grid-row: 1 / -1;
      }
      ```
![](./sidebar-max-rows.png)

- practice
```css
.container {
        display: grid;
        grid-gap: 20px;
        /* Make the grid 10 columns wide, every other taking up twice the free space */
        grid-template-columns: repeat(5, 1fr 2fr);
        /* Make the grid have 10 explicit rows, 50px high each */
        grid-template-rows: repeat(10, 50px);
      }

      /* With Item 1, start at col 3 and go until 5 */
      .item1 {
        grid-column: 3 / 5;
      }

      /* With Item 2, start at col 5 and go until the end */
      .item2 {
        grid-column: 5 / -1;
      }

      /* Make Item 5 double span 2 cols and rows */
      .item5 {
        grid-column: span 2;
        grid-row: span 2;
      }

      /* Make Item 8 two rows high */
      .item8 {
        grid-row: span 2;
      }

      /* Make Item 15 span the entire grid width */
      .item15 {
        grid-column: 1 / -1;
      }

      /* Make item 18 span 4 widths, but end at 9 */
      .item18 {
        grid-column: span 4 / 9;
      }

      /* Make item 20 start at row 4 and have a height of 3 rows */
      .item20 {
        grid-row: 4 / span 3;
      }
      ```
![](./practice.png)













