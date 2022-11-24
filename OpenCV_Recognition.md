
# OpenCV Recognition
https://github.com/nazmiasri95/Face-Recognition
1. 建兩個目錄 dataset trainer
2. face_datasets.py # 掃臉 掃一百張照片
3. training.py # 從一百張照片 建模
4. face_recognition.py # 辨識

Course! https://www.simplilearn.com/big-data-... ⭐

List of Modules and Documentation

Web:
Requests: https://pypi.org/project/requests/
Django: https://pypi.org/project/Django/
Flask: https://pypi.org/project/Flask/
Twisted: https://twistedmatrix.com/trac/
BeautifulSoup: https://pypi.org/project/beautifulsoup4/
Selenium: https://selenium-python.readthedocs.io/

Data science:
Numpy: https://numpy.org/
Pandas: https://pandas.pydata.org/
Matplotlib: https://matplotlib.org/
Nltk: https://www.nltk.org/
Opencv: https://opencv-python-tutroals.readth...

Machine Learning:
Tensorflow: https://www.tensorflow.org/
Keras: https://keras.io/
PyTorch: https://pytorch.org/
Sci-kit Learn: https://scikit-learn.org/stable/

GUI:
Kivy: https://kivy.org/#home
PyQt5: https://pypi.org/project/PyQt5/
Tkinter: https://wiki.python.org/moin/TkInter

Bonus:
Pygame: https://www.pygame.org/docs/
# cv2 版本問題
img2 = cv2.cvColor(img,cv2.COLOR_BGR2RGB)
img2 = cv2.cvtColor(img,cv2.COLOR_BGR2RGB)

Number Plate Classification using Open-CV
https://nayakpplaban.medium.com/number-plate-classification-using-open-cv-d7bef79e104a

https://www.youtube.com/watch?v=1s1Jq0iVPXk

臉部辨識
https://tw511.com/a/01/28496.html
https://medium.com/ching-i/face-recognition-%E4%BA%BA%E8%87%89%E8%BE%A8%E8%AD%98-python-%E6%95%99%E5%AD%B8-75a5e2ef534f

Face Recognition – OpenCV Python | Dataset Generator
https://thecodacus.com/posts/2021-12-13-face-recognition-opencv-python-dataset-generator/
ModuleNotFoundError: No module named 'retinaface'
pip install retina-face
pip install opencv-contrib-python
https://github.com/Mjrovai/OpenCV-Face-Recognition

AttributeError: module 'cv2' has no attribute 'face'

最終，全部卸載，再安裝一次就可以了，這是什麼毛病。。。。

pip uninstall opencv-contrib-python

pip uninstall opencv-python

pip install opencv-python

pip install opencv-contrib-python




# pip list
```
WARNING: Ignoring invalid distribution -ip (c:\python39\lib\site-packages)
```
到提示的目錄site-packages下刪除 ~ip 開頭的目錄。


# Markdown Viewer 
https://www.youtube.com/watch?v=0WzOzNEu8ws

https://chrome.google.com/webstore/detail/markdown-viewer/ckkdlimhmcjmikdlpkmbgfkaikojcbjk/

# FreeRTOS

https://learnembeddedsystems.co.uk/freertos-on-rp2040-boards-pi-pico-etc-using-vscode
FreeRTOS on RP2040 Boards (Pi Pico etc) using VSCode


```            
└───Parent Folder   
    │   ...
    └───PICO-SDK
    │   ...
    └───Other Projects    
    │
    └───FreeRTOS Project
        │   CMakeLists.txt
        │   pico_sdk_import.cmake
        │   ...
        └───ProjectFiles  
        │   CMakeLists.txt
        │   main.c
        │
        └───FreeRTOS   
            │
            └───FreeRTOS-Kernel
                CMakeLists.txt
                FreeRTOSConfig.h
            
```

CmakeLists.txt
```
cmake_minimum_required(VERSION 3.12)

include(pico_sdk_import.cmake)

project(Pico-FreeRTOS)

pico_sdk_init()

add_subdirectory(freertos)
add_subdirectory(ProjectFiles)
```
main.c 
```
add_executable(blink
        main.c
)

target_link_libraries(blink pico_stdlib freertos)
pico_add_extra_outputs(blink)
```
CmakeLists.txt
```
set(PICO_SDK_FREERTOS_SOURCE FreeRTOS-Kernel)

add_library(freertos
    ${PICO_SDK_FREERTOS_SOURCE}/event_groups.c
    ${PICO_SDK_FREERTOS_SOURCE}/list.c
    ${PICO_SDK_FREERTOS_SOURCE}/queue.c
    ${PICO_SDK_FREERTOS_SOURCE}/stream_buffer.c
    ${PICO_SDK_FREERTOS_SOURCE}/tasks.c
    ${PICO_SDK_FREERTOS_SOURCE}/timers.c
    ${PICO_SDK_FREERTOS_SOURCE}/portable/MemMang/heap_3.c
    ${PICO_SDK_FREERTOS_SOURCE}/portable/GCC/ARM_CM0/port.c
)

target_include_directories(freertos PUBLIC
    .
    ${PICO_SDK_FREERTOS_SOURCE}/include
    ${PICO_SDK_FREERTOS_SOURCE}/portable/GCC/ARM_CM0
)
```
FreeRTOSConfig.h
```
#ifndef FREERTOS_CONFIG_H
#define FREERTOS_CONFIG_H

/* Use Pico SDK ISR handlers */
#define vPortSVCHandler         isr_svcall
#define xPortPendSVHandler      isr_pendsv
#define xPortSysTickHandler     isr_systick

#define configUSE_PREEMPTION                    1
#define configUSE_PORT_OPTIMISED_TASK_SELECTION 0
#define configUSE_TICKLESS_IDLE                 0
#define configCPU_CLOCK_HZ                      133000000
#define configTICK_RATE_HZ                      100
#define configMAX_PRIORITIES                    5
#define configMINIMAL_STACK_SIZE                128
#define configMAX_TASK_NAME_LEN                 16
#define configUSE_16_BIT_TICKS                  0
#define configIDLE_SHOULD_YIELD                 1
#define configUSE_TASK_NOTIFICATIONS            1
#define configTASK_NOTIFICATION_ARRAY_ENTRIES   3
#define configUSE_MUTEXES                       0
#define configUSE_RECURSIVE_MUTEXES             0
#define configUSE_COUNTING_SEMAPHORES           0
#define configQUEUE_REGISTRY_SIZE               10
#define configUSE_QUEUE_SETS                    0
#define configUSE_TIME_SLICING                  0
#define configUSE_NEWLIB_REENTRANT              0
#define configENABLE_BACKWARD_COMPATIBILITY     0
#define configNUM_THREAD_LOCAL_STORAGE_POINTERS 5
#define configSTACK_DEPTH_TYPE                  uint16_t
#define configMESSAGE_BUFFER_LENGTH_TYPE        size_t

/* Memory allocation related definitions. */
#define configSUPPORT_STATIC_ALLOCATION         0
#define configSUPPORT_DYNAMIC_ALLOCATION        1
#define configAPPLICATION_ALLOCATED_HEAP        1

/* Hook function related definitions. */
#define configUSE_IDLE_HOOK                     0
#define configUSE_TICK_HOOK                     0
#define configCHECK_FOR_STACK_OVERFLOW          0
#define configUSE_MALLOC_FAILED_HOOK            0
#define configUSE_DAEMON_TASK_STARTUP_HOOK      0

/* Run time and task stats gathering related definitions. */
#define configGENERATE_RUN_TIME_STATS           0
#define configUSE_TRACE_FACILITY                0
#define configUSE_STATS_FORMATTING_FUNCTIONS    0

/* Co-routine related definitions. */
#define configUSE_CO_ROUTINES                   0
#define configMAX_CO_ROUTINE_PRIORITIES         1

/* Software timer related definitions. */
#define configUSE_TIMERS                        1
#define configTIMER_TASK_PRIORITY               3
#define configTIMER_QUEUE_LENGTH                10
#define configTIMER_TASK_STACK_DEPTH            configMINIMAL_STACK_SIZE

/* Define to trap errors during development. */
#define configASSERT( x )

/* Optional functions - most linkers will remove unused functions anyway. */
#define INCLUDE_vTaskPrioritySet                1
#define INCLUDE_uxTaskPriorityGet               1
#define INCLUDE_vTaskDelete                     1
#define INCLUDE_vTaskSuspend                    1
#define INCLUDE_xResumeFromISR                  1
#define INCLUDE_vTaskDelayUntil                 1
#define INCLUDE_vTaskDelay                      1
#define INCLUDE_xTaskGetSchedulerState          1
#define INCLUDE_xTaskGetCurrentTaskHandle       1
#define INCLUDE_uxTaskGetStackHighWaterMark     0
#define INCLUDE_xTaskGetIdleTaskHandle          0
#define INCLUDE_eTaskGetState                   0
#define INCLUDE_xEventGroupSetBitFromISR        1
#define INCLUDE_xTimerPendFunctionCall          0
#define INCLUDE_xTaskAbortDelay                 0
#define INCLUDE_xTaskGetHandle                  0
#define INCLUDE_xTaskResumeFromISR              1

/* A header file that defines trace macro can be included here. */

#endif /* FREERTOS_CONFIG_H */
```
Main.c
```
#include <FreeRTOS.h>
#include <task.h>
#include <stdio.h>
#include "pico/stdlib.h"


void led_task()
{   
    const uint LED_PIN = PICO_DEFAULT_LED_PIN;
    gpio_init(LED_PIN);
    gpio_set_dir(LED_PIN, GPIO_OUT);
    while (true) {
        gpio_put(LED_PIN, 1);
        vTaskDelay(100);
        gpio_put(LED_PIN, 0);
        vTaskDelay(100);
    }
}

int main()
{
    stdio_init_all();

    xTaskCreate(led_task, "LED_Task", 256, NULL, 1, NULL);
    vTaskStartScheduler();

    while(1){};
}
```





---


https://learnembeddedsystems.co.uk/pico-blink-led-code
CMakeLists.txt
```
cmake_minimum_required(VERSION 3.12)

include(pico_sdk_import.cmake)

project(pico-projects)

pico_sdk_init()

add_executable(blink_led blink_led.c)

target_link_libraries(blink_led pico_stdlib)

pico_add_extra_outputs(blink_led)
```
blink_led.c
```
#include "pico/stdlib.h"

int main(){
    // initialise GPIO (Green LED connected to pin 25)
    gpio_init(25);
    gpio_set_dir(25, GPIO_OUT);

    //Main Loop 
    while(1){
        gpio_put(25, 1); // Set pin 25 to high
        sleep_ms(500); // 0.5s delay
        gpio_put(25, 0); // Set pin 25 to low
        sleep_ms(500); // 0.5s delay
    }
}
```
---
https://learnembeddedsystems.co.uk/

https://www.youtube.com/playlist?list=PLEB5F4gTNK68IlRIJtcJ_2cW4dSdmreTw

https://github.com/LearnEmbeddedSystems/rp2040-freertos-project

https://github.com/LearnEmbeddedSystems/rp2040-freertos-project

https://github.com/FreeRTOS/FreeRTOS-Kernel



# Linux

whoami
man
clear
intro to options
pwd
ls
cd
mkdir
touch
rmdir
rm
open
mv
cp
head
tail
date
redirecting standard output
cat
less
echo
wc
piping
sort
uniq
expansions
diff
find
grep
du
df
history
ps
top
kill
killall
jobs, bg, and fg
gzip
gunzip
tar (the bomb disarming command)
nano
alias
xargs
ln
who
su
sudo
passwd
chown
Understanding permissions
chmod


Linux Commands - Basic Bash Command Line Tips You Should Know
Beau Carnes
Beau Carnes
Linux Commands - Basic Bash Command Line Tips You Should Know
Linux has a ton of commands, but most people only use a fraction of them. Here are some of the most used Linux commands to use in the terminal.

First, we'll cover some tips that will make the command line easier to use:

Use tab for autocompletion. After you start typing something in the Linux terminal, hit tab and it will suggest possible options that start with the string you have typed so far.
Use ctrl+r search_term to search commands you have previously used.
Quickly move to the beginning or end of a line with ctrl+a and ctrl+e.
Reuse the previous command in the present command with !!.
You can run multiple commands in a single line by separating commands with a ;.
It's time to learn the common Linux commands. You can get more information about any of these commands by using the man command. This will bring up the manual page for a command. For example, if you type man cat into a linux terminal, you will get more information about the cat command.

