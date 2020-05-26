# AVA

```text
npm install --save-dev ava
mkdir test
```

```javascript
import test from 'ava';

test('should foo', (t) => {
    t.pass();
})
```

* `t.pass`
* `t.fail`
* `t.assert` \| `t.truthy`
* `t.falsy`
* `t.true`
* `t.false`
* `t.is`
* `t.not`
* `t.deepEqual`
* `t.notDeepEqual`
* `t.throws`
* `t.notThrows`
* `t.throwsAsync`
* `t.notThrowsAsync`
* `t.regex`
* `t.notRegex`
* `test`
* `test.skip`
* `test.failing`
* `test.todo`

