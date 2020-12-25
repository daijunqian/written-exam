# 笔试题  

请完成以下笔试题，可以使用自己擅长的语言来编写，通过 github pull request 提交代码。

1. 编写一个递归版本的 reverse(s) 函数(或方法),以将字符串s倒置。
 <script>

function reverse(arr,len,a){
    if(len>=1){ 
       
       let temp = arr.shift();   
       a[len-1] = temp;
       len=len-1;
       reverse(arr,len,a);
    }
    return a;
}
function handleRes(s){
    let arr = s.split('');
    let len = arr.length;
    let a = [];
    let answer = reverse(arr,len,a).join('');
    console.log('1、'+answer);
    return answer;
}
    </script>
2. 编写程序 expr，以计算从命令行输入的逆波兰表达式的值，其中每个运算符或操作数用一个单独的参数表示。例如，命令
expr 2 3 4 + *

3. 用归并排序将3，1，4，1，5，9，2，6 排序。
   <script>
       var mergeSort = function (arr) {
    return mergeSortRec(arr);
}
var mergeSortRec=function (arr) {
    var length=arr.length;
    if(length===1){
        return arr;
    }
    var mid=Math.floor(length/2);
    var left=arr.slice(0,mid);
    var right=arr.slice(mid,length);
    return merge(mergeSortRec(left),mergeSortRec(right));
}
var merge=function (left,right) {
    var result=[];
    var il=0;
    var ir=0;
    while(il<left.length&&ir<right.length){
        if(left[il]<right[ir]){
            result.push(left[il++]);
        }else{
            result.push(right[ir++]);
        }
    }
    while(il<left.length){
        result.push(left[il++]);
    }
    while ((ir<right.length)){
        result.push(right[ir++]);
    }
    return result;
}
var arr = [3,1,4,1,5,9,2,6];
console.log(arr.toString());
console.log(mergeSort(arr).toString());
4. 对下面的 json 字符串 serial 相同的进行去重。

```javascript
  [{
    "name": "张三",
    "serial": "0001"
  }, {
    "name": "李四",
    "serial": "0002"
  }, {
    "name": "王五",
    "serial": "0003"
  }, {
    "name": "王五2",
    "serial": "0003"
  }, {
    "name": "赵四",
    "serial": "0004"
  }, {
    "name": "小明",
    "serial": "005"
  }, {
    "name": "小张",
    "serial": "006"
  }, {
    "name": "小李",
    "serial": "006"
  }, {
    "name": "小李2",
    "serial": "006"
  }, {
    "name": "赵四2",
    "serial": "0004"
  }];
```
 function sortNumber(a,b)
				{
				return a.distance - b.distance
				}
			data.sort(sortNumber);
			for(var i=0; i < data.length; i++) {
			    for(var j=i+1; j < data.length; j++) {
			        if(data[i].id == data[j].id) {
			            data.splice(j,1);
			        }
			    }
			}
			console.log(data);
5. 把下面给出的扁平化json数据用递归的方式改写成组织树的形式

```javascript
  [
    {
      "id": "1",
      "name": "中国",
      "code": "110",
      "parent": ""
    },
    {
      "id": "2",
      "name": "北京市",
      "code": "110000",
      "parent": "110"
    },
    {
      "id": "3",
      "name": "河北省",
      "code": "130000",
      "parent": "110"
    },
    {
      "id": "4",
      "name": "四川省",
      "code": "510000",
      "parent": "110"
    },
    {
      "id": "5",
      "name": "石家庄市",
      "code": "130001",
      "parent": "130000"
    },
    {
      "id": "6",
      "name": "唐山市",
      "code": "130002",
      "parent": "130000"
    },
    {
      "id": "7",
      "name": "邢台市",
      "code": "130003",
      "parent": "130000"
    },
    {
      "id": "8",
      "name": "成都市",
      "code": "510001",
      "parent": "510000"
    },
    {
      "id": "9",
      "name": "简阳市",
      "code": "510002",
      "parent": "510000"
    },
    {
      "id": "10",
      "name": "武侯区",
      "code": "51000101",
      "parent": "510001"
    },
    {
      "id": "11",
      "name": "金牛区",
      "code": "51000102",
      "parent": "510001"
    }
  ];
```
function Tree(s){
    let ind = 0 ; 
    if(s.length>1){
        for(let i=0;i<s.length;i++){
            let a = 0;  
            for(let j=i+1;j<s.length;j++){
                if(s[j].parent == s[i].code){
                    a++;  
                    ind++;
                }
            }
            if(a == 0&&s[i].parent!=''){ 
                for(let n in s){
                    s[n].children = s[n].children?s[n].children:[];
                    if(s[n].code == s[i].parent){
                        s[n].children.push(s[i]);
                    }
                }
                s.splice(i,1);
                i--; 
            }
        }
        if(ind != 0){ 
            Tree(s);
        }
    }
    return s;
}
function handleTree(s){ 
    s = Tree(s);
    console.log(s);
    return s;
}
console.log(s2)