ls
List directory contents.
Example: ls /applications will display all the files and folders stored in the applications folder.
列出目錄內容。
示例： ls /applications將顯示存儲在應用程序文件夾中的所有文件和文件夾。

cd
Change to a directory.
Example: Change from the current directory to /usr/local with cd /usr/local.
切換到一個目錄。
示例：使用.從當前目錄更改為/usr/localcd /usr/local。

mv
Rename or move file(s) or directories.
Example: the command mv todo.txt /home/qlarson/Documents would move "todo.txt" to the "Documents" directory.
重命名或移動文件或目錄。
示例：該命令mv todo.txt /home/qlarson/Documents會將“todo.txt”移動到“Doc​​uments”目錄。

mkdir
Create a new directory.
Example: mkdir freecodecamp will make a directory named "freecodecamp".
創建一個新目錄。
示例：mkdir freecodecamp將創建一個名為“freecodecamp”的目錄。

rmdir
Delete empty directories.
刪除空目錄。

touch
Create an empty file with the specified name.
創建一個具有指定名稱的空文件。

rm
Remove file(s) and/or directories.
Example: rm todo.txt will delete the file.
刪除文件和/或目錄。
示例：rm todo.txt將刪除文件。

locate
Locate a specific file.
Example: locate -i vacuum*mop command will search for any file that contains the word "vacuum" and "mop". The -i makes the search case-insensitive.
找到一個特定的文件。
示例： locate -i vacuum*mop命令將搜索包含單詞“vacuum”和“mop”的任何文件。使-i搜索不區分大小寫。

clear
Clear a command line screen/window for a fresh start.
清除命令行屏幕/窗口以重新開始。

cp
Copy files and directories.
Example: the command cp todo.txt /home/qlarson/Documents would create a copy of "todo.txt" to the "Documents" directory.
複製文件和目錄。
示例：該命令cp todo.txt /home/qlarson/Documents將創建“todo.txt”的副本到“Doc​​uments”目錄。

alias
Create an alias for Linux commands.
Example: alias search=grep will allow you to use search instead of grep.
為 Linux 命令創建別名。
示例： alias search=grep將允許您使用search而不是grep.

cat
Display the contents of a file on the screen.
Example: cat todo.txt will show the text of "todo.txt" on the screen.
在屏幕上顯示文件的內容。
示例：cat todo.txt將在屏幕上顯示“todo.txt”的文本。

chown
Change who owns a file.
Example: chown qlarson todo.txt will make "qlarson" the owner of "todo.txt".
更改誰擁有文件。
示例：chown qlarson todo.txt將使“qlarson”成為“todo.txt”的所有者。

chmod
Change a file’s permissions.
Example: chmod 777 todo.txt will make "todo.txt" readable, writable, and executable by everyone. The digits in "777" specify the permissions for user, group, and others, in that order.
更改文件的權限。
示例：chmod 777 todo.txt將使“todo.txt”對每個人都可讀、可寫和可執行。“777”中的數字按順序指定用戶、組和其他人的權限。

sudo
Perform tasks that require administrative or root permissions.
Example: Use sudo passwd quincy to change the password of user "quincy".
"Sudo make me a sandwich."
執行需要管理或 root 權限的任務。
示例：sudo passwd quincy用於更改用戶“quincy”的密碼。
“須藤給我做三明治。”

find
Search for files matching a provided pattern. This command is for searching file(s) and folder(s) using filters such as name, size, access time, and modification time.
Example: find /home/ -name todo.txt  will search for a file named "todo.txt" within the home directory and its subdirectories.
搜索與提供的模式匹配的文件。此命令用於使用名稱、大小、訪問時間和修改時間等過濾器搜索文件和文件夾。
示例：find /home/ -name todo.txt  將在主目錄及其子目錄中搜索名為“todo.txt”的文件。

grep
Search files or output for a particular string or expression. This command searches for lines containing a specified pattern and, by default, writes them to the standard output.
Example: grep run todo.txt will search for the word "run" in the "todo.txt" file. Lines that contain "run" will be displayed.
搜索特定字符串或表達式的文件或輸出。此命令搜索包含指定模式的行，默認情況下，將它們寫入標準輸出。
示例：grep run todo.txt將在“todo.txt”文件中搜索單詞“run”。將顯示包含“運行”的行。

date
Display or set the system date and time.
顯示或設置系統日期和時間。

df
Display report on the system’s disk space usage.
顯示有​​關係統磁盤空間使用情況的報告。

du
Show how much space each file takes up. This will show the size in disk block numbers. If you want to see it in bytes, kilobytes, and megabytes, add the -h argument like this: du -h.
顯示每個文件佔用了多少空間。這將顯示磁盤塊號的大小。如果您想以字節、千字節和兆字節為單位查看它，請添加如下-h參數：du -h.

file
Determine the type of a file.
Example: file todo.txt would likely show the type of "ASCII text".
確定文件的類型。
示例：file todo.txt可能會顯示“ASCII 文本”的類型。

history
Shows the command history.
顯示命令歷史。

kill
Stop a process.
Example: Stop a process with a PID of 485 using the command kill 485. Use the ps command (below) to determine the PID of a process.
停止一個進程。
示例：使用命令停止 PID 為 485 的進程kill 485。使用ps命令（如下）確定進程的 PID。

less
View the contents of a file one page at a time.
Example: less todo.txt will display the contents of "todo.txt".
一次查看一頁文件的內容。
示例：less todo.txt 將顯示“todo.txt”的內容。

ps
Display a list of the currently running processes. This can be used to determine PIDs needed to kill processes.
顯示當前正在運行的進程的列表。這可用於確定kill進程所需的 PID。

pwd
Display the pathname for the current directory. "print working directory"
顯示當前目錄的路徑名。“打印工作目錄” _ _

ssh
Remotely log in to another Linux machine, over the network.
Example: ssh quincy@104.25.105.32 will login to 104.25.105.32 using the username "quincy".
通過網絡遠程登錄到另一台 Linux 機器。
示例：ssh quincy@104.25.105.32將使用用戶名“quincy”登錄到 104.25.105.32。

tail - Display the last 10 lines of a file. See fewer or more lines by using the -n (number) option.
Example: tail -n 5 todo.txt will display the last 5 lines of "todo.txt".
tail - 顯示文件的最後 10 行。使用 -n（數字）選項查看更少或更多的行。
示例：tail -n 5 todo.txt將顯示“todo.txt”的最後 5 行。


tar
Store and extract files from a tarfile (.tar) or tarball (.tar.gz or .tgz).
從 tarfile (.tar) 或 tarball（.tar.gz 或 .tgz）中存儲和提取文件。

top
Displays the resources being used on your system, similar to the task manager in Windows.
顯示系統上正在使用的資源，類似於 Windows 中的任務管理器。


# Python

## Scikit-Learn
https://scikit-learn.org/stable/auto_examples/index.html

https://scikit-learn.org/stable/_downloads/6f1e7a639e0699d6164445b55e6c116d/auto_examples_jupyter.zip

https://scikit-learn.org/stable/_downloads/07fcc19ba03226cd3d83d4e40ec44385/auto_examples_python.zip

## Beautiful Soup
$ pip install bs4
$ pip install requests
$ pip install flask
$ pip install flask-restx
$ pip install python-decouple


## 呼叫多部檔案
file_two.py
```python
# Python module to import

print("File two __name__ is set to: {}" .format(__name__))

def function_three():
   print("Function three is executed")

def function_four():
   print("Function four is executed")

if __name__ == "__main__":
   print("File two executed when ran directly")
else:
   print("File two executed when imported")
```
file_one.py
```python=
# Python module to execute
from file_two import function_three

print("File one __name__ is set to: {}" .format(__name__))

def function_one():
   print("Function one is executed")

def function_two():
   print("Function two is executed")

if __name__ == "__main__":
   print("File one executed when ran directly")
   function_two()
   function_three()
else:
   print("File one executed when imported")
```
# 熱門書籍

## 駭客
## 遊戲
## PyQt5
## Pandas資料清理、重塑、過濾、視覺化
## SQL
## Excel VBA
## LINE Bot機器人

## SciPy是演算法和數學工具包。
SciPy包含的模組有最佳化、線性代數、積分、插值、特殊函數、快速傅立葉轉換、訊號處理和圖像處理、常微分方程式求解和其他科學與工程中常用的計算。與其功能相類似的軟體還有MATLAB、GNU Octave和Scilab。科學運算

Julia 語言集C語言的執行速度、Ruby 的靈活
JavaScript

## 名詞
神經網路(NN)
積神經網路(CNN)
物件偵測(YOLO)
光學文字辨識(OCR)
車牌辨識(ANPR)
人臉辨識
生成對抗網路 (GAN)
深度偽造 (DeepFake)
自然語言處理(NLP)
聊天機器人(ChatBot)
語音辨識(ASR)
強化學習(RL)

## 演算法
演算法
具體的機器學習演算法有：
構造間隔理論分布：聚類分析和圖型識別
人工神經網路
決策樹（Decision tree ）
聚類分析（Cluster analysis）
決策樹 ( ecision Tree )
隨機森林 ( Random Forest )

降維 七種降維方法
缺失值比率 (Missing Values Ratio)
低方差濾波 (Low Variance Filter)
高相關濾波 (High Correlation Filter)
隨機森林/組合樹 (Random Forests)
主成分分析 (PCA)
反向特徵消除 (Backward Feature Elimination)
前向特徵構造 (Forward Feature Construction)

非監督式學習 (Unsupervised Learning) 
做的處理是依照關聯性去歸類 (Co-occurance Grouping)、
找出潛在規則與套路 (Association Rule Discovery)、
形成集群 (Clustering)，不對資訊有正確或不正確的判別。


感知器
支援向量機
整合學習AdaBoost
降維與度量學習
聚類
貝氏分類器
構造條件機率：迴歸分析和統計分類
高斯過程迴歸
線性判別分析
最近鄰居法
徑向基函數核
通過再生模型構造機率密度函數：
最大期望演算法
機率圖模型：包括貝氏網路和Markov隨機場
Generative Topographic Mapping
近似推斷技術：
馬可夫鏈
蒙特卡羅方法
變分法
最佳化：大多數以上方法，直接或者間接使用最佳化演算法。
量子機器學習


## 程式交易
股票×期貨交易

## 物聯網
樹莓派 Raspberry Pi
AIOT與OpenCV實戰應用、樹莓派、物聯網與機器視覺
MicroPython
Arduino物聯網

## 雲端服務
Microsoft Azure
Flask 網頁開發
架站特訓班：Django
AWS
網路爬蟲

## 人工智慧
人工神經網路
PyTorch自然語言

## 機器學習
Scikit-Learn
TensorFlow
資料科學的統計：機器學習建模
資料科學•機器學習 －NumPy、Pandas、Matplotlib、OpenCV
生成對抗網路（GAN）

## 深度學習
AI影像
Keras
深度學習（Deep Learning）
器學習大致上可以分為三類：
監督式學習 (Supervised Learning)、
非監督式學習 (Unsupervised Learing) 
增強式學習 (Reinforcement Learning)。

深度神經網路（DNN：Deep Neural Networks）
深度置信網路（DBN：deep belief networks）
卷積神經網路（CNN：Convolutional Neural Network）
卷積深度置信網路（CDBN：convolutional deep belief networks）
自然語言處理（NLP：Natural Language Processing）
訓練深度學習模型
監督式學習 監督學習（Supervised learning）
無監督學習（unsupervised learning）
強化學習（RL：Reinforcement learning）


