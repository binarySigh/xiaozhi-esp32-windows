# xiaozhi-esp32-windows

小智AI ESP32固件 Windows 版 — 用于二次开发（修改默认请求地址、UI去气泡等）

## 修改说明

### 移除聊天气泡
删除 `atk-dnesp32s3-box/config.json` 中的 `CONFIG_USE_WECHAT_MESSAGE_STYLE=y`，编译后使用默认的非气泡模式。

### 修改默认请求地址
将 `Kconfig.projbuild` 中 `CONFIG_OTA_URL` 的默认值从 `https://api.tenclass.net/xiaozhi/ota/` 改为 `http://192.168.3.56:8899`，指向本地桥接服务。

⚠️ 如果设备之前连过官方服务器，NVS 中可能存有旧的 OTA URL，需执行 `idf.py erase-flash` 擦除后才能让新默认值生效。
