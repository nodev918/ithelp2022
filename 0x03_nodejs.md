nodejs
非阻塞式執行環境(相對於大部分程式語言是阻塞式, 也就是比較好寫)
javascript 的 後端實作 (就是裝在作業系統上面的, 跟裝在瀏覽器裡面的區別)
QA在寫一些 script 的時候會用到, 例如 K6壓力測試, Cypress Web UI 測試
getting started
完成安裝nodejs https://nodejs.org/zh-tw/download/
node --version ( 預期顯示版本號)
node 是 nodejs 的執行檔, 由於在安裝時候, 安裝包幫你設定好了環境變數, 所以可以直接抓到node這個執行檔, 輸入node會直接進入互動式介面(因為nodejs是直譯語言, 編譯語言沒有這個互動模式可以用)
npm --version ( 預期顯示版本號 )
npm是nodejs的套件管理工具, 一般使用先npm init 一個設定檔package.json出來, 然後下 npm install express (以 express 為例), 這樣就安裝了express套件在 mode_modules裡面了
hello world
node
console.log("hello world")
這樣就在互動介面裡面 hello world了
退出 Ctrl+C 兩次, 或是看畫面上的指引

開啟 vscode
新增一個 app.js (可以 cat app.js)
在裡面新增 console.log("hello world")
然後 Ctrl + ~ 把 inline terminal 叫出來
輸入node app.js

express http server hello world
npm install express
npm install nodemon
然後修改package.json, 在 script 那邊新增一行

效果如下

  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "start":"nodemon app"
  },
上面這行start是因為我們將 nodemon 裝在當前資料夾內, 所以用npm的script去抓nodemon的執行檔

新增 app.js

const express = require('express')
const app = express()
const port = 3000

app.get('/', (req, res) => {
  res.send('Hello World!')
})

app.listen(port, () => {
  console.log(`Example app listening on port ${port}`)
})
Ctrl + ~ 打開 terminal
輸入 npm start ( 預期會看到 Example app listening on port 3000 以及 nodemon 的字樣)
接下來在你修改檔案且存檔的時候, nodemon會自動熱更新 server app, nodemon這種功能通常是用 socket 或 websocket 實作而成, 叫file watcher

接下來打開瀏覽器, 輸入 localhost:3000, 應該會預期看到 hello world
打開 terminal (cmd視窗), 使用

curl http://localhost:3000 
也應該要可以看到 hello world // 這邊如果沒有 curl工具, 建議可以安裝一下
安裝 postman 在裡面呼叫 http://localhost:3000, 也應該要可以看到 hello world
以上為了簡化, 可以先瀏覽器看到為主就ok, 等更熟練再使用 curl 跟 postman 這兩個工具

Next?
到目前我們已經會了一點點 nodejs, 但 javascript 本身是個大坑, 所以之後的js學習建議都以解決工作上需求為主, 之後章節有機會還會再講javascript

