##ES6  
ECMAScript6  ---> ECMA6 ES6
javascript  
ECMAScript 3.1  
    核心解释器  翻译了js的词法和语法  
DOM  
BOM  
ECMA  解决编程语言的规范  
    ECMA- 262  --->> ECMAScript  
ECMAScript
       > 1996 ES1.0 Netscape将js提交给ECMA组织， ES正式出现  
       > 1998年6月，ECMAScript 2.0版发布。  
       > 1999年12月，ECMAScript 3.0版发布，成为JavaScript的通行标准，得到了广泛支持。  
       > 2007年10月，ECMAScript 4.0版草案发布，对3.0版做了大幅升级，预计次年8月发布正式版本。草案发布后，由于4.0版的目标过于激进，各方对于是否通过这个标准，发生了严重分歧  
       > 2008年7月，ECMA开会决定，中止ECMAScript 4.0的开发，将其中涉及现有功能改善的一小部分，发布为ECMAScript 3.1，而将其他激进的设想扩大范围，放入以后的版本，由于会议的气氛，该版本的项目代号起名为Harmony（和谐）。会后不久，ECMAScript 3.1就改名为ECMAScript 5。  
       > 2009年12月，ECMAScript 5.0版正式发布。Harmony项目则一分为二，一些较为可行的设想定名为JavaScript.next继续开发，后来演变成ECMAScript 6；一些不是很成熟的设想，则被视为JavaScript.next.next，在更远的将来再考虑推出。  
       > 2011年6月，ECMAscript 5.1版发布，并且成为ISO国际标准（ISO/IEC 16262:2011）。  
       > 2013年3月，ECMAScript 6草案冻结，不再添加新功能。新的功能设想将被放到ECMAScript 7。  
       > 2013年12月，ECMAScript 6草案发布。然后是12个月的讨论期，听取各方反馈。  
       > 2015年6月17日，ECMAScript 6发布正式版本，即ECMAScript 2015。  
***
ES5和ES6只是为了兼容高级浏览器，有一些ES6的东西高级浏览器也不兼容
##1、在线兼容编辑器  
      http://babeljs.io/repl/
      https://google.github.io/traceur-compile/demo/repl.html#  
##2、引入一些文件来兼容  
     traceur.js     编译：把ES6的代码编译成ES5,ES3.1点代码  
     bootstrap.js   引入文件  
     注：现在写ES6 先不引入文件，如果编译不成功，再引入文件  
     ***  
##1、声明变量  
   原：var  
   ES6:let  
        1、块（代码块）作用域  {}  
        2、同样的变量，不允许重复声明  
        {...}块级作用域  是一种自执行匿名函数（类似封闭空间）
        `(function(){
            ....
            //解决变量名冲突  
            //i的问题  
        })();`  
        const  
        常量（字面量） 一经声明就不会再修改  
        原：声明常量 大写 如：HERF  
        ES6:const  
          特点：1、 一经声明就不会再修改  
               2、 在声明的时候必须赋值（为了防意外修改）  
               3、 同样的变量，不允许重复声明  
               ***
