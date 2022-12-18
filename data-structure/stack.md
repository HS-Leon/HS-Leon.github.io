# Stack 栈

后进先出（last in first out）

生活实际Ex： 一摞书，最后放上去的先拿走； 浏览器访问历史，最后访问的网站先从历史记录中弹出

Attribute/methods： push（入栈）、pop（弹栈）、peek（返回栈顶元素）、length

js 的 Array 天生具备stack的特性

```
function Stack(){
    this.count = 0;
    this.storage = {}

    this.push = function(value){
        this.storage[this.count] = value;
        this.count++;
    }

    this.pop = function(){
        if(this.count === 0){
            return undefined
        }
        this.count--;
        let res = this.storage[this.count]
        delete this.storage[this.count]
        return res;
    }

    this.peek = function(){
        return this.storage[this.count - 1]
    }

    this.size = function(){
        return this.count
    }
    
}
```