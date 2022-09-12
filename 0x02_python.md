Py分為 python2 及 python3, 開發中大部分情況會使用 python3

**查看版本號**
```
python3 --version
```
**如果沒有python3就安裝**
```
sudo apt update
sudo apt install python3 
```
這邊先不指定版本, 讓流程更簡單好上手一點
**接下來開始 Python 互動式界面**, 打開小黑視窗 terminal/cmd
```
python3
```
**由於python是直譯語言, 可以輸入一行執行一行**
在這邊可以輸入
```
print("hello world")
```
這樣就已經執行了第一個python程式

接下來請打開程式碼的 IDE/Editor, 在這邊推薦使用 vscode 或 vim (vim是開開玩笑 >:3)
vscode有個很好用的 shell script功能
在 vscode 界面下 Ctrl + Shift + p 打開 Pallete Panel 後 輸入 Shell Script 並安裝
這個功能是讓你能在 terminal 界面的時候 輸入 code . 就能打開當前資料夾

**開始正式 hello world**
```
mkdir test
cd test
touch main.py
code .
```
以上三行指令, 創建資料夾 test, 移動到資料夾內, 建立一個main.py檔案, 然後開啟 vscode

**這時候我們在 main.py 裡面輸入**
```
print("hello world")
```
然後 Ctrl + ~ 開啟 built in terminal 
輸入 python3 main.py
這時候螢幕上應該會顯示 hello world

這時候已經完成了使用檔案進行 hello world了 !


**Python 套件管理大師 pip**
```
sudo apt install python3-pip
```
這樣應該就會順利安裝
```
pip3 --version
或是
python3 -m pip --version
```
以上兩個指令代表同一件事, 方便後面用 pip3

查看目前電腦裡面安裝的python3套件( site-package )
```
pip3 list
```
**安裝套件流程( 以requests為例 )：**
1. 先google requests pypl 搜尋官方套件名稱
2. pip3 install requests ( 網頁上是 pip install requests, 這樣應該會裝到 python2 去, 不建議 )
3. pip3 list 裡面應該會出現
4. 可以在我們的 main.py 裡面 import requests 來做使用

可以試著 json 以及 pyyml套件練習看看唷 ^.<

**python3 的套件管理 requirements.txt**
1. touch requirements.txt # 建立一個 requirements.txt 檔案
2. pip3 freeze >> requirements.txt # 把全部套件寫進去
3. 在requirements.txt  # 裡面找到不是專案會import的套件, 都砍掉, 這樣才乾淨不會佔空間
4. 在新環境要使用requirements.txt做安裝的時候
5. pip3 install -r requirements.txt

**基本python語法**
1. print
2. def
3. if
4. for

**python 資料型別**
1. number ( 數字 )
2. string ( 字串 )
3. bool ( True / False )
4. list ( array )
5. dict ( object )

**QA常用 python 函式庫**
1. requests
2. json
3. pyyaml

**會用到的類設計模式 (這邊先看個關鍵字就好)**
1. Setup / Teardown
2. Fixture
3. OOP
4. FP
5. Composite

**References:**
1. py官方：https://www.python.org/
2. py安裝pip：https://linuxize.com/post/how-to-install-pip-on-ubuntu-18.04/
3. requirements.txt：https://blog.longwin.com.tw/2019/03/python-pip-requirements-txt-management-package-2019/