##2、字符串  
  原： var str = 'abcdef';  
      var str = "abcedeff"
      拼接 ‘+str+'  
      ###字符串：
          indexOf('小字符串') 返回的是字符串对应的下标
          lastIndexOf()  
          charAt('下标') 返回的是小字符串  
          substring(开始位置，[结束位置])  
          split('切割方式')  
          toUpperCase()  
          toLowerCase()  
          splice()  
          replace('把谁', '替换成谁')  
          replace(正则,'替换成谁')  
          replace(正则, function(str) {  
          //str 符合正则条件的小字符串  
          })  
          match(正则) 从字符串中挑选出符合条件的小字符串  
   ES6: var str = `abcedf`;
        好处： 字符拼接  
          var str = `abcdef`;
          alert(`h1${str}gk`);//模版  
          ${str}  
          ###新的字符串方法
          includes('小字符串') 用法类似于indexOf () 返回值直接是 true 或者 false
          startsWith('小字符串')  返回的是true或者false
          endsWtih('小字符串')
          repeat(数字)重复字符串  
          数字  整数  1，2  
               小数 向下取整  
               0    晴空字符串  
               负数  报错  
          ES7  
          str.padStart(位置，‘小字符串')  向位置插入后面的字符串  
          padEnd    
          ***  
##3、结构赋值：左边的结构和右边的结构一样  
      var [a,b,c,d] = [1,2,3,4];  
      var {a,b,c,d} = {a: 1,b:2,c:3,d:4};  
      
      var [{a,b},c] = [{a:1,b:2},3]  
      var [{a,b},[{c,d},e],f] = [{a:1,b:2},[{c:3,d:4},5],6]  
      作用：数据解析，解析后台的数据  
      city: {  
         name1:xx  
         name2:xx  
         name3:{  
            one:[{  
                  title:0  
            },{},{}]  
         }  
      }  
      var {a,b,{[]{c}}}  
##4、数组：  
      原数组方法：    
      push()  
      pop()  
      shift()  
      unshift()  
      join()  
      需要注意学习：  
      1、他们的返回值是什么；
      2、他们会不会对原数组有影响；  
      ES6新增的：   
      indexOf('数组中的内容')  和字符串一样    
      lastIndexOf()  和上面一样，从后往前 
      ###复制一个数组（没有发生引用）：
        1、for循环赋值  
        2、Array.from(要复制的数组) 返回值是新数组  
          var arr = [1,2,3]  
          var arr2 = Array.from(arr);  
        3、扩展(...)  
          var arr2 = [...arr1]
          
          注：...把后面的东西扩展成一个数列  
          arguments是类数组（伪数组），只能用下标和length不能用其他方法  
          > function show(...arguments) {//把arguments扩展成数组  
            arguments.push(5);  
            console.log(arguments);  
          }  
          show(1,2,3,4)  
###循环  
for  
while  
for in  

forEach只能循环数组  arr.forEach(function(v,i,a){  
    //参数属于行參，写什么无所谓，主要是顺序   
    //v 第一个参数: value
    //i 第二个参数：index  
    //a 第三个参数：arry本身  
});  

for of 数组可以用，json不能用   本质也不是循环数组是循环map对象的  
  
  for(var value of arr) {   
      alert(value);  
  }   
##5、map是个对象和json差不多，也是键值对的形式  

  声明的方式： var map = new Map()  
  设置值： map.set(name,value)  
  查找值： map.get(name)
  删除值： map.delete(name)  
  
  map的循环for in 没用 配合for of 来使用  
  
  for(var name of map) {  
      alert(name); //a,1 b,2 c,3 返回的是每一个键值对  
  }  
  
  for ( var [key,value] of map) {  
      alert(value);
      alert(key)
  }  
  
  for(var key of map.entries()) {  //循环entries和循环map本身一样  
      alert(key);
  }  
  
  for( var value of map.values()) {  
      alert(value);  
  }  
  
  
  for (var key of map.keys()) {  
      alert(key);  
  }  
  ***
  ##6、函数  
   原：  
   命名函数： function show() {  //函数的定义  
      //代码  
     }  
   show()  
   
   匿名函数： function() {  
                代码
             }  
             
   事件函数： oDiv.onclick = function () { }  
   定时器：   setInterval(function() {},1000)  
              时间到了触发  
              var show = function() {}  
              show();  
 ES6：箭头函数  
    var show=()=>{  //把　function去掉，在()和{}中间加=>  
                  alert(1);  
           }  
           show();
           
           传參：  
           var show = (a,b)=>{  
              alert(a+b);
           }  
           show(1,3);  
           传參的简写
           var show=a=>{  
              alert(a);
          }  
          show(1);  
          返回值  
          var show=()=>{    
              return 1  
          }  
          alert(show());  
          返回值简写  //如果只有返回值可以省略{return}  
          var show=()=>'abc';  
          alert(show());  
          
          箭头函数的问题：  
          1、this 不能用了 this是window  
          2、arguments不能用了  
          对象（单列模式：就是创造单个对象的一种方法）  
          以前是用  键值对的形式创建  
          原：  
              var person = {  
                  name:'abc',  
                  showName:function() { 
                      alert(1);  
                  }  
               }  
               
            ES6：  
            var name = 'abc';
            var age = '100';
            var person = {  
                name,  
                age,  
                showName(){  
                   return this.name
                },  
                showAge() {  
                   return this.age
                }  
            }  
           ###面向对象  
            原：通过构造函数于属性，通过原型链来写方法  
            ES6:  
            class 类  
            constructor  构造函数  
            
            class Person{   //类  
                constructor(name,age) {  //构造函数  
                    this.name = name; //写属性  
                    this.age = age;  
                } 
                showName() {  //写方法  
                  return this.name  
                }  
                showAge() {  
                    return this.age
                }  
            }  
            var p1 = new Person('小明', '100');  
            alert(p1.showName());  
        ###继承  
            原：
            class Worker extends Person{  
                constructor(name,age,job = '工人') {  //构造函数
                  super();  
                  this.name = name;  需要继承的属性挂上去  
                  this.age = age;  
                }  
            }  
            
            var w1 = new Worker('小花','100');  
            alert(w1.name);  
            函数的默认值  
            function move(obj = '这个参数是必传的', json = {},option) {
                alert(obj);  
            }  
            move()  
         ###模块化    
            requirejs/seajs  
            
            一个模块就是一个js  
            怎么定义一个模块  
            define(function(require,exports,module) {  
                /*  
                * require 引用模块  
                *  exports  导出模块  
                *  module  批量导出   
                * *／
                exports.a = 12;
            });  
            怎么使用一个模块  
            require(['a.js'],function(mod) {  
                  console.log(mod);  //{a:12}  
                  alert(mod.a)  
            })  
            seajs.use(['a.js'],function(mod) {  
                console.log(mod);  //{a:12}  
                alert(mod.a)  
            })  
            ES6点模块化  
            怎么定义一个模块  
            const a = 12;  
            export default a;  //导出模块  
            
            如何批量导出  
            const a = 12;  
            const b = 5;  
            export default {a,b}  
            怎么使用一个模块  
            import modA from '1.js'  //导入模块  
            
            generator  生成器（其实就是一个函数）  
            本质：  一个函数生成一堆函数  
            
            普通函数  
            function show() { }  
            一路执行到底  
            generator  前端用的非常少， 后台用的多 ，node  
            function* show(){}  
            function *show()  
            中间能暂停  
            
            配合yield 就是控制暂停的  
            
            function* show()  {  
                 yield  //暂停  
                 alert(1);  
            }   
            var fn = show();  
            fn.next();  
            fn.next();  
            
            yield:  
              1、能暂停（一定是在generator函数中，在普通函数没用）  
              2、还有类似return的返回功能  
                  {value: 返回的值， done： 是否完成}  
              3、next(111);  可以传參比较麻烦  
                    1、第一次传的东西白费  
                    2、穿的参数yield本身来接收  
                  function *show(){/*  是第一次next 这个时候传等于白传  
                      alert(1);  
                      var a*/=/*yield;  
                      alert(a);*/   第二次  next  
                      
                  }
                  
                  
                 两个yield需要next几步？3
