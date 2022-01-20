### 代码code_review
主要是提高代码的可读性，可优化性，减少多余的代码

#### 1. 多个条件的代码优化
- 基础 使用 if else
```js
function curVal(i){
    if(i === 'name'){
      return 'xiner'
    }else if(i === 'age'){
      return 26
    }else if(i === 'sex'){
      return  '男'

    }else{
      return '默认值'
    }
  }
```
- 基础 使用 switch case
```js
function curSwitch(i){
    switch(i){
      case 'name':
        return 'xiner'
        break
      case 'age':
        return 26
        break
      case 'sex':
        return  '男'
        break
      default:
        return '默认值'
    }
  }
```
- 进阶 使用 map
```js
  function curVal(i){
    let mapArr = new Map([
      // key 和 val
      ['name','xiner'],
      ['age',26],
      ['sex','男']
    ])
    // 后面默认值
    return mapArr.get(i) || '默认值'
  } 
```
#### 2.多个||条件的情况

```js
function judge(fruit) {
  if (fruit === 'apple' || fruit === 'strawberry' || fruit === 'cherry' || fruit === 'cranberries' ) {
    console.log('red')
  }
}
```
将其进行优化
```js
function judge(fruit){
  const fruit = ['apple','strawberry','cherry','cranberries']
  if(fruit.includes(fruit)){
    console.log('red')
  }
}
```