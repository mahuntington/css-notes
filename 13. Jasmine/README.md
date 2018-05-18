# Test Drive Development

```
npm install jasmine -g
```

multBy2.js:
```javascript
module.exports = (value) => {
    return value * 2;
}
```

test.js:
```javascript
const multBy2 = require('./module.js');

describe("multBy2 test suite", function(){
    it("should multiply a value by 2", function(){
        expect(multBy2(2)).toBe(4)
    })
    it("should return 0 when passed 0", function(){
        expect(multBy2(0)).toBe(1)
    })
})
```

```
jasmine test.js 
```
