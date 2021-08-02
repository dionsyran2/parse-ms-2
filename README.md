# parse-ms-2

> This can parse milliseconds into an object

## Install

```
$ npm install parse-ms-2
```

## Usage

```js
require('parse-ms-2')

parseMilliseconds(1337000001)


/*
Return:

{
	days: 15,
	hours: 11,
	minutes: 23,
	seconds: 20,
	milliseconds: 1,
	microseconds: 0,
	nanoseconds: 0
}
*/
```

This is created by one single file, index.js, its code? here:
```js
function run(milliseconds) {
	if (typeof milliseconds !== 'number') {
		throw new TypeError('Expected a number');
	}

	return {
		days: Math.trunc(milliseconds / 86400000),
		hours: Math.trunc(milliseconds / 3600000) % 24,
		minutes: Math.trunc(milliseconds / 60000) % 60,
		seconds: Math.trunc(milliseconds / 1000) % 60,
		milliseconds: Math.trunc(milliseconds) % 1000,
		microseconds: Math.trunc(milliseconds * 1000) % 1000,
		nanoseconds: Math.trunc(milliseconds * 1e6) % 1000
	};
}

module.exports = run
```
