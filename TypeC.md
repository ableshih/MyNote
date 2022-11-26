# Type-C

https://learn.sparkfun.com/tutorials/pro-micro-rp2040-hookup-guide?_ga=2.182211751.1236383090.1669422972-1574100486.1669422972

https://cdn.sparkfun.com/assets/4/a/6/d/6/SparkFun_Pro_Micro_RP2040_Schematic.pdf
SparkFun_Pro_Micro_RP2040_Schematic.pdf
CC1 5.1k to GND
CC2 5.1k to GND

---


https://blog.csdn.net/weixin_42005993/article/details/100046714
Rp都是5.1K電阻下地，電源供電能力的檢測與否與電阻精度相關



![](https://i.imgur.com/9v5CXRm.png)


如上圖
SINK的兩個CC引腳均通道Rd下拉到GND。
SINK通過檢測電源VBUS是否存在，來判斷Source的連接與否。
SINK通過CC引腳上拉的特性，來檢測目前的USB高速數據鏈路。
SINK可選地去檢測Rp的值，去判斷Source可提供的電流。同時管理自身的功耗，保證不超過Source提供的最大範圍。
同樣的，如果支持高級功能，通過CC引腳進行USB PD協議進行溝通實現。
DRP的CC1，CC2模型


5.配置VCONN
CC pin有CC1，CC2，當其中1 pin被用來做DFP，UFP之間的連接，另外1pin用就來提供VCONN。由圖4.5可以發現，當Cable內部將另外一個CC pin接一個下拉電阻Ra，這表示這是一條主動式Cable，需要被供電的。DFP測到Ra，便會輸出VCONN在CC pin，供電給Cable。Ra的阻抗定義為800ohm ~1200ohm。

在UFP是由CC pin上的電壓，來得知道DFP的VBUS輸出能力。比如DFP為5V/3A，它可以在CC pin上提供330uA的電流，在UFP端的CC pin上就會得到330uA * 5.1k= 1.683V，UFP就可以判斷

DFP為vRd-3.0。或者是DFP用一個上拉電壓10K到VBUS，UFP端的CC pin上的電壓為

5v * 5.1k /（5.1k+10k）=1.688V，UFP一式可以判定DFP為vRd-3.0。


---

4. 發現並配置 VBUS：USB Type-C 電流模式或 USB Power Delivery
下表為Type-C VBUS輸出選項，USB 2.0，USB3.1，USB BC1.2是先前USB協議規定的標準，可以跟隨Type-C兼容。USB Type-C電流1.5A與3A為Type-C所USB PD的功能還需要有USB PD Phy芯片來完成協議溝通，而協議信號是加載在兩個連接的CC引腳上。

![](https://i.imgur.com/uj5JzHE.png)


Type-C如何去決定要執行那個模式呢？這也需要靠CC pin。先提到DFP會有上拉電阻Rp，UFP會有下拉電阻Rd，當DFP與UFP相接，CC pin上就會有分壓，Rd是固定5.1k，而Rp就會依照DFP的類型，而有不同的阻值。UFP會monitor CC pin上的分壓來知道DFP的VBUS類型。另外DFP也用不同大的小的定電流源來提供給CC pin，當電流流到uRd時，同樣可以產生電壓，讓UFP知道DFP的VBUS模式。



![](https://i.imgur.com/4aabmWt.png)


Type-C規格定義了DFP在不同模式下，在CC pin要提供多大的電流或者是要用多大的上拉電阻Rp電阻值。


![](https://i.imgur.com/EFtbvtt.png)
![](https://i.imgur.com/ESbKZ0L.png)

![](https://i.imgur.com/vRRh7Xw.png)


---

http://kevinzhengwork.blogspot.com/2014/08/usb-type-c-configuration-channel-cc-pin.html





Type-C如何去決定要執行那個模式呢?這也需要靠CC pin。先前提到DFP會有上拉電阻Rp，UFP會有下拉電阻Rd，當DFP與UFP相接，CC pin上就會有分壓，Rd是固定5.1k，而Rp就會依照DFP的類別，而有不一樣的阻值。UFP會monitor CC pin上的分壓來知道DFP的VBUS種類。另外DFP也用不同大小的定電流源來供給CC pin，當電流流到uRd，同樣可以產生電壓，讓UFP知道DFP的VBUS模式。



在UFP是由CC pin上的電壓，來得知DFP的VBUS輸出能力。例如DFP為5V/3A，它可以在CC pin上供330uA的電流，在UFP端的CC pin上就會得到330uA * 5.1k=1.683V，UFP就可以判斷
DFP為vRd-3.0。或是DFP用一個上拉電阻10K到VBUS，UFP端的CC pin上的電壓為
5v * 5.1k /(5.1k+10k)=1.688V，UFP一樣可以判斷DFP為vRd-3.0。


要將C接到A，需要一個轉接頭或是一個C to A的cable。你要讓手機供電給device，會需要在轉接頭或cable內的cc pin加一個pulldown電阻5.1K，讓手機可以辨識對方為device。你可以參考Type-C SPEC Figure4-25。


如果要將Type C Host接到傳統A/B的裝置，需要一個轉接線或轉接頭，在Type-C plug的CC pin要接一個對地電阻Rd 5.1K，這樣Type-C Host才會供5V。

請參考文章內，Table4-10，DFP Source有3種，Default USB Power、1.5A、3A。
這3種電源提供的電流或分壓是不同的。雖然你接了5.1K，可以讓Source提供5V給你
，但你無法辦別外部接進來的DFP Source是那一種。如果外部接進來的是5V/1.5A
Source，但你當作5V/3A抽載，就會產生問題。回答你的問題...
1.即使你的板子沒有PD IC，只要有5.1K，就可以讓DFP Source供5v電壓進來，不
會不斷開關。但你抽載的電流大於Source的供電能力，就會有問題。
2.你的板子沒有USB2/3訊號，也不會有問題。只要你的板子上有IC能辨識CC的電壓
準位，就可以判斷DFP Source是Table4-10裡的那一個，才能依照Source能力
來抽載。

---

https://ithelp.ithome.com.tw/articles/10257242
![](https://i.imgur.com/Od8nKGK.jpg)

(1) DFP (Downstream Facing Port)為 Host 端，另一邊的 UFP (Upstream Facing Port)則為 device 端。在 DFP
的 CC pin 會有上拉電阻 Rp，在 UFP 則會有下拉電阻 Rd。(Rp決定host端提供給device端的供電能力)
(2) 在 DFP 與 UFP 未連接之，DFP 的 VBUS 是沒有輸出的。當 DFP 與 UFP 連接後，CC pin 相接，DFP 的
CC pin 偵測到 UFP pulldown Rd，表示接到 Device，DFP 便打開 VBUS 的 FET 開關，輸出 VBUS 電源給
UFP，也就是說在尚未偵測到 CC PIN 的設定之前，VBUS 是不會供應任何電源給 UFP 端的。
(3) 從上圖可以明顯得知,除了 Ra 之外，其餘電阻都不該出現在 cable 之中，Ra 數值如下圖表格所述是一個區間值，一般使用 1k ohm，如作為電源供應器的線材則可能會略低於 800 ohm :


![](https://i.imgur.com/GeM1pzg.jpg)
圖8.Ra電阻值區間 ↑

(4) Rp 的數值是有被規範的，目前常見的 56k ohm 被規範為 default USB power，一般用於相容於傳統 USB架構，故常出現 USB2.0/USB3.0 的 type A/B to type C 的線材在 type C 端加入該電阻。其餘電阻值請看
下圖表格:

![](https://i.imgur.com/joslE06.jpg)


圖9.Rp電阻值區間 ↑

(5) Rd 在規範中僅有 5.1k ohm ，不會在 cable 中使用。
(6) 有 Ra 的 cable，內部一定都有 e-mark IC，所以都會支援 PD 協議。沒有 Ra 的 cable 一定就是 passive cable，內部是沒有 IC 的，當然一定不支援 PD 協議。
(7) CC pin 的偵測可分為以下數種結果：
![](https://i.imgur.com/YGLBupT.jpg)

![](https://i.imgur.com/tyTFQPo.jpg)
圖10.Source端 CC pin 偵測結果總表 ↑

Sink端通電後，將偵測CC1和CC2的電壓是否大於其本地接地電壓，若處於較高的電壓，即代表被Source端中的Rp上拉電位，所以可以判斷插頭的方向。
(8) 正反插偵測
由於 Type-C 是支援正反插，CC pin 被用來偵測正反插，從 DFP 的角度來看，當 CC1 接到 Pulldown (Rd)就是正插，如果是 CC2 接到 Pulldown 就是反插。在偵測完正反插後，就會輸出相對應的 USB 信號， 例如 CC1 對應的是 SSTX1 與 SSRX1。下圖的右邊整合了 MUX，由於 USB 3.1 的 data rate 高達 10 Gbps，為了避免 PCB 的走線出現分支，所以正反插進來的訊號會由 MUX 來切換，正插時，切換到 SSRX1&SSTX1，反插時，切換到 SSRX2&SSTX2。


http://kevinzhengwork.blogspot.com/2014/08/usb-type-c-configuration-channel-cc-pin.html


![](https://i.imgur.com/S8viUqj.png)
https://cdn.sparkfun.com/assets/e/b/4/f/7/USB-C_Datasheet.pdf
https://www.ti.com.cn/cn/lit/ug/zhcu622/zhcu622.pdf?ts=1669427018533&ref_url=http%253A%252F%252Fwww.ti.com.cn%252Ftool%252Fcn%252FTIDA-050016


![](https://i.imgur.com/8XfTzOJ.png)
https://forum.digikey.com/t/simple-way-to-use-usb-type-c-to-get-5v-at-up-to-3a-15w/7016
https://www.st.com/resource/en/technical_article/dm00496853-overview-of-usb-type-c-and-power-delivery-technologies-stmicroelectronics.pdf


![](https://i.imgur.com/JmP367a.png)


https://www.cnblogs.com/zxc2man/p/14991620.html


