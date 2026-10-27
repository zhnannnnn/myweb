# 食光小馆 · 在线点餐

无需构建的中文餐馆点餐网页。用任意静态 HTTP 服务运行 `dist` 目录即可。

## 功能

- 6 个菜品分类、9 道示例菜品，支持分类内搜索和口味筛选。
- 餐盘数量增减、自动合计、清空确认、用餐人数及口味备注。
- 下单二次确认，最近 30 条体验订单保存在浏览器 localStorage。
- 桌面三栏布局，小屏横向分类和浮动餐盘，键盘可访问的按钮与弹窗。

这是前端演示。未连接门店、真实订单服务器、支付或服务员呼叫设备，页面已向使用者明确说明。

## 运行

在这台电脑上，可以使用完整路径启动，不受终端当前所在文件夹影响。如果旧服务还在运行，先按 `Ctrl+C` 停止，再执行：

```powershell
python -m http.server 5173 --bind 127.0.0.1 --directory "C:\Users\张浩楠\Documents\ChatGPT\网页制作\shiguang-kitchen\dist"
```

在其他电脑上，请将上面的路径替换为实际的 `dist` 文件夹路径；也可以先进入包含 `dist` 的项目根目录，再运行：

```powershell
python -m http.server 5173 --bind 127.0.0.1 --directory dist
```

访问 http://127.0.0.1:5173 。终端保持运行，按 `Ctrl+C` 停止服务。如果出现 `GET / 404`，请检查 `--directory` 指定的文件夹中是否存在 `index.html`。

该命令仅用于本机预览，不会发布到互联网。可以直接修改 `dist/app.js` 中的菜品信息。

## 视觉素材

`dist/assets/dishes.webp` 为内置 imagegen 生成的六格菜品摄影素材。首次尝试按指定 CLI 配置运行时，配置缺少 `model_providers.SZU_API.experimental_bearer_token`，因此改用内置生成工具。生成提示词保存在 `image-prompt.md`，项目不包含 API 凭据。
