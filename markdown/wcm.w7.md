---
Title: WCM 五專第七週課程內容
Date: 2024-04-01 11:00
Category: 五專
Tags: Brython, w7
Slug:wcm-w7-project
Author: kmol
---

w7
<!-- PELICAN_END_SUMMARY -->

# 練習利用程式建立單字查詢網頁

wcm2024 5j w7 利用 Python 建立 Javascript 電子書的單字查詢超文件

利用 [2.txt](https://mde.tw/wcm2024/downloads/2.txt) 與 [1.txt](https://mde.tw/wcm2024/downloads/1.txt) Python 程式, 從下列電子書建立英文單字查詢網頁:

# Brython 程式

首先, 對 ChatGPT 提問: Brython 是甚麼程式語言? 該如何使用?

回答:

Brython 是一種在瀏覽器中運行的 Python 解譯器。它允許您在網頁上使用 Python 來編寫 Web-based 前端程式，而無需安裝任何套件或外部解譯器。
[自動猜數字遊戲]: https://mde.tw/wcm2024/content/Brython.html?src=https://gist.githubusercontent.com/mdecycu/8ba6fa28317bc7a784d8350e7bc33580/raw/cb3b9b3e455c54381482d2f98f153442eff93ec4/auto_guessing_game.py

<pre class="brush: python">
# 程式自動猜數字遊戲
# 從 browser 導入 document, html 與 alert 模組
from browser import document, html, alert
# 導入 random 模組
import random

# 宣告一個變數, 名稱為 "id4", 與超文件中 id 為 "brython_div1" 的物件進行對應
id4 = document["brython_div1"]
# 宣告一個變數, 名稱為 "執行次數", 起始對應為 100
執行次數 = 100
# 宣告 "總猜測次數" 變數, 起始對應為 0
總猜測次數 = 0
# range() 是一個能夠建立一系列數字的函式
for i in range(執行次數):
    # "<=" 是 Brython 特有符號, 用來將超文字指向左邊對應的變數在網頁超文件標註中的位置
    id4 <= "第" + str(i+1) + "次玩:" + html.BR()
    下限 = 1
    上限 = 100
    # 利用能夠產生整數亂數的函式, 建立標準答案變數對應整數
    標準答案 = random.randint(下限, 上限)
    # pc 所猜的數字也是由亂數函式產生
    pc猜的數字 = random.randint(下限, 上限)
    #print(標準答案, pc猜的數字)
    #integer int()
    #string str()
    #float float()
    #你猜的數字 = int(input("請輸入您所猜的整數:"))
    猜測次數 = 1
    while 標準答案 != pc猜的數字:
        if 標準答案 < pc猜的數字:
            #print("太大了，再猜一次 :)加油")
            # 因此已經確定"pc猜的數字"不是答案, 因此 - 1
            id4 <= "電腦猜的數字:" + str(pc猜的數字) + " 太大了!" + html.BR()
            上限 = pc猜的數字 - 1
        else:
            #print("太小了，再猜一次 :)加油")
            # 因此已經確定"pc猜的數字"不是答案, 因此 + 1
            id4 <= "電腦猜的數字:" + str(pc猜的數字) + " 太小了!" + html.BR()
            下限 = pc猜的數字 + 1
        #pc猜的數字 = int(input("請輸入您所猜的整數:"))
        pc猜的數字 = random.randint(下限, 上限)
        猜測次數 += 1
    #print("猜對了！總共猜了", 猜測次數, "次")
    id4 <= "電腦猜對了, 答案為: " + str(標準答案) + ", 總共猜了 "+ str(猜測次數) + "次" + html.BR()
    總猜測次數 += 猜測次數
平均猜測次數 = int(總猜測次數/執行次數)
#print("平均次數", 平均猜測次數)
id4 <= "平均次數: " + str(平均猜測次數)
</pre>
# Gist

<https://docs.github.com/en/get-started/writing-on-github/editing-and-sharing-content-with-gists/creating-gists>

請根據上列有關 Github Gist 的簡介說明, 將 Gist 相關的參考資料整理到各自的網誌.
