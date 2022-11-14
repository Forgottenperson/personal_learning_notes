CPU/IO
---
* non-blocking    IO
* blocking        IO

主要是讀取順序

使用多次 setTimeout(延遲執行callback) 並觀察過程 可以知道 nodejs 是 哪種類型

* non-blocking    CPU(多Thread)
* blocking        CPU(單Thread)

主要是運算順序

使用多次 讓for迴圈執行10000次計算 並觀察過程 可以知道 nodejs 是 哪種類型
