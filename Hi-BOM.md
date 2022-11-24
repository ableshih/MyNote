# **AI 專題：Hi-BOM**


# 序
## [三人分工合作](#三人分工合作1)
## [設計規劃初終](#設計規劃初終1)

    
    
        
    
    


* 四大類 
  * 猜遠近：各景點 台大校園 自來水廠 
  * 猜交通方式：車 公車 機車 
  * 猜年齡男女： 
  * 猜喜好：吃喝玩樂 
    * 圖片 一、食(吃的喝的)二、衣(男裝女裝童裝)三、行(廁所)四、公共空間(學校公園) 
    * 照片怎麼分? 如 四個目錄 隨機選照片 
    * 吃的吃的 喝的吃的... 
* 機器學習 
  * 一頁四張照 選四次 就如鳶尾花的長寬特徵 得到一個類別 縮圖 
  * 用 csv 造出 100 筆數據 
  * 100 筆數據 訓練 
  * 訓練保存 
* 結果 
  * 顯示 GPS 座標 圖片 
* 廣告 
  * 圖片 折扣 

```













```
# [第一棒 照片 檔名編碼原則](#檔名編碼原則) 
## [台灣縣市與行政區](#檔名編碼原則)



# [第二棒 UI 操作 UI 程式碼] 
## [Tkinter GUI](#Tkinter)



# [第三棒 AI 程式] 
## [AI 程式流程](#取檔流程)

```













```

# 三人分工合作

一、照片 收集過程 城市 如 台北 區 中山萬華 各地特色

二、AI 程式碼 三個特徵 一個分類 訓練過程取參數 過程

三、實際操作 自設立埸 先選 與台北有關 大安區有關 學校有關 顯示台科大







# 設計規劃初終

就如：算命，算不準也沒關係

就是：打開程式，選一選，顯示一個結果。結束

作一個可以動的有可能

真的要百分之百作出來，是不可能。

```













```

# 檔名編碼原則

每張照片，會作編號 編號作為檔名 

A0101001
A(縣市)01(行政區)01(景點分類)001(店家編號)


第一碼：城市 A-Z
第二碼：城市行政區 1-500
第三碼：類別 (風景、學校) 1-50

A00101 就等於 台北市、中正區、學校

用正規表達式 取城市碼 亂數抽取四張照片 顯示

當選第一張圖會用 取第一碼 存給變數一

判斷變數一是那個城市在從那譬城市的行政區 亂數產生四張照片

當選第二張圖會用 正規表達式 取第二碼 存給變數二

判斷變數二是那個城市行政區 亂數產生四張照片

當選第三張圖會用 正規表達式 取第三碼 存給變數三


在將三個變數存成陣列

# 台灣縣市與行政區

https://zh.wikipedia.org/zh-tw/%E8%87%BA%E7%81%A3%E8%A1%8C%E6%94%BF%E5%8D%80%E5%8A%83

台灣有二十個縣市 358 行政區

1	臺北市	12區		
2	新北市	29區		
3	桃園市	13區		
4	臺中市	29區		
5	臺南市	37區		
6	高雄市	38區		
7	基隆市	7區			
8	新竹市	3區			
9	嘉義市	2區			
10	新竹縣	1市3鎮9鄉	
11	苗栗縣	2市5鎮11鄉	
12	彰化縣	2市6鎮18鄉	
13	南投縣	1市4鎮8鄉	
14	雲林縣	1市5鎮14鄉	
15	嘉義縣	2市2鎮14鄉	
16	屏東縣	1市3鎮29鄉	
17	宜蘭縣	1市3鎮8鄉	
18	花蓮縣	1市2鎮10鄉	
19	臺東縣	1市2鎮13鄉	
20	澎湖縣	1市5鄉		

臺北市		12區
中正區、大同區、中山區、松山區、大安區、
萬華區、信義區、士林區、北投區、內湖區、
南港區、文山區

新北市		29區
板橋區、中和區、永和區、土城區、三峽區、
鶯歌區、樹林區、新莊區、三重區、蘆洲區、
五股區、泰山區、林口區、八里區、淡水區、
三芝區、石門區、金山區、萬里區、汐止區、
瑞芳區、貢寮區、平溪區、雙溪區、新店區、
深坑區、石碇區、坪林區、烏來區

