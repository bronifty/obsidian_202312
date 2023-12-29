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
























