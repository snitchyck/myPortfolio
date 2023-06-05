<div class="container">
    <a href="/blog">Домой</a>
    <slot />
  </div>
  <style>
    .container {
      margin: 50px auto;
      max-width: 800px;
      padding: 0 20px;
    }
    a{
      color:blueviolet; 
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      font-weight: bolder;
    }
  </style>