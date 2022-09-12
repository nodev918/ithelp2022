### 基本語法
```
run:
    python3 main.py

clean:
    python3 clean_tool.py
```
make run  會執行 python3 main.py
make clean 會執行 python3 clean.py


### 傳入環境變數
```
run:
	echo $(var)
```
輸入 make run var=hi
預期會在畫面上看到hi, 表示成功把環境變數透過指令傳入給 Makefile了

<br/><br/>
以下工作上不一定用到但Makefile語法相關, 有時間再來補充解釋跟說明進來
### C 語言編譯binary
gcc -o hello hello.c
sleep 3
./hello

### C++ 編譯 Kernel OS 
以下為了湊字數, 是C++編譯可執行檔的makefile, 參考價值還不錯但是目前有點離題, 先把程式碼放上來, 等有機會再補充解釋

GPPPARAMS = -m32 -fno-use-cxa-atexit -nostdlib -fno-builtin -fno-rtti -fno-exceptions -fno-leading-underscore
ASPARAMS = --32
LDPARAMS = -melf_i386

objects = loader.o kernel.o 

%.o: %.cpp
	g++ $(GPPPARAMS) -o $@ -c $<

%.o: %.s
	as $(ASPARAMS) -o $@ $<

mykernel.bin: linker.ld $(objects)
	ld $(LDPARAMS) -T $< -o $@ $(objects)

install: mykernel.bin
	sudo cp $< /boot/mykernel.bin