深度增強式學習
人工神經網路（ANN：Artificial Neural Network）
神經網路
卷積神經網路 (CNN)
反卷積神經網路 (DNN)
深度神經網路（DNN：Deep Neural Networks）
生成對抗網路 (GAN：Generative Adversarial Network）
遞迴 or 循環神經網路（RNN：Recurrent neural network）
轉換器
人工神經網絡下的深度學習
深度學習結構
深度神經網絡
深度神經網絡的問題
深度置信網絡
卷積神經網絡
卷積深度置信網絡
語音識別
圖像分類
深度學習與神經科學
公眾視野中的深度學習
梯度下降法（Gradient descent）


特徵工程（Feature engineering）
深度（Depth）、或者稱為層數（Number of layers）
決定深度學習透過多層感知器（Multi-layer perceptron, MLP）
電腦視覺（Computer vision）

深度學習庫

Torch
TensorFlow
Theano
PaddlePaddle
Deeplearning
Caffe
roNNie
Keras
MXNet


演算法
具體的機器學習演算法有：

構造間隔理論分布：聚類分析和圖型識別
人工神經網路
感知器
支援向量機
整合學習AdaBoost
降維與度量學習
聚類
貝氏分類器


梯度下降法
線性回歸、邏輯回歸和softmax 回歸
01 程式設計和數學基礎
1.1 Python 快速入門
1.2 張量函數庫NumPy
1.3 微積分
1.4 機率基礎

02 梯度下降法
2.1 函數極值的必要條件
2.2 梯度下降法基礎
2.3 梯度下降法的參數最佳化策略
2.4 梯度驗證
2.5 分離梯度下降法與參數最佳化策略

03 線性回歸、邏輯回歸和softmax 回歸
3.1 線性回歸
3.2 資料的規範化
3.3 模型的評估
3.4 正則化
3.5 邏輯回歸
3.6 softmax 回歸
3.7 批次梯度下降法和隨機梯度下降法

04 神經網路
4.1 神經網路概述
4.2 反向求導
4.3 實現一個簡單的深度學習框架

05 改進神經網路性能的基本技巧
5.1 資料處理
5.2 參數偵錯
5.3 批次規範化
5.4 正則化
5.5 梯度爆炸和梯度消失

06 卷積神經網路
6.1 卷積入門
6.2 卷積神經網路概述
6.3 卷積的矩陣乘法
6.4 基於座標索引的快速卷積
6.5 典型卷積神經網路結構

07 循環神經網路
7.1 序列問題和模型
7.2 循環神經網路基礎
7.3 穿過時間的反向傳播
7.4 單層循環神經網路的實現
7.5 循環神經網路語言模型和文字的生成
7.6 循環神經網路中的梯度爆炸和梯度消失
7.7 長短期記憶網路
7.8 門控循環單元
7.9 循環神經網路的類別及其實現
7.10 多層循環神經網路和雙向循環神經網路
7.11 Seq2Seq 模型

08 生成模型
8.1 生成模型概述
8.2 自動編碼器
8.3 變分自動編碼器
8.4 生成對抗網路
8.5 生成對抗網路建模實例
8.6 生成對抗網路的損失函數及其機率解釋
8.7 改進的損失函數—Wasserstein GAN
8.8 深度卷積對抗網路


|Chapter 05| 自然語言處理
5.1 讓我著迷的Word2Vec
5.2 詞向量的使用與視覺化
5.3 語言與RNN
5.4 Hello RNN! 中文文本生成實作範例
5.5 打掉重練的勇氣：Google 翻譯與Seq2Seq
5.6 大躍進：注意力機制
5.7 注意力才是王道：Transformer
5.8 Hello Transformer! 二訪中文文本生成實作範例
5.9 再度大躍進：BERT
5.10 Hello BERT! 文字情緒分析實作範例

|Chapter 06| 電腦視覺
6.1 從ImageNet發起的資料大戰
6.2 圖像與CNN
6.3 文字也有結構，圖像也有序列
6.4 圖像描述生成實作範例
6.5 改變世界的GAN
6.6 字型風格轉換實作分享

|Chapter 07| 強化學習
7.1 決策與RL
7.2 用RL玩電動：Deep Atari
7.3 Hello RL! CartPole實作範例
7.4 用RL打撞球：DeepCueLearning實作分享
7.5 令世界驚艷的AlphaGo

第 1 章 機器與深度學習常用的數學基礎
1.1 數值資料表示方式
1.1.1 純量 (scalar)
1.1.2 向量 (vector)
1.1.3 矩陣 (matrix)
1.1.4 張量 (tensor)
1.2 向量與矩陣運算
1.2.1 向量和純量相乘
1.2.2 向量相乘
1.2.3 矩陣相乘
1.2.4 Hadamard 乘積
1.2.5 逆矩陣 (反矩陣)
1.3 矩陣分解
1.3.1 特徵分解 (Eigenvalue decomposition)
1.3.2 奇異值分解 (SVD)
 
第 2 章 機器學習相關機率論 
2.1 集合
2.2 隨機試驗與樣本空間
2.2.1 隨機試驗範例
2.2.2 隨機試驗與公正與否
2.3 事件
2.3.1 基本事件與複合事件
2.3.2 事件空間
2.4 事件的機率
2.4.1 事件機率三大公理
2.4.2 事件機率相同的例子
2.4.3 事件機率不同的例子
2.4.4 事件機率運算規則
2.5 條件機率與貝氏定理
2.5.1 條件機率
2.5.2 貝氏定理
2.5.3 統計獨立
2.6 隨機變數
2.6.1 隨機變數的類型
2.6.2 多維隨機變數
2.7 機率分布與機率密度函數
2.7.1 機率分布
2.7.2 數位化都是離散型的隨機變數
2.7.3 一維機率密度函數
2.7.4 多維機率密度函數 (聯合機率密度函數)
2.7.5 邊際機率密度函數
2.8 機器學習常用到的統計機率模型
2.8.1 伯努利分布 (Bernoulli Distribution)
2.8.2 二項分布 (Binomial Distribution)
2.8.3 均勻分布 (Uniform Distribution)
2.8.4 常態分布 (Normal Distribution)
 
第 3 章 機器學習常用的統計學 (一)
3.1 資料結構分類
3.1.1 「正確的資料」與「好品質的資料」
3.1.2 結構化資料
3.1.3 非結構化資料
3.1.4 半結構化資料
3.2 將統計量作為資料的特徵表徵
3.2.1 期望值
3.2.2 各階中心動差
3.2.3 相關係數與共變異數
3.2.4 共變異數矩陣
 
第 4 章 機器學習常用的統計學 (二)
4.1 母體與樣本估計
4.1.1 樣本統計量與抽樣分布
4.1.2 樣本平均數的期望值等於母體平均數
4.1.3 樣本變異數的期望值等於母體變異數
4.1.4 小結
4.2 信賴區間
4.2.1 信賴區間與顯著水準、信心水準的關係
4.3 母體為常態分布的區間估計
4.31 常態分布的特性
4.3.2 將常態分布標準化：z-score
4.3.3 標準常態分布平均值的區間估計
4.3.4 每次抽樣都有不同的信賴區間
4.3.5 信賴區間的用途
4.4 自由度 (Degree of Freedom)
4.5 t-分布 (t-distribution)
4.5.1 t 值 (t-score)：母體為常態，但標準差未知的情況
4.5.2 t 值與 z 值的關係
4.5.3 t-分布：隨機變數 t 的機率分布
4.6 抽樣數的選擇
4.6.1 母體數有無限個的情況
4.6.2 有限母體數的修正
4.7 假設檢定
4.7.1 假設檢定的預備知識
4.7.2 虛無假設、對立假設
4.7.3 檢定虛無假設成立的機率
4.7.4 計算橫軸上的 t 值
4.7.5 計算 p 值
 
第 5 章 機器學習常用的資料處理方式 
5.1 資料標準化
5.1.1 Z 值標準化
5.1.2 Min-max 正規化
5.2 資料縮放
5.3 非線性轉換
5.3.1 對數函數能將數值範圍縮小
5.3.2 指數函數將數值轉換到特定範圍
5.3.3 非線性轉換較少用於資料前處理的原因
5.4 類別變數編碼
5.4.1 One-hot encoding
5.4.2 目標編碼 Target encoding
 
第 6 章 機器與深度學習常用到的基礎理論 
6.1 機器、深度學習與統計學的關係
6.1.1 統計學與機器學習 (深度學習) 的差異
6.1.2 機器學習和深度學習的差異
6.2 監督式學習與非監督式學習
62.1 監督式學習 (Supervised Learning)
6.2.2 非監督式學習 (Unsupervised Learning)
6.3 最大概似估計
6.3.1 概似函數 (likelihood function)
6.3.2 範例：伯努利抽紅白球的機率
6.3.3 範例：常態分布找出平均值與變異數
6.4 貝氏法則理論與最大後驗機率
6.41 貝氏法則理論
6.4.2 最大後驗機率法
6.4.3 最大後驗機率法範例
6.5 常用到的距離和相似度計算方式
6.5.1 曼哈頓距離 (Manhattan Distance)
6.5.2 歐幾里得距離 (Euclidean Distance)，歐氏距離
6.5.3 明可夫斯基距離 (Minkowski distance)
6.5.4 餘弦相似度 (Cosine similarity)
6.5.5 馬氏距離 (Mahalanobis Distance)
6.5.6 雅卡爾相似度係數 (Jaccard similarity coefficient)
6.6 損失函數
6.6.1 迴歸常用的損失函數：均方誤差、平均絕對值誤差
6.6.2 迴歸常用的損失函數：Huber 損失函數
6.6.3 分類常用的損失函數：交叉熵
6.6.4 交叉熵與相對熵、最大概似估計的關係
 
第 7 章 迴歸分析 Regression 
7.1 簡單線性迴歸分析
7.1.1 用最小平方法找迴歸方程式
7.1.2 用最大概似函數估計法找迴歸方程式
7.2 多元線性迴歸分析
7.2.1 多元迴歸用向量與矩陣表示
7.2.2 用最小平方法求參數向量
7.3 非線性迴歸分析
 
第8章 分類 Classification
8.1 單純貝氏分類器 (Naive Bayes Classifier)
8.1.1 單純貝氏分類器的公式
8.1.2 高斯單純貝氏分類器
8.1.3 單純貝氏分類器的缺點與優點
8.2 線性區別分析 (LDA)
8.2.1 LDA 的概似函數
8.2.2 LDA 分類器公式
8.2.3 二分類的 LDA
8.3 羅吉斯迴歸 (Logistic Regression)
8.3.1 羅吉斯迴歸用 Sigmoid 函數限制值域
8.3.2 羅吉斯迴歸求參數的方法
 
第 9 章 統計降維法 Dimension Reduction 
9.1 特徵數過多的問題
9.2 特徵選取法
9.2.1 刪除變異量最小的特徵資料
9.2.2 單一變數特徵選擇：迴歸任務
9.23 單一變數特徵選擇：分類任務
9.2.4 順序特徵選取
9.3 特徵萃取法
9.3.1 向量做投影空間轉換
9.3.2 PCA 主成分分析
9.3.3 LDA 線性區別分析
9.3.4 主成分分析 (PCA) 和線性區別分析 (LDA) 的差異
 
第 10 章 類神經網路 Artificial Neural Network 
10.1 感知機神經網路 (Perceptron Neural Network)
10.1.1 常用的激活函數 (Activation function)
10.1.2 感知機神經網路運作範例
10.2 多層感知機神經網路 (Multilayer perceptron，MLP)
10.2.1 多層感知機神經網路與深度學習的區別
10.2.2 透過激活函數做到特徵非線性轉換
10.3 神經網路的前向傳遞
10.3.1 輸入層到隱藏層的前向傳遞
10.3.2 隱藏層到輸出層的前向傳遞
 
第 11 章 梯度下降法 Gradient Descent
11.1 梯度是微分的觀念
11.1.1 用微分找函數的極小值
11.1.2 離散資料用逼近的方式求解
11.1.3 梯度與梯度方向
11.2 梯度下降法的作法
11.2.1 梯度下降法的運算方式
11.2.2 學習率過大會無法收斂
11.2.3 學習率過小有可能只找到局部低點
 
第 12 章 倒傳遞學習法 Backpropagation
12.1 最小化損失函數以找出權重參數
12.2 隱藏層到輸出層的梯度
12.3 輸入層到隱藏層的梯度
12.4 前向傳遞與倒傳遞範例實作
12.4.1 前向傳遞計算預測值
12.4.2 用倒傳遞學習法反推以更新權重
12.4.3 用更新後的權重參數再做前向傳遞
12.5 梯度消失與梯度爆炸
 
第 13 章 參數常規化 Parameter Regularization
13.1 訓練擬合 (fitting) 的問題
13.2 損失函數加上懲罰項可避免過擬合
13.2.1 損失函數未加入懲罰項的範例
13.2.2 加入懲罰項做參數常規化的範例
13.2.3 λ 值對於常規化的影響
13.3 用懲罰項限制損失函數的求解範圍
13.4 常規化實際的解空間
 
第 14 章 模型評估 Model Validation
14.1 二元分類模型評估指標
14.1.1 二元分類的混淆矩陣
14.1.2 評估指標－正確率
14.1.3 評估指標－靈敏度、特異度
14.1.4 評估指標－偽陰性率、偽陽性率
14.1.5 評估指標－陽性預測值、陰性預測值
14.1.6 評估指標－陽性概似比、陰性概似比
14.1.7 評估指標－F1score 與 F(beta)score
14.1.8 評估指標－G-mean
14.1.9 算出所有的評估指標
14.1.10 ROC 曲線
14.2 多元分類評估指標
14.2.1 評估指標說明
14.2.2 多元評估指標範例
14.3 迴歸模型評估指標 (Regression Metrics)
14.3.1 三種評估指標－MSE、MAE、MSLE
14.3.2 MSLE 的優勢
14.4 交叉驗證：如何選取模型與模型評估
14.4.1 Resubstitution
14.4.2 Holdout CV
14.4.3 k-fold CV
14.4.4 Leave-one-out CV

目錄
序言
第一篇 何謂數學模型
第1章 資料分析與數學模型
1.1 資料分析
1.2 數學模型的作用

第2章 數學模型的組成元素與類型
2.1 變數、數學結構、參數
2.2 數學模型與自然科學的基礎理論
2.3 理解導向建模與應用導向建模
2.4 理解導向建模
2.5 應用導向建模
2.6 數學模型的限制與適用範圍

第二篇 基礎數學模型
第3章 由簡單方程式建構而成之模型
3.1 線性模型（Linear Model）
3.2 實驗公式與曲線擬合
3.3 最佳化問題（Optimization Problem）

第4章 由基本微分方程式建構而成之模型
4.1 可求解的微分方程式模型
4.2 非線性微分方程式模型
4.3 可求解之模型和不可求解之模型
4.4 控制理論（Control Theory）

第5章 機率模型
5.1 隨機過程（Stochastic Process）
5.2 馬可夫過程（Markov Process）
5.3 排隊理論

第6章 統計模型
6.1 常態分佈
6.2 統計檢定
6.3 迴歸分析

第三篇 進階數學模型
第7章 時間序列模型
7.1 時間序列資料之結構
7.2 使用可觀測變數之模型
7.3 狀態空間模型（State Space Model）
7.4 他種類的時間序列分析法

第8章 機器學習（Machine Learning）模型
8.1 機器學習使用的模型與處理的問題特徵
8.2 分類（Classifification）、迴歸問題（Regression）
8.3 分群
8.4 降維（Dimensionality Reduction）
8.5 深度學習（Deep Learning）

第9章 強化式學習（Reinforcement Learning）模型
9.1 以強化式學習做為行為模型
92 以強化式學習進行機器學習

第10章 多體系統模型(Many-body System) 模型
10.1 從微觀到宏觀
10.2 各種集體現象模型
10.3 交互作用的網路

第四篇 建立數學模型
第11章 決定模型的因素
11.1 數學模型的性質
11.2 理解導向建模的要點
11.3 應用導向建模的要點

第12章 設計模型
12.1 變數的選擇
12.2 資料取得與實驗設計
12.3 數學結構與參數的選擇
12.4 避免建模錯誤

第13章 參數估計
13.1 根據目的進行參數估計
13.2 參數估計中目標函數的最小化
13.3 貝氏推論（Bayesian Inference）與貝氏建模（Bayesian Modeling）

第14章 評估模型
14.1 什麼是「好的模型」？
14.2 分類準確率之指標
14.3 訊息準則（Information Criterion）
14.4 與虛無模型（Null Model）的比較與概似比檢驗（Likelihood Ratio Test）
14.5 交叉驗證（Cross-Validation）


目錄
01 Python 機器學習入門
1.1 機器學習簡介
1.2 安裝Anaconda（Python）
1.3 Python 快速入門
1.4 Python 基礎函數庫入門實戰
1.5 機器學習模型初探
1.6 本章小結
 
02 資料探索與視覺化
2.1 遺漏值處理
2.2 資料描述與異常值發現
2.3 視覺化分析資料關係
2.4 資料樣本間的距離
2.5 本章小結
 
03 特徵工程
3.1 特徵變換
3.2 特徵
3.3 特徵選擇
3.4 特徵提取和降維
3.5 資料平衡方法
3.6 本章小結
 
04 模型選擇和評估
4.1 模型擬合效果
4.2 模型訓練技巧
4.3 模型的評價指標
4.4 本章小結
 
05 假設檢驗和回歸分析
5.1 假設檢驗
5.2 一元回歸
5.3 多元回歸
5.4 正規化回歸分析
5.5 Logistic 回歸分析
5.6 本章小結
 
06 時間序列分析
6.1 時間序列資料的相關檢驗
6.2 移動平均演算法
6.3 ARIMA 模型
6.4 SARIMA 模型
6.5 Prophet 模型預測時間序列
6.6 多元時間序列ARIMAX模型
6.7 時序資料的異常值檢測
6.8 本章小結
 
07 聚類演算法與異常值檢測
7.1 模型簡介
7.2 資料聚類分析
7.3 資料異常值檢測分析
7.4 本章小結
 
08 決策樹和整合學習
8.1 模型簡介與資料準備
8.2 決策樹模型
8.3 隨機森林模型
8.4 AdaBoost 模型
8.5 梯度提升樹（GBDT）
8.6 本章小結
 
09 貝氏演算法和K- 近鄰演算法
9.1 模型簡介
9.2 貝氏分類演算法
9.3 貝氏網路資料分類
9.4 K- 近鄰演算法
9.5 本章小結
 
10 支持向量機和類神經網路
10.1 模型簡介
10.2 支援向量機模型
10.3 全連接神經網路模型
10.4 本章小結
 
11 連結規則與文字探勘
11.1 模型簡介
11.2 資料連結規則探勘
11.3 文字資料前置處理
11.4 文字聚類分析
11.5 《三國演義》人物關係分析
11.6 本章小結
 
12 深度學習入門
12.1 深度學習介紹
12.2 PyTorch 入門
12.3 卷積神經網路辨識草書
12.4 循環神經網路新聞分類
12.5 自編碼網路重構圖像
12.6 本章小結


目錄
第 1 章 機器與深度學習常用的數學基礎
1.1 數值資料表示方式
1.1.1 純量 (scalar)
1.1.2 向量 (vector)
1.1.3 矩陣 (matrix)
1.1.4 張量 (tensor)
1.2 向量與矩陣運算
1.2.1 向量和純量相乘
1.2.2 向量相乘
1.2.3 矩陣相乘
1.2.4 Hadamard 乘積
1.2.5 逆矩陣 (反矩陣)
1.3 矩陣分解
1.3.1 特徵分解 (Eigenvalue decomposition)
1.3.2 奇異值分解 (SVD)
 
第 2 章 機器學習相關機率論 
2.1 集合
2.2 隨機試驗與樣本空間
2.2.1 隨機試驗範例
2.2.2 隨機試驗與公正與否
2.3 事件
2.3.1 基本事件與複合事件
2.3.2 事件空間
2.4 事件的機率
2.4.1 事件機率三大公理
2.4.2 事件機率相同的例子
2.4.3 事件機率不同的例子
2.4.4 事件機率運算規則
2.5 條件機率與貝氏定理
2.5.1 條件機率
2.5.2 貝氏定理
2.5.3 統計獨立
2.6 隨機變數
2.6.1 隨機變數的類型
2.6.2 多維隨機變數
2.7 機率分布與機率密度函數
2.7.1 機率分布
2.7.2 數位化都是離散型的隨機變數
2.7.3 一維機率密度函數
2.7.4 多維機率密度函數 (聯合機率密度函數)
2.7.5 邊際機率密度函數
2.8 機器學習常用到的統計機率模型
2.8.1 伯努利分布 (Bernoulli Distribution)
2.8.2 二項分布 (Binomial Distribution)
2.8.3 均勻分布 (Uniform Distribution)
2.8.4 常態分布 (Normal Distribution)
 
第 3 章 機器學習常用的統計學 (一)
3.1 資料結構分類
3.1.1 「正確的資料」與「好品質的資料」
3.1.2 結構化資料
3.1.3 非結構化資料
3.1.4 半結構化資料
3.2 將統計量作為資料的特徵表徵
3.2.1 期望值
3.2.2 各階中心動差
3.2.3 相關係數與共變異數
3.2.4 共變異數矩陣
 
第 4 章 機器學習常用的統計學 (二)
4.1 母體與樣本估計
4.1.1 樣本統計量與抽樣分布
4.1.2 樣本平均數的期望值等於母體平均數
4.1.3 樣本變異數的期望值等於母體變異數
4.1.4 小結
4.2 信賴區間
4.2.1 信賴區間與顯著水準、信心水準的關係
4.3 母體為常態分布的區間估計
4.31 常態分布的特性
4.3.2 將常態分布標準化：z-score
4.3.3 標準常態分布平均值的區間估計
4.3.4 每次抽樣都有不同的信賴區間
4.3.5 信賴區間的用途
4.4 自由度 (Degree of Freedom)
4.5 t-分布 (t-distribution)
4.5.1 t 值 (t-score)：母體為常態，但標準差未知的情況
4.5.2 t 值與 z 值的關係
4.5.3 t-分布：隨機變數 t 的機率分布
4.6 抽樣數的選擇
4.6.1 母體數有無限個的情況
4.6.2 有限母體數的修正
4.7 假設檢定
4.7.1 假設檢定的預備知識
4.7.2 虛無假設、對立假設
4.7.3 檢定虛無假設成立的機率
4.7.4 計算橫軸上的 t 值
4.7.5 計算 p 值
 
第 5 章 機器學習常用的資料處理方式 
5.1 資料標準化
5.1.1 Z 值標準化
5.1.2 Min-max 正規化
5.2 資料縮放
5.3 非線性轉換
5.3.1 對數函數能將數值範圍縮小
5.3.2 指數函數將數值轉換到特定範圍
5.3.3 非線性轉換較少用於資料前處理的原因
5.4 類別變數編碼
5.4.1 One-hot encoding
5.4.2 目標編碼 Target encoding
 
第 6 章 機器與深度學習常用到的基礎理論 
6.1 機器、深度學習與統計學的關係
6.1.1 統計學與機器學習 (深度學習) 的差異
6.1.2 機器學習和深度學習的差異
6.2 監督式學習與非監督式學習
62.1 監督式學習 (Supervised Learning)
6.2.2 非監督式學習 (Unsupervised Learning)
6.3 最大概似估計
6.3.1 概似函數 (likelihood function)
6.3.2 範例：伯努利抽紅白球的機率
6.3.3 範例：常態分布找出平均值與變異數
6.4 貝氏法則理論與最大後驗機率
6.41 貝氏法則理論
6.4.2 最大後驗機率法
6.4.3 最大後驗機率法範例
6.5 常用到的距離和相似度計算方式
6.5.1 曼哈頓距離 (Manhattan Distance)
6.5.2 歐幾里得距離 (Euclidean Distance)，歐氏距離
6.5.3 明可夫斯基距離 (Minkowski distance)
6.5.4 餘弦相似度 (Cosine similarity)
6.5.5 馬氏距離 (Mahalanobis Distance)
6.5.6 雅卡爾相似度係數 (Jaccard similarity coefficient)
6.6 損失函數
6.6.1 迴歸常用的損失函數：均方誤差、平均絕對值誤差
6.6.2 迴歸常用的損失函數：Huber 損失函數
6.6.3 分類常用的損失函數：交叉熵
6.6.4 交叉熵與相對熵、最大概似估計的關係
 
第 7 章 迴歸分析 Regression 
7.1 簡單線性迴歸分析
7.1.1 用最小平方法找迴歸方程式
7.1.2 用最大概似函數估計法找迴歸方程式
7.2 多元線性迴歸分析
7.2.1 多元迴歸用向量與矩陣表示
7.2.2 用最小平方法求參數向量
7.3 非線性迴歸分析
 
第8章 分類 Classification
8.1 單純貝氏分類器 (Naive Bayes Classifier)
8.1.1 單純貝氏分類器的公式
8.1.2 高斯單純貝氏分類器
8.1.3 單純貝氏分類器的缺點與優點
8.2 線性區別分析 (LDA)
8.2.1 LDA 的概似函數
8.2.2 LDA 分類器公式
8.2.3 二分類的 LDA
8.3 羅吉斯迴歸 (Logistic Regression)
8.3.1 羅吉斯迴歸用 Sigmoid 函數限制值域
8.3.2 羅吉斯迴歸求參數的方法
 
第 9 章 統計降維法 Dimension Reduction 
9.1 特徵數過多的問題
9.2 特徵選取法
9.2.1 刪除變異量最小的特徵資料
9.2.2 單一變數特徵選擇：迴歸任務
9.23 單一變數特徵選擇：分類任務
9.2.4 順序特徵選取
9.3 特徵萃取法
9.3.1 向量做投影空間轉換
9.3.2 PCA 主成分分析
9.3.3 LDA 線性區別分析
9.3.4 主成分分析 (PCA) 和線性區別分析 (LDA) 的差異
 
第 10 章 類神經網路 Artificial Neural Network 
10.1 感知機神經網路 (Perceptron Neural Network)
10.1.1 常用的激活函數 (Activation function)
10.1.2 感知機神經網路運作範例
10.2 多層感知機神經網路 (Multilayer perceptron，MLP)
10.2.1 多層感知機神經網路與深度學習的區別
10.2.2 透過激活函數做到特徵非線性轉換
10.3 神經網路的前向傳遞
10.3.1 輸入層到隱藏層的前向傳遞
10.3.2 隱藏層到輸出層的前向傳遞
 
第 11 章 梯度下降法 Gradient Descent
11.1 梯度是微分的觀念
11.1.1 用微分找函數的極小值
11.1.2 離散資料用逼近的方式求解
11.1.3 梯度與梯度方向
11.2 梯度下降法的作法
11.2.1 梯度下降法的運算方式
11.2.2 學習率過大會無法收斂
11.2.3 學習率過小有可能只找到局部低點
 
第 12 章 倒傳遞學習法 Backpropagation
12.1 最小化損失函數以找出權重參數
12.2 隱藏層到輸出層的梯度
12.3 輸入層到隱藏層的梯度
12.4 前向傳遞與倒傳遞範例實作
12.4.1 前向傳遞計算預測值
12.4.2 用倒傳遞學習法反推以更新權重
12.4.3 用更新後的權重參數再做前向傳遞
12.5 梯度消失與梯度爆炸
 
第 13 章 參數常規化 Parameter Regularization
13.1 訓練擬合 (fitting) 的問題
13.2 損失函數加上懲罰項可避免過擬合
13.2.1 損失函數未加入懲罰項的範例
13.2.2 加入懲罰項做參數常規化的範例
13.2.3 λ 值對於常規化的影響
13.3 用懲罰項限制損失函數的求解範圍
13.4 常規化實際的解空間
 
第 14 章 模型評估 Model Validation
14.1 二元分類模型評估指標
14.1.1 二元分類的混淆矩陣
14.1.2 評估指標－正確率
14.1.3 評估指標－靈敏度、特異度
14.1.4 評估指標－偽陰性率、偽陽性率
14.1.5 評估指標－陽性預測值、陰性預測值
14.1.6 評估指標－陽性概似比、陰性概似比
14.1.7 評估指標－F1score 與 F(beta)score
14.1.8 評估指標－G-mean
14.1.9 算出所有的評估指標
14.1.10 ROC 曲線
14.2 多元分類評估指標
14.2.1 評估指標說明
14.2.2 多元評估指標範例
14.3 迴歸模型評估指標 (Regression Metrics)
14.3.1 三種評估指標－MSE、MAE、MSLE
14.3.2 MSLE 的優勢
14.4 交叉驗證：如何選取模型與模型評估
14.4.1 Resubstitution
14.4.2 Holdout CV
14.4.3 k-fold CV
14.4.4 Leave-one-out CV

目錄
Part01 深度學習簡介－從應用面看起

Ch01 生物視覺與機器視覺 (Biological and Machine Vision)
1.1 生物視覺 (Biological Vision)
1.2 機器視覺 (Machine Vision)
1.3 上 TensorFlow Playground 網站體驗深度學習
1.4 上限時塗鴉 (Quick Draw!) 網站體驗即時的深度學習運算能力
1.5 總結

Ch02 用機器處理自然語言 (Natural Language Processing)
2.1 深度學習 + 自然語言處理
2.2 將語言量化
2.3 Google Duplex 的自然語言功力
2.4 總結

Ch03 機器藝術 (Machine Arts)：對抗式生成網路 (Generative Adversarial Network) 概述
3.1 對抗式生成網路的源起
3.2 經由「計算」生成假的人臉
3.3 風格轉移 (Style transfer) – CycleGAN
3.4 將自己手繪的塗鴉轉換成照片 – cGAN
3.5 憑文字敘述就生成擬真圖片 – StackGAN
3.6 使用深度學習進行影像處理
3.7 總結

Ch04 遊戲對局 (Game-Playing Machines)：Alpha Go、DQN (Deep Q Network)、RL (Reinforcement Learning) 概述
4.1 強化式學習 (Reinforcement Learning)
4.2 深度強化式學習 (Deep Reinforcement Learning)
4.3 深度強化式學習的應用 (一)：電子遊戲
4.4 深度強化式學習的應用 (二)：棋盤類遊戲
4.5 深度強化式學習在真實世界的應用：操控物體
4.6 常用的深度強化式學習模擬環境
4.7 總結

Part02 深度學習的核心概念 - 神經網路 (Neural Network)

Ch05 先動手實作！5 行程式體驗神經網路模型
5.1 熟悉 Google Colab 執行環境
5.2 用 tf.Keras 套件建立淺層神經網路
5.3 總結

Ch06 神經網路的基礎：人工神經元和激活函數
6.1 認識生物神經網路
6.2 最早期的神經元：感知器 (Perceptron)
6.3 神經元的激活函數 (Activation Function)
6.4 激活函數的選擇
6.5 總結

Ch07 多神經元組成的神經網路
7.1 輸入層 (Input Layer)
7.2 密集層 (Dense Layer)
7.3 用密集神經網路辨識熱狗堡
7.4 用密集神經網路做多個速食的分類
7.5 回顧第 5 章的範例程式
7.6 總結

Ch08 訓練深度神經網路
8.1 損失函數 (Loss Function)
8.2 藉由訓練讓誤差值最小化
8.2.1 梯度下降法 (Gradient Descent)
8.2.2 學習率 (Learning rate)
8.2.3 批次量 (Batch-Size) 與隨機梯度下降法 (SGD)
8.2.4 從局部最小值 (Local Minimum) 脫離
8.3 反向傳播 (Back Propagation)
8.4 規劃隱藏層與各層神經元的數量
8.5 範例：建構多層神經網路
8.6 總結

Ch09 改善神經網路的訓練成效
9.1 權重初始化 (Weight Initialization)
9.2 解決梯度不穩定的問題
9.3 避免過度配適 (Overfitting) 的技巧
9.4 使用各種優化器 (Optimizer)
9.5 實作：用 tf.Keras 建構深度神經網路
9.6 改試試迴歸 (Regression) 範例
9.7 用 TensorBoard 視覺化判讀訓練結果
9.8 總結

Part03 深度學習的進階技術

Ch10 機器視覺實戰演練 - CNN (Convolutional Neural Network)
10.1 卷積神經網路 (CNN)
10.2 池化層 (Pooling Layer)
10.3 CNN 實作範例 (用 tf.Keras 重現 LeNet-5 經典架構)
10.4 進階的 CNN 技術 (用 tf.Keras 重現 AlexNet 與 VGGNet 架構)
10.5 殘差神經網路 (Residual Network)
10.6 機器視覺的各種應用
10.7 總結

Ch11 自然語言處理實戰演練 (一)：資料預處理、建立詞向量空間
11.1 自然語言資料的預處理
11.2 用 word2vec 建立詞向量空間
11.3 總結

Ch12 自然語言處理實戰演練 (二)：用密集神經網路、CNN 建立 NLP 模型
12.1 前置作業
12.2 進行簡單的資料預處理
12.3 用密集神經網路區分正評、負評
12.4 用 CNN 模型區分正評、負評
12.5 總結

Ch13 自然語言處理實戰演練 (三)：RNN 循環神經網路
13.1 RNN 循環神經網路
13.2 LSTM (長短期記憶神經網路)
13.3 雙向 LSTM (Bi-LSTMs)
13.4 以「函數式 API」建構非序列式 NLP 模型
13.5 總結

Ch14 藝術生成實戰演練 - GAN (Generative Adversarial Network)
14.1 GAN 的基本概念
14.2 《限時塗鴉！》資料集
14.3 建構鑑別器 (Discriminator) 神經網路
14.4 建構生成器 (Generator) 神經網路
14.5 結合生成器與鑑別器, 建構對抗式生成網路
14.6 訓練 GAN
14.7 總結

Ch15 遊戲對局實戰演練 - DRL (Deep Reinforcement Learning)、DQN (Deep Q Network)
15.1 強化式學習 (Reinforcement Learning) 的基本概念
15.2 DQN 的基本概念
15.3 建構 DQN 代理人
15.4 與 OpenAI Gym 環境互動
15.5 DQN 以外的代理人訓練方式
15.6 總結

Part04 AI 與你

Ch16 打造自己的深度學習專案
16.1 探索方向
16.2 晉升更高階的專案
16.3 模型建構流程建議
16.4 軟體 2.0 (Software 2.0)
16.5 通用人工智慧 (AGI) 的進展
16.6 總結

附錄 A 使用 Google 的 Colab 雲端開發環境

目錄
Part01 深度學習簡介－從應用面看起

Ch01 生物視覺與機器視覺 (Biological and Machine Vision)
1.1 生物視覺 (Biological Vision)
1.2 機器視覺 (Machine Vision)
1.3 上 TensorFlow Playground 網站體驗深度學習
1.4 上限時塗鴉 (Quick Draw!) 網站體驗即時的深度學習運算能力
1.5 總結

Ch02 用機器處理自然語言 (Natural Language Processing)
2.1 深度學習 + 自然語言處理
2.2 將語言量化
2.3 Google Duplex 的自然語言功力
2.4 總結

Ch03 機器藝術 (Machine Arts)：對抗式生成網路 (Generative Adversarial Network) 概述
3.1 對抗式生成網路的源起
3.2 經由「計算」生成假的人臉
3.3 風格轉移 (Style transfer) – CycleGAN
3.4 將自己手繪的塗鴉轉換成照片 – cGAN
3.5 憑文字敘述就生成擬真圖片 – StackGAN
3.6 使用深度學習進行影像處理
3.7 總結

Ch04 遊戲對局 (Game-Playing Machines)：Alpha Go、DQN (Deep Q Network)、RL (Reinforcement Learning) 概述
4.1 強化式學習 (Reinforcement Learning)
4.2 深度強化式學習 (Deep Reinforcement Learning)
4.3 深度強化式學習的應用 (一)：電子遊戲
4.4 深度強化式學習的應用 (二)：棋盤類遊戲
4.5 深度強化式學習在真實世界的應用：操控物體
4.6 常用的深度強化式學習模擬環境
4.7 總結

Part02 深度學習的核心概念 - 神經網路 (Neural Network)

Ch05 先動手實作！5 行程式體驗神經網路模型
5.1 熟悉 Google Colab 執行環境
5.2 用 tf.Keras 套件建立淺層神經網路
5.3 總結

Ch06 神經網路的基礎：人工神經元和激活函數
6.1 認識生物神經網路
6.2 最早期的神經元：感知器 (Perceptron)
6.3 神經元的激活函數 (Activation Function)
6.4 激活函數的選擇
6.5 總結

Ch07 多神經元組成的神經網路
7.1 輸入層 (Input Layer)
7.2 密集層 (Dense Layer)
7.3 用密集神經網路辨識熱狗堡
7.4 用密集神經網路做多個速食的分類
7.5 回顧第 5 章的範例程式
7.6 總結

Ch08 訓練深度神經網路
8.1 損失函數 (Loss Function)
8.2 藉由訓練讓誤差值最小化
8.2.1 梯度下降法 (Gradient Descent)
8.2.2 學習率 (Learning rate)
8.2.3 批次量 (Batch-Size) 與隨機梯度下降法 (SGD)
8.2.4 從局部最小值 (Local Minimum) 脫離
8.3 反向傳播 (Back Propagation)
8.4 規劃隱藏層與各層神經元的數量
8.5 範例：建構多層神經網路
8.6 總結

Ch09 改善神經網路的訓練成效
9.1 權重初始化 (Weight Initialization)
9.2 解決梯度不穩定的問題
9.3 避免過度配適 (Overfitting) 的技巧
9.4 使用各種優化器 (Optimizer)
9.5 實作：用 tf.Keras 建構深度神經網路
9.6 改試試迴歸 (Regression) 範例
9.7 用 TensorBoard 視覺化判讀訓練結果
9.8 總結

Part03 深度學習的進階技術

Ch10 機器視覺實戰演練 - CNN (Convolutional Neural Network)
10.1 卷積神經網路 (CNN)
10.2 池化層 (Pooling Layer)
10.3 CNN 實作範例 (用 tf.Keras 重現 LeNet-5 經典架構)
10.4 進階的 CNN 技術 (用 tf.Keras 重現 AlexNet 與 VGGNet 架構)
10.5 殘差神經網路 (Residual Network)
10.6 機器視覺的各種應用
10.7 總結

Ch11 自然語言處理實戰演練 (一)：資料預處理、建立詞向量空間
11.1 自然語言資料的預處理
11.2 用 word2vec 建立詞向量空間
11.3 總結

Ch12 自然語言處理實戰演練 (二)：用密集神經網路、CNN 建立 NLP 模型
12.1 前置作業
12.2 進行簡單的資料預處理
12.3 用密集神經網路區分正評、負評
12.4 用 CNN 模型區分正評、負評
12.5 總結

Ch13 自然語言處理實戰演練 (三)：RNN 循環神經網路
13.1 RNN 循環神經網路
13.2 LSTM (長短期記憶神經網路)
13.3 雙向 LSTM (Bi-LSTMs)
13.4 以「函數式 API」建構非序列式 NLP 模型
13.5 總結

Ch14 藝術生成實戰演練 - GAN (Generative Adversarial Network)
14.1 GAN 的基本概念
14.2 《限時塗鴉！》資料集
14.3 建構鑑別器 (Discriminator) 神經網路
14.4 建構生成器 (Generator) 神經網路
14.5 結合生成器與鑑別器, 建構對抗式生成網路
14.6 訓練 GAN
14.7 總結

Ch15 遊戲對局實戰演練 - DRL (Deep Reinforcement Learning)、DQN (Deep Q Network)
15.1 強化式學習 (Reinforcement Learning) 的基本概念
15.2 DQN 的基本概念
15.3 建構 DQN 代理人
15.4 與 OpenAI Gym 環境互動
15.5 DQN 以外的代理人訓練方式
15.6 總結

Part04 AI 與你

Ch16 打造自己的深度學習專案
16.1 探索方向
16.2 晉升更高階的專案
16.3 模型建構流程建議
16.4 軟體 2.0 (Software 2.0)
16.5 通用人工智慧 (AGI) 的進展
16.6 總結

附錄 A 使用 Google 的 Colab 雲端開發環境





目錄
01 數學基礎
1.1 向量和矩陣
1.2 導數和偏導數
1.3 特徵值和特徵向量
1.4 機率分佈與隨機變數
1.5 常見機率分佈
1.6 期望、方差、協方差、相關係數
 
02 機器學習基礎
2.1 基本概念
2.2 機器學習的學習方式
2.3 分類演算法
2.4 邏輯回歸
2.5 代價函數
2.6 損失函數
2.7 梯度下降法
2.8 線性判別分析
2.9 主成分分析
2.10 模型評估
2.11 決策樹
2.12 支援向量機（SVM）
2.13 貝氏分類器
2.14 EM 演算法
2.15 降維和分群
 
03 深度學習基礎
3.1 基本概念
3.2 神經網路計算
3.3 啟動函數
3.4 Batch Size
3.5 歸一化
3.6 參數初始化
3.7 預訓練與微調
3.8 超參數
3.9 學習率
3.10 正規化
 
04 卷積神經網路的經典網路
4.1 LeNet-5
4.2 AlexNet
4.3 ZFNet
4.4 NIN
4.5 VGGNet
4.6 GoogLeNet
4.7 ResNet
4.8 DenseNet
4.9 CNN 模型在GoogLeNet、VGGNet 或AlexNet 上調整的原因
 
05 卷積神經網路
5.1 CNN 的結構
5.2 輸入層
5.3 卷積層
5.4 啟動層
5.5 池化層
5.6 全連接層
5.7 二維卷積與3D 卷積
5.8 了解轉置卷積與棋盤效應
5.9 卷積神經網路凸顯共通性的方法
5.10 局部卷積
5.11 CNN 視覺化
5.12 卷積神經網路的最佳化及應用
 
06 循環神經網路
6.1 為什麼需要RNN
6.2 圖解RNN 基本結構
6.3 RNN 的性質
6.4 RNN 的反向傳播
6.5 長短期記憶網路（LSTM）
6.6 常見的RNN 結構上的擴充和改進
6.7 RNN 在NLP 中的典型應用舉例
6.8 RNN 與影像領域的結合舉例
6.9 RNN 與條件隨機場的結合
 
07 生成對抗網路
7.1 GAN 的基本概念
7.2 GAN 的生成模型評價
7.3 其他常見的生成模型
7.4 GAN 的改進與最佳化
7.5 GAN 的應用：影像翻譯
7.6 GAN 的應用：文字生成
7.7 GAN 在其他領域的應用
 
08 物件偵測
8.1 基本概念
8.2 two-stage 物件偵測演算法
8.3 one-stage 物件偵測演算法
8.4 物件偵測的常用資料集
8.5 物件偵測常用標記工具
 
09 影像分割
9.1 常見的影像分割演算法
9.2 FCN
9.3 U-Net
9.4 U-Net++
9.5 SegNet
9.6 LinkNet
9.7 RefineNet
9.8 PSPNet
9.9 DeepLab 系列
9.10 Mask R-CNN 作為目標分割的介紹
9.11 基於弱監督學習的影像分割
 
10 遷移學習
10.1 遷移學習基礎知識
10.2 遷移學習的研究領域
10.3 遷移學習的應用
10.4 遷移學習的基本方法
10.5 分佈對齊的常用方法
10.6 深度遷移學習方法
10.7 遷移學習研究前端
 
11 網路架構介紹及訓練
11.1 TensorFlow
11.2 Caffe
11.3 PyTorch
11.4 常見的深度學習分散式架構
11.5 網路架設原則及訓練技巧
 
12 網路最佳化技巧
12.1 資料集和樣本最佳化
12.2 資料不符合問題
12.3 網路建構和初始化
12.4 特徵選擇
12.5 梯度消失和梯度爆炸
12.6 評價指標
12.7 模型和系統最佳化
 
13 超參數調整
13.1 超參數的概念
13.2 網路訓練中的超參數調整策略
13.3 合理使用預訓練網路
13.4 自動化超參數搜尋方法
13.5 自動機器學習AutoML
 
14 模型壓縮、加速和行動端部署
14.1 模型壓縮
14.2 為什麼需要模型壓縮和加速
14.3 模型壓縮方法
14.4 網路壓縮的未來研究方向
14.5 模型最佳化加速方法
14.6 如何選擇壓縮和加速方法
14.7 高效CNN 網路設計的準則
14.8 常用的輕量級網路
14.9 現有的行動端開放原始碼架構及其特點
14.10 行動端開放原始碼架構部署











# 英文自然語言處理的經典工具 NLTK
https://clay-atlas.com/blog/2019/07/30/nlp-python-cn-nltk-kit/

# 嵌入影片
* 不可最大
<iframe src="https://www.youtube.com/embed/g4scxhUTifM?"></iframe>

* 可最大
<iframe width="600" height="480" src="https://www.youtube.com/embed/g4scxhUTifM?start=200" frameborder="0" allowfullscreen></iframe>

* 從 Youtube 取得
<iframe width="560" height="315" src="https://www.youtube.com/embed/g4scxhUTifM" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

```{%youtube <video_URI> %}```
{%youtube<https://www.youtube.com/watch?v=MhwEaZTrmNg>%}
{%youtube <https://www.youtube.com/watch?v=MhwEaZTrmNg> %}

* https://www.youtube.com/embed/q1KZvATQ7Sk?參數1=值&參數2=值&參數3=值

* 靜音 影片網址加上參數 mute=1 即可開啟自動播放功能。
https://www.youtube.com/embed/q1KZvATQ7Sk?mute=1

* 自動播放 影片網址加上參數 autoplay=1 即可開啟自動播放功能。
https://www.youtube.com/embed/q1KZvATQ7Sk?autoplay=1

* 自動輪播 loop=1&playlist=影片ID。
https://www.youtube.com/embed/q1KZvATQ7Sk?loop=1&playlist=q1KZvATQ7Sk

* 開始與結束時間 開始start=秒數，end=秒數 可設定結束時間，兩者可單獨使用或一起使用，以下範例是從開始 1 分鐘播放到第 2 分鐘結束
https://www.youtube.com/embed/q1KZvATQ7Sk?start=60&end=120

* 關閉相關影片推薦 
https://www.youtube.com/embed/q1KZvATQ7Sk?rel=0

* 該影片從第1分鐘到第2分鐘一直重播：
https://www.youtube.com/embed/q1KZvATQ7Sk?feature=oembed&mute=1&autoplay=1&loop=1&playlist=q1KZvATQ7Sk&start=60&end=120




[MarkDown語法大全](https://hackmd.io/@eMP9zQQ0Qt6I8Uqp2Vqy6w/SyiOheL5N/%2FBVqowKshRH246Q7UDyodFA)

[顯示連結名稱](https://google.com "滑鼠移至游標顯示")
<https://google.com>

# 環境
* Anaconda (Jupyter Notebook)
    https://jupyter.org/install
* VScode
    https://code.visualstudio.com/docs/setup/windows
* Google Colaboratory 
    https://colab.research.google.com/
* QT
    https://doc.qt.io/qt-5/gettingstarted.html
* MicroPython
    https://micropython.org/download/
* Thonny
    https://thonny.org/
* Sublime Text
    https://www.sublimetext.com/download
* PyCharm
    https://pygame.hackersir.org/Lessons/01/PyCharm_install.html
* git
    https://github.com/ableshih/Python/blob/main/Draw.ipynb

# 安裝


# 套件 pip
https://pypi.org/

* pip install numpy
* pip install opencv-python
* 
* python.exe -m pip install --upgrade pip
* pip install --upgrade pip --user
* 
* Vscode install Jupyter 

1. pip安裝包升級
pip install --upgrade pip
2. 列出已安裝過的library
pip freeze pip list
3. 解除已安裝的library
pip uninstall
4. 升級library
pip install -U <library名稱>
pip install <library名稱>==版本 #指定版本安裝
5. 顯示libray所在路徑
pip show -f <library名稱>
6. 查詢可升級的包
pip list -o
7. 升級所有library資料
conda update --all
8. 將pakeage指定安裝python3底下
pip3 install <library名稱>



```
pip install windows 一鍵安裝大量library方法

獲取當前環境的所有套件，存成 Text 文字檔
pip freeze > requirements.txt

安裝 requirements.txt 所有套件
pip install -r requirements.txt

產生維護升級用的Text 文字檔
pip freeze > requirements-update.txt

升級維護用的Text 文字檔
pip install -r requirements-to-freeze.txt --upgrade

使用pip 一次安裝多個 library (空一格)
pip install pillow pymysql jieba 
```

## 5.查看目前安裝過软件包清單：
pip list
* python.exe -m pip list
* python.exe -m pip list
```
Jupyter Extension for Visual Studio Code
1. win11 VScode 安裝 Jupyter v2021.10.1101450599
2. Ctrl + Shift + P
3. >Jupyter: Create New Jupyter Notebook

To create a new notebook open the command palette (Windows: Ctrl + Shift + P, macOS: Command + Shift + P) and select the command "Jupyter: Create New Blank Notebook"
```
## 1.安裝套件： 可以將 flask 換成任何想安裝的 Python 套件
$ pip install flask

## 安装三種方法
```
pip install SomePackage              # 最新版本
pip install SomePackage==1.0.4       # 指定版本
pip install 'SomePackage>=1.0.4'     # 最小版本
pip install Django -i https://pypi.tuna.tsinghua.edu.cn/simple
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple pip -U
pip install Django==3.0.6 -i https://pypi.tuna.tsinghua.edu.cn/simple


pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
如果您到 pip 默认源的网络连接较差，临时使用本镜像站来升级 pip：


注意事项
如果 Python2 和 Python3 同时有 pip，则使用方法如下：
Python2：
python2 -m pip install XXX

Python3:
python3 -m pip install XXX
```

## 2.升级更新套件：
    ** pip install -U flask
    ** pip install -U pip
    ** pip install pip -U

## 3.移除安裝過的套件：
    ** pip uninstall flask

## 4.安裝並且指定套件版本：
$ pip install -v flask==1.0 



## 查看可升级的包
pip list -o

## 1. pip 安裝 requirements.txt 內的清單：
$ pip install -r requirements.txt 

### 2. 將安裝過的套件建立成 requirements.txt 文件清單：
$ pip freeze > requirements.txt

## pip 升级
pip install --upgrade SomePackage
升级指定的包，通过使用==, >=, <=, >, < 来指定一个版本号。

如果这个升级命令出现问题 ，可以使用以下命令：
sudo easy_install --upgrade pip
* Linux 或 macOS
    pip install --upgrade pip    # python2.x
    pip3 install --upgrade pip   # python3.x
* Windows 平台升级：
    python -m pip install -U pip   # python2.x
    python -m pip3 install -U pip    # python3.x

## 显示版本和路径
pip --version     # Python2.x 版本命令
pip3 --version    # Python3.x 版本命令

## 获取帮助
pip --help

## 卸载包
pip uninstall SomePackage
我们也可以轻易地通过以下的命令来移除软件包：
pip uninstall some-package-name
例如我们移除 numpy 包：
pip uninstall numpy

## 搜索包
pip search SomePackage

## 显示安装包信息
pip show 

## 查看指定包的详细信息
pip show -f SomePackage

# python thread 多線程範例教學
http://python-learnnotebook.blogspot.com/2018/11/pyhton-thread.html

導入多進程library
```python=
from threading import Thread
import time
```
定義好要執行的程式區塊
```python=
def timer(name,delay,times):
    print("計時器: "+ name + "開始")
    while times > 0:
        time.sleep(delay)
        print(name + ": " + str(time.ctime(time.time())))
        times -= 1
    print("計時器: " + name + "完成")
```
執行多線程
```python=
def Main():
    t1 = Thread(target=timer,args=("程式1",1,5))
    t2 = Thread(target=timer,args=("程式2",2,5))
    #程式開始
    t1.start()
    t2.start()
    print("\n程式開始")
    #程式結束
    t1.join() # join() 等待程式自然結束或拋出Error
    t2.join()
    print("\n程式結束")

```
# 問題
```
* 由於要求 X Window，你的工作階段已停止運作。Colab 不支援 X Window System。
* ModuleNotFoundError: No module named 'cv2'
    * pip install opencv-python
* ModuleNotFoundError: No module named 'matplotlib'
    * pip install matplotlib
* ModuleNotFoundError: No module named 'pandas'
    * pip install pandas
* ModuleNotFoundError: No module named 'seaborn'
    * pip install seaborn
* ModuleNotFoundError: No module named 'vispy'
    * pip install --upgrade vispy
* ModuleNotFoundError: No module named 'pygame'
    * pip install pygame

* ModuleNotFoundError: No module named 'PyQt5'
    * pip install sip
    * pip install PyQt5
    
ModuleNotFoundError: No module named 'youtube_dl'
pip install --upgrade youtube-dl
```

# UnicodeDecodeError

## 錯誤回報案例
```
Traceback (most recent call last):
  File ".\main.py", line 4, in <module>
    line = f.read()
UnicodeDecodeError: 'cp950' codec can't decode byte 0xe8 in position 7: illegal multibyte sequence
```
## 錯誤程式碼
```python
import re

f = open("1.txt","r")  #注意此行
line = f.read()
print(line)
```
## 修改後程式碼
在 open() 裡加上 encoding="utf-8" 即可解決。

```python
import re

f = open("1.txt","r",encoding="utf-8")  #注意此行
line = f.read()
print(line)
```

# 編碼
```python=
import sys

print(sys.getdefaultencoding())     # 印出目前系統編碼
# utf-8

s = '你好'
s_to_unicode = s.encode('utf-8').decode('utf-8')
print(s_to_unicode)
# 你好

s = '你好2'
s_to_unicode = s.encode('utf-8')  
print(s_to_unicode)
# b'\xe4\xbd\xa0\xe5\xa5\xbd2'

a = "\x3cdiv\x3e"
print (a)
# <div>

a = "\\x3cdiv\\x3e" 
print (a)
# \x3cdiv\x3e

a = rb"\x3cdiv\x3e"
a.decode('unicode_escape')
print (a)
# b'\\x3cdiv\\x3e'

a = b"\x3cdiv\x3e"
a.decode('unicode_escape')
print (a)
# b'<div>'

a = b"\x3cdiv\x3e"
a.decode('ascii')
print (a)
# b'<div>'

b = a.decode("ascii")
print (b)
# <div>

s = '你好1'
s_to_unicode = s.decode(encoding='utf-8')  
print(s_to_unicode)
# Traceback (most recent call last):
#   File "c:\Users\able_\Desktop\PY\h.py", line 12, in <module>
#     s_to_unicode = s.decode(encoding='utf-8')
# AttributeError: 'str' object has no attribute 'decode'
```

# Pygame游戏开发
https://www.92python.com/begin/Pygame/

# 資源
* Python 3 教程 
https://www.runoob.com/python3/python3-tutorial.html
* Python基礎教程 
https://www.runoob.com/python/python-tutorial.html
* Python 100例 
https://www.runoob.com/python/python-100-examples.html
* 小馬技術 
https://www.youtube.com/channel/UCazV3A3_1-Mtd6E_auw_ifg/videos
* 零度解說 -
https://www.youtube.com/c/%E9%9B%B6%E5%BA%A6%E8%A7%A3%E8%AF%B4/videos
* GrandmaCan -我阿嬤都會 
https://www.youtube.com/c/GrandmaCan%E6%88%91%E9%98%BF%E5%AC%A4%E9%83%BD%E6%9C%83/videos
* Gamma Ray 說話怪怪的 
https://www.youtube.com/c/GammaRay%E8%BB%9F%E9%AB%94%E5%B7%A5%E4%BD%9C%E5%AE%A4/videos
* 彭彭的課程 
https://www.youtube.com/c/%E5%BD%AD%E5%BD%AD%E7%9A%84%E8%AA%B2%E7%A8%8B/videos
* 補根課程 
https://www.youtube.com/channel/UCT81jejfi3660ugmYypDozA/videos
* 30天學會Python iThome 鐵人賽 
https://ithelp.ithome.com.tw/users/20121148/ironman/2924
* 莫煩Python 
https://www.youtube.com/c/%E5%91%A8%E8%8E%AB%E7%83%A6/videos
* Python基礎教程 菜鳥教程 
https://www.runoob.com/python/python-tutorial.html
* 純淨天空 
https://vimsky.com/zh-tw/examples/list/python-all-page-1.html
* turtle --- 龜圖學
https://docs.python.org/zh-tw/3/library/turtle.html
* 標準函式庫
https://docs.python.org/zh-tw/3/library/index.html
* Python 3.11.0a0 說明文件
https://docs.python.org/zh-tw
* 初學總整理 第8講：Matplotlib套件
https://blog.happycoding.today/pythonbeginner-ep8/
* Python Matplotlib 貼士
https://www.delftstack.com/zh-tw/howto/matplotlib/
* 使用Python Tkinter 模組
https://www.rs-online.com/designspark/python-tkinter-cn
* turtle
https://docs.python.org/3/library/turtle.html
* 唐元亮
http://yltang.net/tutorial/python/0/

https://docs.python.org/zh-tw/3/tutorial/index.html
* Hello Py
https://bookdown.org/tonykuoyj/hello-py/section-4.html
* 學習如何使用 Python 程式語言
https://chusiang.gitbooks.io/using-python/content/Installation.html

```
# 語法
## 運算式
## 標準數據類型
## Python3 中有六個標準的數據類型：
```
# 繪圖
## pygame

### KEYDOWN
### QUIT
### KEYUP
### MOUSEMOTION
### MOUSEBUTTONDOWN


# 常用函數
## Number（數字）
```
>>> 2 + 2
4
>>> 50 - 5*6
20
>>> (50 - 5*6) / 4
5.0
>>> 8 / 5  # 总是返回一个浮点数
1.6
```

## String（字符串）
```
var1 = 'Hello World!'
var2 = "Runoob"
 
print ("var1[0]: ", var1[0])
print ("var2[1:5]: ", var2[1:5])
```
## List（列表）
```
list = ['red', 'green', 'blue', 'yellow', 'white', 'black']
print( list[0] )
print( list[1] )
print( list[2] )
```

## Tuple（元組）
```
#!/usr/bin/python3
 
tup1 = (12, 34.56)
tup2 = ('abc', 'xyz')
 
# 以下修改元组元素操作是非法的。
# tup1[0] = 100
 
# 创建一个新的元组
tup3 = tup1 + tup2
print (tup3)

以上实例输出结果：
(12, 34.56, 'abc', 'xyz')
```

## Set（集合）
```
>>> thisset = set(("Google", "Runoob", "Taobao"))
>>> len(thisset)
3

thisset = set(("Google", "Runoob", "Taobao", "Facebook"))
x = thisset.pop()

print(x)
输出结果：

$ python3 test.py 
Runoob
```
## Dictionary（字典）
```
tinydict = {'Name': 'Runoob', 'Age': 7, 'Class': 'First'}
 
print ("tinydict['Name']: ", tinydict['Name'])
print ("tinydict['Age']: ", tinydict['Age'])
以上实例输出结果：

tinydict['Name']:  Runoob
tinydict['Age']:  7
```


# Python3 註釋
* ### 多行註釋用三個單引號'''或者三個雙引號"""將註釋括起來，例如:

## 1、單引號（'''）
```
#!/usr/bin/python3 
'''
這是多行註釋，用三個單引號這是多行註釋，用三個單引號這是多行註釋，用三個單引號
''' 
print ( " Hello, World! " )
```

## 2、雙引號（"""）
```
#!/usr/bin/python3 
"""
這是多行註釋，用三個雙引號這是多行註釋，用三個雙引號這是多行註釋，用三個雙引號
""" 
print ( " Hello, World! " )
```
```
# 第一个注释
# 第二个注释
 
'''
第三注释
第四注释
'''
 
"""
第五注释
第六注释
"""
```

## if
```
a=2
if(a>3):
    print('if',a)
elif(a==3):
    print('elif',a)
else:
    print('else',a)
```

## def
```
def HH():
    print('HH')

HH()
```
```
def HH(a):
    print(a)

HH('HH')
```
```
def HH(a,b):
    print(a+b)

HH(6,10)
```
```
def HH(a,b):
    return a+b

print(HH(6,10))
```
```
def HH(*a):
    print(*a)

HH(1)
HH(1,2)
HH(1,2,3)
HH(1,2,3,4)
HH(1,2,3,4,5)
```
## for
```
for a in range(0,5):
    print('AA')
```
## while
```
a=5
while(a<5):
    print('AA')
```
## break
```
for a in range(0,10):
    if(a==6):
        break
    print(a)
```
## continue
```
for a in range(0,10):
    if(a==6):
        continue
    print(a)
```
## class
```
class HH():
    def __init__(self):
        AA=5
        print('xx',AA)

CC=HH()
```
## try
```
try:
    a=10/0
    print(a)
except:
    print('HH')
```
## finally
```
try:
    a=10/0
    print(a)
except:
    print('HH')
finally:
    print('AA')
```
## import
```
import time
time.sleep(3)
```
## GUI
### Tk
```
from tkinter import *
a=Tk()
a.mainloop()
```
### Button
```
from tkinter import *
abc=Tk()
button=Button(abc,text="Hello")
button.pack()
mainloop()
```
## 判斷式
```
==	等於 - 比較對像是否相等	(a == b) 返回假。
!=	不等於 - 比較兩個對像是否不相等	(a != b) 返回真。
<>	不等於 - 比較兩個對像不相等。	(a <> b) 返回 true。這個相似性 != 。
>	大於 - 返回x是否大於y	(a > b) 返回假。
<	小於 - 返回x是否小於。所有比較相同1返回表示真，返回0表示假。	(a < b) 返回真。
>=	大於等於 - 返回x是否大於等於y。	(a >= b) 返回假。
<=	小於等於 - 返回 x 小於等於 y。	(a <= b) 返回真。
```

## 賦值衝突
```
後果變量a為10，變量b為20：

相見	描述	實例
=	簡單的擊中	c = a + b a + b 的運算結果將為 c
+=	加法撞擊	c += a 絕對於 c = c + a
-=	減法命中	c -= a 嚴格於 c = c - a
*=	乘法碰撞	c *= a 嚴格於 c = c * a
/=	除法啟動	c /= a 嚴格於 c = c / a
%=	取模觸發	c %= a 完全於 c = c % a
**=	抗拒對抗	c **= a 真的於 c = c ** a
//=	取整除引發	c //= a 嚴格於 c = c // a
```

```
&	更多位與一位：參與操作的兩個值，如果兩個位都為1，則該位的結果為1，否則為0	(a & b) 輸出結果 12 ，二進制解釋： 0000 1100

|	按位或一致：只要對應的二個二進位有一個為1時，結果位就為1。	(a | b) 輸出結果 61 ，雙解釋： 0011 1101

^	兩個異位或相反：當兩個的二進位相異時，結果為1	(a ^ b) 輸出結果 49 ，雙解釋： 0011 0001

~	按位取反矛盾：對數據的二進制位取反，把1變成0，把0變成1。~x奇異-x-1	(~a ) 輸出結果 -61 ，二進制解釋： 1100 011，在一個有符號二進制數的補碼形式。

<<	左移動：左移動手術數的各二進全部左移等位，<<的數字了移動的右邊位，高位由低位指定，低位補0。	a << 2 輸出結果 240 ，二進制解釋： 1111 0000

>>	移動右邊：把“>>”二食位的手柄數的進進全部右移部分，>>右邊的數字指定了移動的手指	a >> 2 輸出結果 15 ，二進制解釋： 0000 1111
```

## 變數、運算
```
#!/usr/bin/python
# -*- coding: UTF-8 -*-
counter = 100 # 赋值整型变量
miles = 1000.0 # 浮点型
name = "John" # 字符串
print counter
print miles
print name
```

```
Numbers（數字）
String（字符串）
List（列表）
Tuple（元組）
Dictionary（字典）
```

```
數字類型：
int（有符號整型）
long（長整型，也可以代表八進制和十六進制）
float（浮點型）
complex（複數）
```

```
+　　 加 - 兩個對象相加							　　　　　　　　　　	a + b 輸出結果 30

--　　- 得到負數一個減少一個數				　　	　　　　　　	a - b 輸出結果 -10

*　　 乘 - 兩個數相乘來返回一個被重複若干次的字符串	　　a * b 輸出結果 200

/　　 除 - x除以y									　　	　　　　　　　　b / a 輸出結果 2

%　　取模 - 返回除法的餘數				　　		　　　　　　	b % a 輸出結果 0

**　　冪 - 返回x的y次冪							　　　　　　　　	a**b 為10的20次方，輸出結果100000000000000000000

//　　取整除 - 返回商的部分除掉（取整）		　　　　		>>> 9 //2 4 >>> - 9 //2 - 5 


```

## 数学函数
```
abs(x)	返回数字的绝对值，如abs(-10) 返回 10
ceil(x)	返回数字的上入整数，如math.ceil(4.1) 返回 5
cmp(x, y)	如果 x < y 返回 -1, 如果 x == y 返回 0, 如果 x > y 返回 1
exp(x)	返回e的x次幂(ex),如math.exp(1) 返回2.718281828459045
fabs(x)	返回数字的绝对值，如math.fabs(-10) 返回10.0
floor(x)	返回数字的下舍整数，如math.floor(4.9)返回 4
log(x)	如math.log(math.e)返回1.0,math.log(100,10)返回2.0
log10(x)	返回以10为基数的x的对数，如math.log10(100)返回 2.0
max(x1, x2,...)	返回给定参数的最大值，参数可以为序列。
min(x1, x2,...)	返回给定参数的最小值，参数可以为序列。
modf(x)	返回x的整数部分与小数部分，两部分的数值符号与x相同，整数部分以浮点型表示。
pow(x, y)	x**y 运算后的值。
round(x [,n])	返回浮点数x的四舍五入值，如给出n值，则代表舍入到小数点后的位数。
sqrt(x)	返回数字x的平方根
```

## 随机数函数
```
choice(seq)	从序列的元素中随机挑选一个元素，比如random.choice(range(10))，从0到9中随机挑选一个整数。

randrange ([start,] stop [,step])	从指定范围内，按指定基数递增的集合中获取一个随机数，基数默认值为 1

random()	随机生成下一个实数，它在[0,1)范围内。

seed([x])	改变随机数生成器的种子seed。如果你不了解其原理，你不必特别去设定seed，Python会帮你选择seed。

shuffle(lst)	将序列的所有元素随机排序

uniform(x, y)	随机生成下一个实数，它在[x,y]范围内。
```

## 三角函数
```
函数	描述
acos(x)	返回x的反余弦弧度值。
asin(x)	返回x的反正弦弧度值。
atan(x)	返回x的反正切弧度值。
atan2(y, x)	返回给定的 X 及 Y 坐标值的反正切值。
cos(x)	返回x的弧度的余弦值。
hypot(x, y)	返回欧几里德范数 sqrt(x*x + y*y)。
sin(x)	返回的x弧度的正弦值。
tan(x)	返回x弧度的正切值。
degrees(x)	将弧度转换为角度,如degrees(math.pi/2) ， 返回90.0
radians(x)	将角度转换为弧度
```

## 数学常量
```
pi	数学常量 pi（圆周率，一般以π来表示）
e	数学常量 e，e即自然常数（自然常数）。
```

## 列表(List)
```
列表(List)

序列是Python中最基本的数据结构。序列中的每个元素都分配一个数字 - 它的位置，或索引，第一个索引是0，第二个索引是1，依此类推。

Python有6个序列的内置类型，但最常见的是列表和元组。
序列都可以进行的操作包括索引，切片，加，乘，检查成员。
此外，Python已经内置确定序列的长度以及确定最大和最小的元素的方法。
列表是最常用的Python数据类型，它可以作为一个方括号内的逗号分隔值出现。
列表的数据项不需要具有相同的类型
创建一个列表，只要把逗号分隔的不同的数据项使用方括号括起来即可。如下所示：

list1 = ['physics', 'chemistry', 1997, 2000]
list2 = [1, 2, 3, 4, 5 ]
list3 = ["a", "b", "c", "d"]
```
```
### 類別
#### 類別繼承
#### 類別封裝
### 圖形使用者介面設計
### 正規表達式
### Class類別
```

# 支援中文編碼
```
#!/usr/bin/python
# -*- coding: utf-8 -*-
# 中文註解

print("Hello, world.")
```

# 内置函数
```
内置函数		
abs()	dict()	help()	min()	setattr()
all()	dir()	hex()	next()	slice()
any()	divmod()	id()	object()	sorted()
ascii()	enumerate()	input()	oct()	staticmethod()
bin()	eval()	int()	open()	str()
bool()	exec()	isinstance()	ord()	sum()
bytearray()	filter()	issubclass()	pow()	super()
bytes()	float()	iter()	print()	tuple()
callable()	format()	len()	property()	type()
chr()	frozenset()	list()	range()	vars()
classmethod()	getattr()	locals()	repr()	zip()
compile()	globals()	map()	reversed()	__import__()
complex()	hasattr()	max()	round()	 
delattr()	hash()	memoryview()	set()
```

# Python3 基本數據類型
```
Python 中的變量不需要聲明。每個變量在使用前都必須賦值，變量賦值以後該變量才會被創建。
在Python 中，變量就是變量，它沒有類型，我們所說的"類型"是變量所指的內存中對象的類型。
等號（=）用來給變量賦值。
等號（=）運算符左邊是一個變量名,等號（=）運算符右邊是存儲在變量中的值。例如：

實例(Python 3.0+)
#!/usr/bin/python3

counter = 100          # 整型變量
miles   = 1000.0       # 浮點型變量
name     = "runoob"     # 字符串

print ( counter )
print ( miles )
print ( name )
```

# Python3 实例
https://www.runoob.com/python3/python3-examples.html
```
以下实例在 Python3.4.3 版本下测试通过：
Python Hello World 实例
Python 数字求和
Python 平方根
Python 二次方程
Python 计算三角形的面积
Python 计算圆的面积
Python 随机数生成
Python 摄氏温度转华氏温度
Python 交换变量
Python if 语句
Python 判断字符串是否为数字
Python 判断奇数偶数
Python 判断闰年
Python 获取最大值函数
Python 质数判断
Python 输出指定范围内的素数
Python 阶乘实例
Python 九九乘法表
Python 斐波那契数列
Python 阿姆斯特朗数
Python 十进制转二进制、八进制、十六进制
Python ASCII码与字符相互转换
Python 最大公约数算法
Python 最小公倍数算法
Python 简单计算器实现
Python 生成日历
Python 使用递归斐波那契数列
Python 文件 IO
Python 字符串判断
Python 字符串大小写转换
Python 计算每个月天数
Python 获取昨天日期
Python list 常用操作
Python 约瑟夫生者死者小游戏
Python 五人分鱼
Python 实现秒表功能
Python 计算 n 个自然数的立方和
Python 计算数组元素之和
Python 数组翻转指定个数的元素
Python 将列表中的头尾两个元素对调
Python 将列表中的指定位置的两个元素对调
Python 翻转列表
Python 判断元素是否在列表中存在
Python 清空列表
Python 复制列表
Python 计算元素在列表中出现的次数
Python 计算列表元素之和
Python 计算列表元素之积
Python 查找列表中最小元素
Python 查找列表中最大元素
Python 移除字符串中的指定位置字符
Python 判断字符串是否存在子字符串
Python 判断字符串长度
Python 使用正则表达式提取字符串中的 URL
Python 将字符串作为代码执行
Python 字符串翻转
Python 对字符串切片及翻转
Python 按键(key)或值(value)对字典进行排序
Python 计算字典值之和
Python 移除字典点键值(key/value)对
Python 合并字典
Python 将字符串的时间转换为时间戳
Python 获取几天前的时间
Python 将时间戳转换为指定格式日期
Python 打印自己设计的字体
Python 二分查找
Python 线性查找
Python 插入排序
Python 快速排序
Python 选择排序
Python 冒泡排序
Python 归并排序
Python 堆排序
Python 计数排序
Python 希尔排序
Python 拓扑排序
```








# Python 3
```
Python 3 教程 
 Python3 教程
Python3 简介
Python3 环境搭建
Python3 VScode
Python3 基础语法
Python3 基本数据类型
Python3 解释器
Python3 注释
Python3 运算符
Python3 数字(Number)
Python3 字符串
Python3 列表
Python3 元组
Python3 字典
Python3 集合
Python3 编程第一步
Python3 条件控制
Python3 循环语句
Python3 迭代器与生成器
Python3 函数
Python3 数据结构
Python3 模块
Python3 输入和输出
Python3 File
Python3 OS
Python3 错误和异常
Python3 面向对象
Python3 命名空间/作用域
Python3 标准库概览
Python3 实例
Python 测验

Python3 高级教程
Python3 正则表达式
Python3 CGI编程
Python3 MySQL(mysql-connector)
Python3 MySQL(PyMySQL)
Python3 网络编程
Python3 SMTP发送邮件
Python3 多线程
Python3 XML 解析
Python3 JSON
Python3 日期和时间
Python3 内置函数
Python3 MongoDB
Python3 urllib
Python uWSGI 安装配置
Python3 pip
Python 基础教程
Python 简介
Python 环境搭建
Python 中文编码
Python 基础语法
Python 变量类型
Python 运算符
Python 条件语句
Python 循环语句
Python While 循环语句
Python for 循环语句
Python 循环嵌套
Python break 语句
Python continue 语句
Python pass 语句
Python Number(数字)
Python 字符串
Python 列表(List)
Python 元组
Python 字典(Dictionary)
Python 日期和时间
Python 函数
Python 模块
Python 文件I/O
Python File 方法
Python 异常处理
Python OS 文件/目录方法
Python 内置函数

Python 高级教程
Python 面向对象
Python 正则表达式
Python CGI 编程
Python MySQL
Python 网络编程
Python SMTP
Python 多线程
Python XML 解析
Python GUI 编程(Tkinter)
Python2.x 与 3​​.x 版本区别
Python IDE
Python JSON
Python 100例
Python 测验
```
