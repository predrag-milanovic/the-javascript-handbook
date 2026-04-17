# Maps

JavaScript offers maps, which are collections of key/value pairs. A map is a good fit when you want to add and remove entries dynamically.

Map keys are unique, so setting the same key again replaces the existing value:

```js
const map = new Map();

map.set("bertholdt", "shifter");
map.set("reiner", "warrior");
map.set("annie", "shifter");
map.set("bertholdt", "colossal titan");

console.log(map);
// Map { 'bertholdt' => 'colossal titan', 'reiner' => 'warrior', 'annie' => 'shifter' }
```

You can also remove entries when you no longer need them:

```js
map.delete("annie");

console.log(map);
// Map { 'bertholdt' => 'colossal titan', 'reiner' => 'warrior' }
```

Maps can be constructed from any iterable, and since maps are iterable themselves, you can use one map to copy another:

```js
const originalMap = new Map();
originalMap.set("bertholdt", "shifter");

const mapCopy = new Map(originalMap);

console.log(mapCopy);
// Map { 'bertholdt' => 'shifter' }
```
