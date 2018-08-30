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
