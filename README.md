# FPGA_FinalProject

### Authors: 109213057 109213064

#### Input/Output unit:
```verilog=
module project2(
    input CLK, reset, start,
    output reg [0:27] led,
    output reg [2:0] life,
    output reg beep,
    input left, right,
    input throw,
    input show_two_row,
    output reg a,b,c,d,e,f,g,
    output reg [0:3] COM,
    input highSpeed
);
```
* 輸入
    * CLK : 用來當作除頻器
    * reset : 當死掉時,可以重設球的位置到板子上
    * start： 啟動/暫停遊戲
    * left： 向左移動板子
    * right： 向右移動板子
    * throw： 當球在板子上的時候丟出球
    * show_two_row： 當遊戲死亡或勝利時，設定下次遊戲是否要出現一排或兩排磚塊（on 為兩排磚塊）
    * highSpeed： 選擇是否讓球快速移動（on 為快速移動）

* 輸出
    * led: 8*8 LED 顯示輸出
    * life: 3 位元的生命值
    * beep: 蜂鳴器輸出
    * a, b, c, d, e, f, g: 七段顯示器輸出
    * COM: 4 位元的控制七段顯示器的輸出

#### 功能說明:
1. 平台控制：使用按鈕控制平台左右移動，不讓球落下
2. 球的角度：球每次碰到磚塊/牆壁後會反彈
3. 多種磚塊：地圖上有多種不同顏色的磚塊，每個磚塊的分數不同
4. 計分制：擊打磚塊得分
5. 遊戲結束畫面：遊戲結束時(沒有接到球/磚塊到達底部)顯示玩家的得分

#### 程式模組說明:
> *** 請說明各 I/O 變數接到哪個 FPGA I/O 裝置，例如: button, button2 -> 接到 4-bit SW
*** 請加強說明程式邏輯
![image](https://hackmd.io/_uploads/rJDXlAwu6.png)
![image](https://hackmd.io/_uploads/H1tSeAPO6.png)
![image](https://hackmd.io/_uploads/ByPwlRPup.png)

#### Demo video: (請將影片放到雲端空間)
https://drive.google.com/drive/folders/1y-0xPFgwEqcWb8KKfoKyG0W5o9wBjTjC?usp=sharing