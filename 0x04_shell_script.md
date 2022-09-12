指令基本內建, 函式庫要看機器
如果沒有的話, 安裝指令為
```
sudo apt update
sudo apt instal app_name
```

### 一些基本指令
ls：當前目錄內有哪些檔案
cat：檔案內有什麼內容
cd：移動(change directory)
mkdir：建資料夾
cp：複製
mv：改名或移動
rm：刪除 (使用這個指令請小心, 別把系統砍了)
sudo：給權限
uname -a：看一下自己系統是什麼
which：看一下某個指令的 binary 在哪個資料夾, 例如 which python3 他會說明這個binary在哪裡
grep：字串比對(篩選?)
指令教學可以參考：https://reurl.cc/ERVZn0


### 一些寫法
* echo $(curl https://google.com) >> google_res.txt
這樣就是把google網頁的回應, 寫到google_res.txt裡面, $() 代表這邊是一個變數
* ls | grep go
這樣就是在查看當前有什麼包含go名字的檔案



### 好用的函式庫
* echo ( 印在畫面上, 也可以 echo "abc" >> test.txt 這樣對檔案做新增 )
* curl ( http 呼叫, 五顆星常用 ) 
* wget (但我通常都 curl -OL 就可以省下這個, 不過很常用到還是列一下)
* tar ( tar -cvf xxx.tar tar 壓縮 / tar -xvf xxx.tar 解壓縮 )
* jq ( 這個是用來解析json資料的, 自己工作上有一隻程式用到, 覺得很棒 )
  refs: https://stedolan.github.io/jq/ 
* telnet ( 這個是如果有寫 socket programming 會用到, 不是安全通訊比較少用 )
* ssh-gen ( 要做ssh key pair 的時候會用到, 自己目前還比較少用 )

### .sh
shell script 可以整合到檔案裡面做執行, 早期有些軟體都會用.sh檔做自動化安裝
```
touch test.sh
sudo chmod +x test.sh
echo "echo 'hello world' " >> test.sh
./test.sh
```
預期會看到 hello world 出現在螢幕上
我在工作上也有寫了一隻.sh, 用來把 grpcurl 的呼叫做成半自動化工具, 等修改成比較適合的程式碼再補充上來




