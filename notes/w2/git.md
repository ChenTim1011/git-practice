
想要了解更多關於 Git 的知識， Git 是一個分散式版本控制系統，也是我們每天都在使用的工具。

### 1. 物件模型

Git 的核心是基於四種物件類型：

- **Blob（Binary Large Object）**：用於儲存檔案的內容。每個檔案的內容都被存為一個 blob 物件，與檔名無關。

- **Tree（樹）**：表示目錄結構，包含指向 blob 和其他 tree 物件的指標，並記錄檔名和目錄結構。

- **Commit（提交）**：記錄一次提交的狀態，包含指向一個 tree 物件的指標，以及提交者資訊、提交訊息和父提交的指標。

- **Tag（標籤）**：為特定的 commit 物件加上可讀的標籤，通常用於版本發布。

這些物件都以 SHA-1 雜湊值作為唯一標識，確保內容的完整性和唯一性。

### 2. 資料儲存

Git 將這些物件儲存在 `.git/objects` 目錄中。每個物件的 SHA-1 雜湊值的前兩個字元作為子目錄名稱，後 38 個字元作為檔案名。例如，物件 `d670460b4b4aece5915caf5c68d12f560a9fe3e4` 會儲存在 `.git/objects/d6/70460b4b4aece5915caf5c68d12f560a9fe3e4`。

### 3. 索引（Index）

索引（或稱暫存區）是 Git 的一個中間層，位於工作目錄和本地儲存庫之間。當執行 `git add` 時，檔案的變更會被添加到索引中，
準備提交。索引確保了提交的準確性和一致性。

### 4. 分支與標籤

- **分支（Branch）**：實際上是指向特定 commit 物件的可移動指標。當在某個分支上進行新的提交時，該分支的指標會移動到最新的 commit。

- **標籤（Tag）**：是指向特定 commit 的固定指標，通常用於標記版本發布。

### 5. 差異儲存與壓縮

為了節省空間，Git 使用差異儲存和壓縮技術。

- **差異儲存**：在物件之間只儲存差異部分，減少重複資料。

- **壓縮**：使用 zlib 壓縮演算法壓縮物件，進一步節省空間。

### 6. 分散式特性

每個 Git 儲存庫都是完整的，包含所有的歷史記錄和物件。這使得 Git 能夠在沒有中央伺服器的情況下運作，並且支持離線操作。

### 7. 安全性與完整性

Git 使用 SHA-1 雜湊確保資料的完整性。每個物件的內容都會生成一個唯一的 SHA-1 雜湊值，任何變更都會導致不同的雜湊值，確保資料未被篡改。

 