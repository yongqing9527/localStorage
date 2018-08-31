# localStorage
下面的代码片段访问当前域名下的本地 Storage 对象，并增加了一个数据项通过使用Storage.setItem()。

    localStorage.setItem(`myCat`, `Tom`);
该语法用于读取 localStorage 项，如下:

    let cat = localStorage.getItem(`myCat`);
该语法用于移除 localStorage 项，如下:

    localStorage.removeItem(`myCat`);
该语法用于移除所有的 localStorage 项，如下:

    // 移除所有
    localStorage.clear();

# Cookie
cookies保存哪些方面的信息？

        Cookie的名字
        Cookie的值
        到期时间
        所属域名（默认是当前域名）
        生效的路径（默认是当前网址）
使用 JavaScript 创建Cookie
  
        document.cookie = "username=John Doe";
        document.cookie="username=John Doe; expires=Thu, 18 Dec 2013 12:00:00 GMT";
        document.cookie="username=John Doe; expires=Thu, 18 Dec 2013 12:00:00 GMT; path=/";
使用 JavaScript 读取 Cookie

        var x = document.cookie;
使用 JavaScript 修改 Cookie

        document.cookie="username=John Smith; expires=Thu, 18 Dec 2013 12:00:00 GMT; path=/";
使用 JavaScript 删除 Cookie

        document.cookie = "username=; expires=Thu, 01 Jan 1970 00:00:00 GMT";
设置 cookie 值的函数

    function setCookie(cname,cvalue,exdays){
        var d = new Date();
        d.setTime(d.getTime()+(exdays*24*60*60*1000));
        var expires = "expires="+d.toGMTString();
        document.cookie = cname+"="+cvalue+"; "+expires;
    }
    //获取 cookie 值的函数
    function getCookie(cname){
        var name = cname + "=";
        var ca = document.cookie.split(';');
        for(var i=0; i<ca.length; i++) {
            var c = ca[i].trim();
            if (c.indexOf(name)==0) { return c.substring(name.length,c.length); }
        }
        return "";
    }
    //检测 cookie 值的函数
    function checkCookie(){
      var username=getCookie("username");
      if (username!=""){
        alert("Welcome again " + username);
      }else {
        username = prompt("Please enter your name:","");
        if (username!="" && username!=null){
          setCookie("username",username,365);
        }
      }
    }
    
#  sessionStorage
sessionStorage 用于临时保存同一窗口(或标签页)的数据，在关闭窗口或标签页之后将会删除这些数据。
* 提示: 如果你想在浏览器窗口关闭后还保留数据，可以使用 localStorage 属性， 改数据对象没有过期时间，今天、下周、明年都能用，除非你手动去删除。
保存数据语法：

        sessionStorage.setItem("key", "value");
读取数据语法：

        var lastname = sessionStorage.getItem("key");
删除指定键的数据语法：

        sessionStorage.removeItem("key");
删除所有数据：
        
        sessionStorage.clear();