桃園市		13區 **(這個有點亂，還沒很清楚)**
北桃園	桃園區	市中區、中路區、埔子區、會稽區、大樹林區
龜山區	龜山區、龍壽區、南崁區、林口區
八德區	八塊厝/下庄仔地區、霄裡地區、茄苳溪區、大湳區
大溪區	河東區、河西區
蘆竹區	南崁地區、坑子地區、大竹地區
大園區	大園/橫山/田心子/照鏡地區、雙溪口/許厝港/內海墘地區、埔心地區、竹圍地區
南桃園	中壢區	區中心、龍岡、內壢、大西區（青埔、大崙、過嶺）
龍潭區	銅鑼圈區、龍潭坡區、三坑子區
平鎮區	北勢區、社子區、平鎮/南勢區、東勢區、宋屋區
楊梅區	楊梅區、埔心區、富岡區、高山頂區
新屋區	新屋區、永安區、大坡區、頭洲區
觀音區	草漯區、新坡區、觀音區
原住民區	復興區	南復興、北復興、巴陵區

臺中市		29區
中區、東區、南區、西區、北區、
北屯區、西屯區、南屯區、太平區、大里區、
霧峰區、烏日區、豐原區、后里區、石岡區、
東勢區、和平區、新社區、潭子區、大雅區、
神岡區、大肚區、沙鹿區、龍井區、梧棲區、
清水區、大甲區、外埔區、大安區

臺南市		37區
中西區、東區、南區、北區、安平區、
安南區、新營區、鹽水區、白河區、柳營區、
後壁區、東山區、麻豆區、下營區、六甲區、
官田區、大內區、佳里區、學甲區、西港區、
七股區、將軍區、北門區、新化區、善化區、
新市區、安定區、山上區、玉井區、楠西區、
南化區、左鎮區、仁德區、歸仁區、關廟區、
龍崎區、永康區、

高雄市		38區
鹽埕區、鼓山區、左營區、楠梓區、三民區、
新興區、前金區、苓雅區、前鎮區、旗津區、
小港區、鳳山區、林園區、大寮區、大樹區、
大社區、仁武區、鳥松區、岡山區、橋頭區、
燕巢區、田寮區、阿蓮區、路竹區、湖內區、
茄萣區、永安區、彌陀區、梓官區、旗山區、
美濃區、六龜區、甲仙區、杉林區、內門區、
茂林區、桃源區、那瑪夏區

基隆市		7區
中正區、七堵區、暖暖區、仁愛區、中山區、
安樂區、信義區

新竹市		3區
東區、北區、香山區

嘉義市		2區
東區、西區

新竹縣		1市3鎮9鄉
竹北市、關西鎮、新埔鎮、竹東鎮、湖口鄉、
橫山鄉、新豐鄉、芎林鄉、寶山鄉、北埔鄉、
峨眉鄉、尖石鄉、五峰鄉

苗栗縣 2市5鎮11鄉
苗栗市、頭份市、苑裡鎮、通霄鎮、竹南鎮、
後龍鎮、卓蘭鎮、大湖鄉、公館鄉、銅鑼鄉、
南莊鄉、頭屋鄉、三義鄉、西湖鄉、造橋鄉、
三灣鄉、獅潭鄉、泰安鄉
		
彰化縣	 2市6鎮18鄉
彰化市、員林市、鹿港鎮、和美鎮、北斗鎮、
溪湖鎮、田中鎮、二林鎮、線西鄉、伸港鄉、
福興鄉、秀水鄉、花壇鄉、芬園鄉、大村鄉、
埔鹽鄉、埔心鄉、永靖鄉、社頭鄉、二水鄉、
田尾鄉、埤頭鄉、芳苑鄉、大城鄉、竹塘鄉、
溪州鄉
	
南投縣	1市4鎮8鄉
南投市、埔里鎮、草屯鎮、竹山鎮、集集鎮、
名間鄉、鹿谷鄉、中寮鄉、魚池鄉、國姓鄉、
水里鄉、信義鄉、仁愛鄉
	
雲林縣	1市5鎮14鄉
斗六市、斗南鎮、虎尾鎮、西螺鎮、土庫鎮、
北港鎮、古坑鄉、大埤鄉、莿桐鄉、林內鄉、
二崙鄉、崙背鄉、麥寮鄉、東勢鄉、褒忠鄉、
臺西鄉、元長鄉、四湖鄉、口湖鄉、水林鄉、
	
