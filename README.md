# totally-random

A utility class to help with random value generation.

---

## Table of Contents

- [Installation](https://github.com/superhackerboy/totally-random#Installation)
- [Importing](https://github.com/superhackerboy/totally-random#Importing)
- [Functions](https://github.com/superhackerboy/totally-random#Between)
  - [Between](https://github.com/superhackerboy/totally-random#Between)
  - [Boolean](https://github.com/superhackerboy/totally-random#Boolean)
  - [Color](https://github.com/superhackerboy/totally-random#Color)
  - [From (Array)](https://github.com/superhackerboy/totally-random#From)
  - [Percentage](https://github.com/superhackerboy/totally-random#Percent)
  - [Shuffle](https://github.com/superhackerboy/totally-random#Shuffle)
  - [String](https://github.com/superhackerboy/totally-random#String)
  - [To (Number)](https://github.com/superhackerboy/totally-random#To)
- [Contributing](https://github.com/superhackerboy/totally-random#Contributing)
- [License](https://github.com/superhackerboy/totally-random#License)

## Installation

```javascript
npm i totally-random
```

### Importing

```javascript
const TotallyRandom = require("totally-random");
const random = new TotallyRandom();
```

You may also import this package from [unpkg](https://unpkg.com/browse/totally-random/) for browser use.

All numbers are _inclusive_. If you use an API or another technique to get random numbers (i.e. [RANDOM.org](https://random.org/)), you may supply your own function in the constructor. It must return a floating point number between 0 and 1, not including 1.

```javascript
const random = new TotallyRandom(randomFunction);
```

---

## Between

### `.between(num1, num2, [count = 1])`

Return a number, or array of numbers, within a given range.

#### Parameters

| Parameter        | Type   | Description                                                         |
| ---------------- | ------ | ------------------------------------------------------------------- |
| num1             | Number | The beginning number of the range                                   |
| num2             | Number | The ending number of the range                                      |
| count (Optional) | Number | The amount of numbers to include in the returned array. Default = 1 |

#### Example

```javascript
random.between(25, 50);
// 34

random.between(100, 200, 3);
// [192, 125, 167]
```

## Boolean

### `.boolean([count = 1])`

Return a boolean or array or booleans

#### Parameters

| Parameter        | Type   | Description                                                          |
| ---------------- | ------ | -------------------------------------------------------------------- |
| count (Optional) | Number | The amount of booleans to include in the returned array. Default = 1 |

#### Example

```javascript
random.boolean();
// false

random.boolean(5);
// [true, false, false, true, false]
```

## Color

### `.color([option = "hex"])` | `.colour([option = "hex"])`

Returns a random color in the form of a Hexcode, RGB, RGBA, HSL, or HSLA value.

#### Parameters

| Parameter         | Type   | Description                                                                                                          |
| ----------------- | ------ | -------------------------------------------------------------------------------------------------------------------- |
| option (Optional) | String | The type of color value you would like returned. Default = "hex". Valid options: "hex", "rgb", "rgba", "hsl", "hsla" |

#### Example

```javascript
random.color();
// #3bf93d

random.color("rgb");
// rgb(61, 134, 160)

random.color("rgba");
// rgb(227, 30, 44,, 0.7)

random.color("hsl");
// hsl(326, 87%, 43%)

random.color("hsla");
// hsla(328, 72%, 44%, 0.8)
```

## From

### `.from(arr, [count = 1])`

Returns a random element from an array.

#### Parameters

| Parameter        | Type   | Description                                                          |
| ---------------- | ------ | -------------------------------------------------------------------- |
| arr              | Array  | The array of elements to select from                                 |
| count (Optional) | Number | The amount of elements to include in the returned array. Default = 1 |

#### Example

```javascript
random.from(["Paul", "Chani", "Gurney"]);
// Chani

random.from(["Paul", "Chani", "Gurney"], 5);
// ["Gurney", "Paul", "Gurney", "Chani", "Chani"]
```

## Percent

### `.percent([count = 1])`

Returns a random number between 1-100, or an array of random numbers between 1-100.

#### Parameters

| Parameter        | Type   | Description                                                          |
| ---------------- | ------ | -------------------------------------------------------------------- |
| count (Optional) | Number | The amount of elements to include in the returned array. Default = 1 |

#### Example

```javascript
random.percent();
// 27

random.percent(5);
// [37, 88, 24, 90, 11]
```

## Shuffle

### `.shuffle(arr)`

Return a shuffled version of a given array using the Fisher-Yates Algorithm

#### Parameters

| Parameter | Type  | Description                      |
| --------- | ----- | -------------------------------- |
| arr       | Array | The array of elements to shuffle |

#### Example

```javascript
random.shuffle([1, 2, 3, 4, 5]);
// [3, 5, 2, 1, 4]
```

## String

### `.string([option = "alphanumeric"], [length = between(3, 24)])`

Returns a random string.

#### Parameters

| Parameter         | Type   | Description                                                                                                              |
| ----------------- | ------ | ------------------------------------------------------------------------------------------------------------------------ |
| option (Optional) | String | The type of string you would like to return. Default = "alphanumeric". Valid options: "alphanumeric", "alpha", "numeric" |
| length (Optional) | Number | The length you would like the string to be. Default = between(3, 24)                                                     |

#### Example

```javascript
random.string();
// hX4XHE2M6eyE9XM1fj3

random.string(5);
// Us8dP

random.string("alpha");
// DCjWSnSOuSjK

random.string("numeric");
// 9386263812837196384

random.string("alpha", 8);
// ajmRmsEC
```

## To

### `.to(num)`

Returns a random number between 1 (or -1) and the number you specify, or an array of random numbers between 1 (or -1) and the number you specify.

#### Parameters

| Parameter        | Type   | Description                                                         |
| ---------------- | ------ | ------------------------------------------------------------------- |
| num              | Number | The maximum number to select from                                   |
| count (Optional) | Number | The amount of numbers to include in the returned array. Default = 1 |

#### Example

```javascript
random.to(10);
// 7

random.to(-99, 3);
// [-64, -1, -27]
```

---

## Contributing

Pull requests are welcome if they are related to practical random generation.

For major changes, please open an issue first to discuss what you would like to change.

---

## License

This project is licensed under the [MIT License](LICENSE).
