# nodejs-uWebSockets-example

## 0. source
* environment
  * CentOS 7
* uWebSockets
  * nodejs npm(Javascript): https://www.npmjs.com/package/uws
  
## 2. build & install
* Node.js
  * $ mkdir -p nodejs-uWebSockets-example
  * $ cd nodejs-uWebSockets-example
  * $ npm init
  * $ npm install uws --save
  * $ node server-uws.js
  * 打開client-uws.html, 用browser與server互動
  
## problems(solved)
* Node.js 執行錯誤
  * 官網是說有兩個可能
    * There was no C++11 compiler available at installation.
    * Your system is not an official Tier 1 Node.js platform.
  * 可我g++已經是gcc version 4.8.5, 有支援c++11, 所以應該是Node.js太舊
    * CentOS 用 yum install下來的node.js太舊(v6.14.3), 要升級, 否則uws執行時會有error
    * [Node.js更新方法](http://eddychang.me/blog/javascript/58-nodes-update.html)
    * Node.js管理版本的工具叫做'n'...設計這些工具的人應該也要考慮user在google時的體驗...n這種關鍵字不是很難google嗎...
    * $ sudo n stable
    * 裝完shell要重開...
    
```
[Error] Error: Compilation of µWebSockets has failed and there is no pre-compiled binary available for your system. Please install a supported C++11 compiler and reinstall the module 'uws'.
```