嘉義縣	2市2鎮14鄉
太保市、朴子市、布袋鎮、大林鎮、民雄鄉、
溪口鄉、新港鄉、六腳鄉、東石鄉、義竹鄉、
鹿草鄉、水上鄉、中埔鄉、竹崎鄉、梅山鄉、
番路鄉、大埔鄉、阿里山鄉
	
屏東縣	1市3鎮29鄉
屏東市、潮州鎮、東港鎮、恆春鎮、萬丹鄉、
長治鄉、麟洛鄉、九如鄉、里港鄉、鹽埔鄉、
高樹鄉、萬巒鄉、內埔鄉、竹田鄉、新埤鄉、
枋寮鄉、新園鄉、崁頂鄉、林邊鄉、南州鄉、
佳冬鄉、琉球鄉、車城鄉、滿州鄉、枋山鄉、
三地門鄉、霧臺鄉、瑪家鄉、泰武鄉、來義鄉、
春日鄉、獅子鄉、牡丹鄉、
	
宜蘭縣		1市3鎮8鄉
宜蘭市、羅東鎮、蘇澳鎮、頭城鎮、礁溪鄉、
壯圍鄉、員山鄉、冬山鄉、五結鄉、三星鄉、
大同鄉、南澳鄉

花蓮縣	1市2鎮10鄉
花蓮市、鳳林鎮、玉里鎮、新城鄉、吉安鄉、
壽豐鄉、光復鄉、豐濱鄉、瑞穗鄉、富里鄉、
秀林鄉、萬榮鄉、卓溪鄉、

臺東縣	1市2鎮13鄉
臺東市、成功鎮、關山鎮、卑南鄉、大武鄉、
太麻里鄉、東河鄉、長濱鄉、鹿野鄉、池上鄉、
綠島鄉、延平鄉、海端鄉、達仁鄉、金峰鄉、
蘭嶼鄉
	
澎湖縣 1市5鄉 
馬公市、湖西鄉、白沙鄉、西嶼鄉、望安鄉、七美鄉





---
```















```
# Tkinter

圖形介面 tkinter 為 Python 內建的 GUI 程式庫 (library) ，基本使用順序如下

1. 建立 Tk 物件， Tk 物件是視窗應用程式。
2. 建立 Frame 物件， Frame 是基本的視窗。
3. 建立所需的視窗元件物件，再利用 pack() 或 grid() 方法設定視窗元件如何在視窗上顯示。
4. Tk 物件呼叫 mainloop() 方法，維持視窗在螢幕上顯示。

**視窗元件
Button        按鈕
Frame        視窗
Label        文字標籤
Text        文字方塊
Toplevel    新增視窗**


