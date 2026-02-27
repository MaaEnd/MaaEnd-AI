# ItemTransfer 物品检测模型

库存转移等流程中使用的 YOLO 物品检测 ONNX 模型，供 Pipeline `NeuralNetworkDetect` 使用。

## ItemTransfer.onnx

- **用途**：在仓库/背包区域检测物品图标（替代 TemplateMatch）。
- **来源**：[Endfield_Vision_Models](https://github.com/icaruszezen/Endfield_Vision_Models) 的 YOLOv11 模型（`EF_items_11n.pt`）导出为 ONNX。
- **类别**：与 `items/classes.txt` 一致，共 193 类；class id = 该文件中行号（从 0 开始）。

### 如何生成 ItemTransfer.onnx

1. 从 [Releases](https://github.com/icaruszezen/Endfield_Vision_Models/releases) 下载 `EF_items_11n.pt`（若脚本下载因 SSL 失败可手动下载）。
2. 在项目根目录执行：

   ```bash
   pip install ultralytics
   python tools/ItemTransfer/export_ef_items_onnx.py "path/to/EF_items_11n.pt"
   ```

   或将已下载的 `.pt` 放到 `tools/ItemTransfer/` 下并运行：

   ```bash
   python tools/ItemTransfer/export_ef_items_onnx.py
   ```

3. 生成的 `ItemTransfer.onnx` 会写入本目录。
