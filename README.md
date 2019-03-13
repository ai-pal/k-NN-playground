# Learn K-NN with JS :sunglasses:

This repository focuses on developing a interactive ground to understand K-NN algorithm with the :heart: of `JS`.

For this mission we use a popular game knows as [Plinko](https://www.youtube.com/watch?v=me4SV_tuMSE).

## How we Progress

Initially we will collect the following data of balls.

* Drop position
* Bounciness
* Ball Size
* Bucket ball fall into

Then we will use our `knn` algorithm to predict the bucket of a ball drop from determined position.

## K-NN Algorithm using Lodash

```js
function knn(data, point, k) {
    return _.chain(data)
        .map(row => {
            return [distance(_.initial(row), point), _.last(row)]
        })
        .sortBy(row => row[0])
        .slice(0, k)
        .countBy(row => row[1])
        .toPairs()
        .sortBy(row => row[1])
        .last()
        .first()
        .parseInt()
        .value();
}
```
