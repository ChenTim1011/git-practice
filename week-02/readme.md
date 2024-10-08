### A. 環境準備

- 在自已的開發電腦安裝好 NodeJS（或 Deno, Bun, …）
    - https://nodejs.org/en
    - 思考: 安裝哪個版本？為什麼？
- 請在 week-02/readme.md 中描述
    - 安裝的 nodejs 版本
    - (optional) 如果不是安裝 NodeJS，那可以試著說明為什麼？ → 練習回答技術選型問題
    - nvm 與 npm 分別是什麼

___


### 思考: 安裝哪個版本？為什麼？

#### 安裝 Node.js v20.17.0
我覺得應該安裝具有 LTS ( Long-term support ) 的Node.js v20.17.0，我覺得有三個原因
1. 對於軟體來說，定期維護更新很重要，當遇到漏洞或潛在風險能夠即時修補，使軟體具有更好的可靠性。
2. 具有 LTS 版本的軟體，注重軟體品質而不是新功能，新功能可能會有一些錯誤產生，在開發產品可能有導致更多漏洞。
3. 未來在公司開發產品，如果因為安裝軟體而產生漏洞，需要額外成本來除錯，所以選擇 LTS 版本軟體能降低風險。




### (optional) 如果不是安裝 NodeJS，那可以試著說明為什麼？
    
1. 選擇 bun：如果你需要追求啟動速度和運行效能、需要快速的開發者體驗、小型或快速開發專案，bun 會是一個不錯的選擇。
2. 選擇 Node.js：如果正在開發大型應用、需要穩定的生態系統、處理企業級需求，Node.js 是更為成熟和可靠的選擇。
    
### nvm 與 npm 分別是什麼?
    
1. nvm 是 Node.js **版本管理器**，允許你在一台機器上安裝和切換多個不同版本的 Node.js。
   因為每個專案可能依賴於特定版本的 Node.js 或其套件，所以 nvm 是很好用的工具。
2. npm 是 Node.js 的**套件管理工具**，用於管理 JavaScript 和 Node.js 應用中的第三方套件。
   npm 可以讓我們方便安裝、管理和分享開發中使用的各種 JavaScript 函式庫和工具。

### 參考資料
- [bun](https://bun.sh/)
- [nvm](https://github.com/nvm-sh/nvm)
- [npm](https://github.com/npm/cli)



### 補充 關於fib.js

我使用了遞迴法、遞迴 TCO法 、 迭代法、改良前動態規劃法、改良後動態規劃法、來求費波納契數。 比較 n = 5 到 n = 45 所需要花費的時間如圖所示,資料結果可以看 newFibExperiment.md


![實驗結果1](https://github.com/user-attachments/assets/572c7b0d-9676-40b8-bebe-36a13bf0b6c8)



接下來實驗是 比較 n = 2 到 n = 8192 遞迴 TCO法 、 迭代法、改良前動態規劃法、改良後動態規劃法、來求費波納契數哪個比較快。
做到 n = 8192 是因為數字太大遞迴 TCO 法 遞迴深度過深會出錯，資料結果可以看 FibExperiment2.md



![實驗結果2](https://github.com/user-attachments/assets/f64a1516-67b7-48cd-804e-822fb67d13f8)


#### 結論：
- 遞迴法 隨著 n 增加，計算時間顯著增長。對於較大的 n，遞迴方法的時間呈指數級增長， 時間複雜度 O(2^n)，在計算數字大費波納契數時非常慢。
- 遞迴 TCO 法: 遞迴 TCO 法顯示改善遞迴法的時間和空間，時間複雜度可以到 O(n) ， 空間複雜度也可以到 O(1)， 但是網路上有些提到  一些瀏覽器不支援 TCO 的說法，實驗測試 n 太大 也是會導致遞迴深度過深會出錯，空間複雜度也可能變成 O(n)。
- 迭代法: 一直是最快的，隨著 n 增加，表現出 O(n) 時間複雜度。
- 動態規劃法: 也表現得相當有效率，與迭代法相似，但由於需要用陣列儲存先前計算的值，需要 O(n) 的空間複雜度，
但我們可以學習迭代法，用三個變數去儲存之前算過的值，那只要花 O(1) 的空間複雜度。
但是我選擇**使用陣列去存三個變數，實驗出來的速度和迭代法有差，這是一個很有趣的問題。**

比較:
| 演算法          | 空間複雜度 | 時間複雜度 |
| --------------- | ---------- | ---------- |
| 遞迴法          | O(n)       | O(2^n)     |
| 遞迴 TCO法      | O(1)       | O(n)      |
| 迭代法          | O(1)       | O(n)       |
| 原本的動態規劃  | O(n)       | O(n)       |
| 改良後的動態規劃| O(1)       | O(n)       |



#### 分析一下為什麼 recursive 這麼慢嗎？
- 直觀分析: 直接數看看總共跑了幾次，可以發現因為遞迴會一直重複呼叫，已經重複計算過的內容。


#### 選擇
以上五種方法我會選擇 迭代法 因為 實作容易、程式碼可讀性、空間複雜度 O(1)、時間複雜度 O(n) 。


              

#### 作業二心得
- 這次作業學會到的三個意識
1. 檢查程式碼的語法是否可以再更精簡!
2. 當我有好幾個不同的選擇，我選擇的理由是什麼?  我要如何來支持我的選擇?
3. 對於實驗觀察的結果，抱持好奇心去討論為什麼會這樣?

#### 參考
[Fibonacci Iterative vs. Recursive](https://syedtousifahmed.medium.com/fibonacci-iterative-vs-recursive-5182d7783055)
