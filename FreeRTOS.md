# FreeRTOS

## 參考
How to Set Up Visual Studio Code to Program the Pi Pico (Windows) (基礎)
https://www.youtube.com/watch?v=mUF9xjDtFfY

FreeRTOS Kernel SMP for the Raspberry PI Pico (講的比較深)
https://www.youtube.com/watch?v=nD8XeWjn-2w


## Raspberry PI Pico

## Install Tools


### GCC (編譯器 GNU Compiler Collection，縮寫為GCC)
Arm GNU Toolchain 工具鏈
GNU是一個自由的作業系統
https://developer.arm.com/downloads/-/gnu-rm

https://developer.arm.com/-/media/Files/downloads/gnu-rm/10.3-2021.10/gcc-arm-none-eabi-10.3-2021.10-win32.exe?rev=29bb46cfa0434fbda93abb33c1d480e6&hash=3C58D05EA5D32EF127B9E4D13B3244D26188713C

gcc-arm-none-eabi-10.3-2021.10-win32.exe
Windows 32-bit Installer (Signed for Windows 10 and later) (Formerly SHA2 signed binary)
MD5: 8d0f75f33f9e3d5f9600197626297212

### CMake (管理軟體建置的程式 編譯程式)
組態檔是用一種建構軟體專用的特殊程式語言寫的CMake指令碼。
https://cmake.org/download/
https://github.com/Kitware/CMake/releases/download/v3.25.0/cmake-3.25.0-windows-x86_64.msi



### VS code Build Tools (xx) (要用 vscode 環境才要裝)
https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019
https://aka.ms/vs/17/release/vs_BuildTools.exe

### Python (自動產生 make file 用到的)
https://www.python.org/downloads/windows/
https://www.python.org/ftp/python/3.11.0/python-3.11.0-amd64.exe


### GIT (用來抓程式)
https://git-scm.com/download/win
https://github.com/git-for-windows/git/releases/download/v2.38.1.windows.1/Git-2.38.1-64-bit.exe




### pico SDK


## 步驟
```
1. cmd
2. cd\
3. md Pico
4. cd Pico
5. git clone -b master https://github.com/raspberrypi/pico-sdk.git
6. cd pico-sdk
7. git submodule update --init
8. cd..
9. git clone -b master https://github.com/raspberrypi/pico-examples.git
10. setx PICO_SDK_PATH "c:\Pico\pico-sdk"
11. cd pico-examples
12. md build
13. cd build
14. cmake -G "NMake Makefiles" ..
15. cd..
16. nmake (要花不少時間)
```

找不到路徑 是因為要重開機


在目錄裡會找到 .bin .uf2 C:\Pico\pico-examples\blink


改了 blink.c 只要 nmake 就可

---


Toolchain :
ARM GCC compiler
Cmake
Build Tools for VS 2019
Python 3
Git
VS code

setx PICO_SDK_PATH "..\pico-sdk"

cd pico-examples

md build

cd build

cmake -G "NMake Makefiles" ..

找不到路徑 是因為要重開機

cd..

cd blink

nmake

在目錄裡會找到 .bin .uf2 C:\Pico\pico-examples\blink


改了 blink.c 只要 nmake 就可



---
### 上面可以編譯出 *.uf2 在執行以下步驟
```
Run "Developer Command Prompt for VS 2022"

C:\Program Files\Microsoft Visual Studio\2022\Community>cd\
C:\Pico>git clone --recurse-submodules https://github.com/LearnEmbeddedSystems/rp2040-freertos-project
C:\Pico>cd rp2040-freertos-project
C:\Pico\rp2040-freertos-project>git clone https://github.com/FreeRTOS/FreeRTOS-Kernel
C:\Pico\rp2040-freertos-project>md build
C:\Pico\rp2040-freertos-project>cd build
C:\Pico\rp2040-freertos-project\build>cmake -G "NMake Makefiles" ..
C:\Pico\rp2040-freertos-project\build>nmake
C:\Pico\rp2040-freertos-project\build>
```

產出 .uf2
C:\Pico\rp2040-freertos-project\build\ProjectFiles



Task1 100
Task2 50 60

LA 量到 8ch (簡單型)
1.0639s hi 8ch
1.0639s low 8ch
2.179s 8ch

638ms low 8ch
531ms hi 8ch
1.17s 8ch

5個 100
12.343s - 1.679s = 10.664s 8ch
10個 50,60
12.782s - 1.059s  11.723s 8ch


LA 量到 16ch (原版)
5個 100
1.289 - 11.935 = 10.646 16ch
1.06399 hi 16ch
1.0639 low 16ch
2.1279 16ch

10個 50,60
12.365s - 644.54ms = 11.721 16ch
531.985ms hi 16ch
638.405ms low 16ch
1.1703s 16ch


5個 100
12.001s - 1.360 = 10.641
1.0639s hi
1.0639s low
2.127s

5個 150,160
1.264s - 17.761s = 16.497 (理論上 15.50)
1.595s hi
1.702s low
3.298s



5個 100
11.358s - 0.707 = 10.651
1.0639s hi
1.0639s low
2.127s

5個 100,100
同上



## LA 盜版跟原版 量出來差不多

# 多工 實測得到 時間越短 誤差越大 沒效果?

---

```
cmake -G "NMake Makefiles" ..
會找你的環境路徑 產生 Makefile



C:\Pico\rp2040-freertos-project

CMakeLists.txt
pico_sdk_import.cmake


C:\Pico\rp2040-freertos-project\build (本來是空的)

cmake_install.cmake
CMakeCache.txt
Makefile

```
