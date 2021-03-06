# What's New in version 1.0.4
We found that the package provide a weak performance where many words may have the same hash. To improve the performance we replaced the fixed prefix 'x' into a maped version of the first letter. Tests show a remarkable improvement in the performance and the results as well. Moreover, we treated both ة and ه at the end of the word as a ه in both cases.

# arSoundex

There are many libraries that generate soundex index for English but non for Arabic. <br />
In this contribution we provide the first open source soundex index for Arabic. <br />
Our Arabic soundex library could help in improving the search in arabic documents, finding and correcting spelling errors and many other applications.

[Soundex Algorithem](https://en.wikipedia.org/wiki/Soundex)

We developed an algorithm based on Tajweed rules that categorize the characters into groups based on it's pronunciation. <br />
The second algorithm inspired from [this source](https://www.codeproject.com/Articles/26880/Arabic-Soundex)

## Install
```javascript
npm i ar-soundex
```
## Build
Make sure that you have installed devDependencies or run:
```javascript
npm i
```
If you have trouble installing rollup you may check it's documentation [rollup installed](https://rollupjs.org/guide/en/)<br />
To build the package on your machine run the following command
```javascript
npm run build
```
## API
```javascript
var arSoundex = require('ar-soundex');
arSoundex('عبدالله') // => x74600
```
## Parameters
| parameter        | Type | Description           | Defult  |
| ------------- |:-------------:|:-------------:| -----:|
| word      | String| A string of one word or more | '' |
| length      | Number | The max length of generated index |   6 |
| method | Number | To set which algorithm to be used [1 or 2] |    1 |

## Example
```javascript
// Detecting misspelling
arSoundex('عبدالله') // => x74600
arSoundex('عبدلله') // => x74600

// Detecting extra characters
```
<p>arSoundex('<span dir="rtl">ضربوه</span>', 6, 1) // => x26700</p>
<p>arSoundex('<span dir="rtl">ضرب</span>', 6, 1) // => x26700</p>


## License
[MIT ©](https://github.com/SupervisionT/arSoundex/blob/master/LICENSE)

## Contributions & Issues
All contributions are welcome. Create a pull request [here](https://github.com/SupervisionT/arSoundex/pulls) <br />
If you have an issue please let us know . Create an issue [here](https://github.com/SupervisionT/arSoundex/issues) <br />

## Keywords
Arabic Natural Language Soundex Metaphone Index Search Spelling