## LAVI's Message Queue Side Project
使用 [RabbitMQ](https://www.rabbitmq.com/) 來實作 Message Queue 

## Information
### Environment
1. 先至[官方文件](https://www.rabbitmq.com/install-windows.html)中下載 Windows 版本的 `rabbitmq-server-3.11.15`
2. 在 windows 環境下安裝 RabbitMQ 需先安裝 [Erlang 套件](https://www.erlang.org/downloads)，目前的版本是 `Erlang OTP 25.3.2`

### Details
1. 執行 `rabbitmq-plugins.bat enable rabbitmq_management`
    - RabbitMQ 指令，用於啟用 RabbitMQ 管理插件
2. 訪問 RabbitMQ 的 Web 管理介面 `http://localhost:15672`，預設帳密為 `guest:guest`，登入後會進入 Overview 頁面，可查看 queue 中的 message 數量及 rate
3. 利用 [Github rabbitmq/rabbitmq-tutorials](https://github.com/rabbitmq/rabbitmq-tutorials/tree/main/python) 中提供的 Hello World 示範 `send.py` 進行測試
4. 令自身成為訊息接收方，利用 `receive.py` 接收目前在 queue 裡的所有訊息

### Knowledge
- 整個實作 Message queue 的過程中有三個角色：
  1. 將 message 發送到 Queue 者，為 Producer (本次實作時，利用 send.py 將 message 發送至 queue)
  2. 負責暫存 message，為 Queue (本次實作利用了 RabbitMQ 提供的服務)
  3. 從 Queue 中接收訊息者，為 Consumer (本次實作時，利用 receive.py 接收 queue 中的 message)
- 而本次實作利用 RabbitMQ 中的 Direct 模式進行，Direct 模式只會有一個 Producer 發送 message，也只會有一個 Consumer 接收 message，類似於單點至單點傳送訊息的關係

## Reference
- [下載 Windows 版本的 rabbitmq-server-3.11.15](https://www.rabbitmq.com/install-windows.html)
- [Erlang 套件官方下載](https://www.erlang.org/downloads)
- [Install RabbitMQ on windows 11 (with management console)](https://www.youtube.com/watch?v=9-RiNlhzHek)
- [Github rabbitmq/rabbitmq-tutorials](https://github.com/rabbitmq/rabbitmq-tutorials/tree/main/python)
- [RabbitMQ 基本介紹、安裝教學](https://kucw.github.io/blog/2020/11/rabbitmq/)

<!-- 自從寫作品集的時候發現當初過程紀錄和截圖都太糊ㄌ...
以至於未來整理的時候很頭疼
這次學乖了，寫好得當下就要仔細寫好紀錄，未來的自己會感謝你 QQ -->