![](https://static.coderbridge.com/img/techbridge/images/kdchang/python-tkinter101/demo3.png)

```python
# -*- coding: utf-8 -*-
try:
    import Tkinter as tk
except:
    import tkinter as tk

from PIL import ImageTk ,Image
from tkinter.ttk import *

class Test():
    def __init__(self):
        print('start')

    def S1(self):
        def leave(event):
            self.M1.destroy()

        self.M1 = tk.Tk()
        self.M1.geometry('1920x1080')
        self.M1.wm_attributes('-fullscreen','true')
        self.M1.state("zoomed")
        self.M1.bind("<Escape>",leave)

        L_img1 = Image.open(r'1.png')
        img1 = ImageTk.PhotoImage(L_img1)
        lab1 = tk.Button(self.M1, padx=1, pady=1, image=img1, command = self.S2)
        lab1.place(x=0,y=0)
        self.M1.mainloop()

    def S2(self):
        def leave(event):
            self.M2.destroy()

        self.M1.destroy()
        self.M2 = tk.Tk()
        self.M2.geometry('1920x1080')
        self.M2.wm_attributes('-fullscreen','true')
        self.M2.state("zoomed")
        self.M2.bind("<Escape>",leave)

        L_img2 = Image.open(r'2.png')
        img2 = ImageTk.PhotoImage(L_img2)
        lab2 = tk.Button(self.M2, padx=1, pady=1, image=img2, command = self.S3)
        lab2.place(x=0,y=0)
        self.M2.mainloop()

    def S3(self):
        def leave(event):
            self.M3.destroy()

        self.M2.destroy()
        self.M3 = tk.Tk()
        self.M3.geometry('1920x1080')
        self.M3.wm_attributes('-fullscreen','true')
        self.M3.state("zoomed")
        self.M3.bind("<Escape>",leave)

        L_img3 = Image.open(r'3.png')
        img3 = ImageTk.PhotoImage(L_img3)
        lab3 = tk.Button(self.M3, padx=1, pady=1, image=img3, command = self.S4)
        lab3.place(x=0,y=0)
        self.M3.mainloop()

    def S4(self):
        def leave(event):
            self.M4.destroy() # 按 Esc 結束程式

        self.M3.destroy() # 關閉上一個視窗
        self.M4 = tk.Tk() # 造一個視窗
        self.M4.geometry('1920x1080')
        self.M4.wm_attributes('-fullscreen','true') # 設定成無邊框視窗
        self.M4.state("zoomed") # 最大化視窗 只能在windowns下使用
        self.M4.bind("<Escape>",leave) # Esc鍵

        L_img4 = Image.open(r'4.png') # 載入圖片 (1536, 864)
        img4 = ImageTk.PhotoImage(L_img4) # 將圖片轉成陣列
        lab4 = tk.Button(self.M4, padx=1, pady=1, image=img4, command = self.Squit) # 造一個圖片按鍵
        lab4.place(x=0,y=0) # 將 圖片按鍵 顯示
        self.M4.mainloop() # 視窗停留迴圈

    def Squit(self):
        self.M4.destroy() # 結束程式

app = Test()
app.S1()
```



```











```
# 取檔流程

要 5個變數

用正規取前一碼
亂數出四張圖
選到的第一張 取前一碼存變數A 與 4-5碼 存變數B 

用正規取前2-3碼
亂數出四張圖

選到的第二張 取前2-3碼存到變數C 與 4-5碼 存變數D

用正規取前4-5碼
亂數出四張圖

選到的第三張 取前4-5碼存到變數E

看變數 B D E 先把 景點 確定 

在看所在地 景點 選出 店家編號

### 特徵

每個縣市的行政區數量不一，最少只有二個
每個行政區的景點也各有不同

```python
#!/usr/bin/env python3
# -*- coding: utf-8 -*- #

# 10a-sklearn_train
# 18-iris_decisiontree

import pandas as pd
from sklearn.datasets import load_iris
from sklearn.model_selection import train_test_split
''' 訓練'''
# iris = load_iris() # 由 from sklearn.datasets 載入 iris 資料
# X = pd.DataFrame(iris.data) # 花萼長寬 花瓣長寬
# y = pd.DataFrame(iris.target) # 品種

# data = X
# data.to_csv('Xx666data.csv')
# data = y
# data.to_csv('yy666data.csv')

# X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, shuffle = True, random_state = 123)

iris_dataset = pd.read_csv('AI_5_X.csv', index_col=0)
# print(iris_dataset)
X = iris_dataset 

iris_datasety = pd.read_csv('AI_5_y.csv', index_col=0)
# print(iris_datasety)
y = iris_datasety 

# X = iris_le.drop(columns=['4'])
#X = iris_le.drop(columns=['1','3','4'])
#X = iris_le.drop(columns=['0','2','4'])
# y = iris_le.pop('4')

'''全隨機取值'''
# X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, shuffle = True)


'''用 123 當亂數因子取值'''
#X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.2, shuffle = True, random_state = 123) 


'''用 456 當亂數因子取值'''
X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.08, shuffle = True, random_state = 456) 


print("X_train shape: {}".format(X_train.shape))
print("X_test shape: {}".format(X_test.shape))
print("y_train shape: {}".format(y_train.shape))
print("y_test shape: {}".format(y_test.shape))

print()

print("X_train")
print(X_train)
print()

print("X_test")
print(X_test)
print()

print("y_train")
print(y_train)
print()

print("y_test")
print(y_test)
print()

from sklearn import tree
from sklearn import metrics

'''決策樹 分類器'''
clf = tree.DecisionTreeClassifier()
iris_clf = clf.fit(X_train, y_train)

'''預測'''
y_test_predicted = iris_clf.predict(X_test)
print('Predicted:', y_test_predicted)

'''準確性分數'''
accuracy = metrics.accuracy_score(y_test, y_test_predicted)
print('Score:', accuracy)
```
