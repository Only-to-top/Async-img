# Async-img

<h1>Последовательная загрузка картинок</h1>

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <title>Document</title>
</head>
<body>

  <img data-src="https://picsum.photos/200" alt="">
  <img data-src="https://picsum.photos/201" alt="">
  <img data-src="https://picsum.photos/202" alt="">
  <img data-src="https://picsum.photos/203" alt="">
  <img data-src="https://picsum.photos/204" alt="">
  <img data-src="https://picsum.photos/205" alt="">

  <script>
  (async ()=> {
    for (let node of document.getElementsByTagName('img')) {
      await new Promise(res=> {
        node.src=node.dataset.src;
        node.onload = ()=>res();
      })
    }
  })();
  //Используется data-src вместо src
  </script>
  
</body>
</html>
```
