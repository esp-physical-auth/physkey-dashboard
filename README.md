# ESP Physical Auth · Web

ATRI 物理认证器的配套 Web 应用。全部为静态 HTML，通过 Web Bluetooth 与 ESP32-C5 硬件通信，无需后端服务器。

## 组成

- **`totp.html`** — TOTP 两步验证器。向硬件下发密钥，由设备生成基于时间的六位动态口令，界面实时显示并自动刷新。
- **`wallet.html`** — BTC 冷钱包 / 交易签名器。在浏览器中使用 `bitcoinjs-lib` + `@scure/bip32` 进行 HD 派生，真正的私钥签名运算在 ESP32 端完成，私钥永不离开设备。

## 使用

直接双击打开 HTML 文件，或用任意静态服务器托管（例如 `python3 -m http.server`）。浏览器需支持 Web Bluetooth（Chrome / Edge / 新版 Safari），并通过 HTTPS 或 `localhost` 访问。

首次使用请先让硬件进入配对模式，然后在页面点击「连接」按钮完成 BLE 绑定。

## 许可

本项目采用 GNU General Public License v3.0（GPLv3）授权。你可以自由地运行、研究、修改和分发本软件，但修改后的作品必须以相同许可发布，并提供源代码。详见 [https://www.gnu.org/licenses/gpl-3.0.txt](https://www.gnu.org/licenses/gpl-3.0.txt)。

```
ESP Physical Auth · Web — ATRI 物理认证器配套 Web 应用
Copyright (C) 2026

This program is free software: you can redistribute it and/or modify
it under the terms of the GNU General Public License as published by
the Free Software Foundation, either version 3 of the License, or
(at your option) any later version.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the
GNU General Public License for more details.

You should have received a copy of the GNU General Public License
along with this program. If not, see <https://www.gnu.org/licenses/>.
```