# Замітки щодо виконання лабораторних робіт по курсу Browser-based Models with TensorFlow.js

https://www.coursera.org/learn/browser-based-models-tensorflow

- розширення WebServer вже не підтримується, тому його не можна використовувати, натомість у Brackets є вбудований сервер на базі Node.js (https://community.deeplearning.ai/t/web-server-for-chrome-no-longer-supported-on-chrome/219533/5)
- відкривається порожня сторінка і це нормально, бо там треба використовувати консоль
- видає помилку `DevTools failed to load source map: Could not load content for https://cdn.jsdelivr.net/npm/@tensorflow/tf.min.js.map: Помилка HTTP: код статусу 404, net::ERR_HTTP_RESPONSE_CODE_FAILURE`, але все одно працює
- Варто почитати довідку про [Dataset](https://js.tensorflow.org/api/latest/?_gl=1*t6m8cx*_ga*MTkwNTc5NjI5MS4xNjgwNDIzNzk0*_ga_W0YLR4190T*MTY4ODMxMzE0Ny4xOC4xLjE2ODgzMTMxNDcuMC4wLjA.#class:data.Dataset) та про методи, які використані в лабі. Погратися з виводами, наприклад:

```js
var tmp = await trainingData.toArray();
console.log (tmp);
tmp = await convertedTrainingData.toArray();
console.log (tmp);
```



