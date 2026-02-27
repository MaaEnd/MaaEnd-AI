# ItemTransfer 物品检测模型

库存转移等流程中使用的 YOLO 物品检测 ONNX 模型，供 Pipeline `NeuralNetworkDetect` 使用。

## ItemTransfer.onnx

- **用途**：在仓库/背包区域检测物品图标（替代 TemplateMatch）。
- **类别**：与 `ItemTransfer/classes.txt` 一致，共 193 类；class id = 该文件中行号（从 0 开始）。

### 来源

- [Endfield_Vision_Models](https://github.com/icaruszezen/Endfield_Vision_Models) 的 YOLOv11 模型：`EF_items_11n.pt`。

### 操作内容（生成 ItemTransfer.onnx）

1. 下载 `EF_items_11n.pt` 到本地。
2. 使用 Ultralytics（YOLOv11）将 `.pt` 导出为 ONNX，输入/输出与当前 Pipeline 使用的 `ItemTransfer.onnx` 一致。
3. 将生成的 `ItemTransfer.onnx` 放入本目录（`assets/resource/model/detect/ItemTransfer/`）。
