# mt-platform

YOLO 模型训练平台，基于 Flask + Ultralytics YOLO11。

### 核心功能
- YOLO 模型训练全流程：数据集上传、模型选择、断点恢复、模型测试、下载
- 支持 CPU / GPU 训练
- 实时训练进度、日志、指标监控
- YOLO 格式数据集上传（ZIP）

### 使用说明

1. **安装依赖**：
   ```bash
   python -m venv venv

   # Linux/Mac
   source venv/bin/activate

   # Windows
   venv\Scripts\activate

   pip install -r requirements.txt

   # 训练依赖
   pip install ultralytics==8.3.1
   pip install numpy==1.26.4

   # CPU 版 torch
   pip install torch==2.1.2 torchvision==0.16.2

   # CUDA 版 torch
   pip install torch==2.1.0 torchaudio==2.1.0 torchvision==0.16.0 --index-url https://download.pytorch.org/whl/cu121
   ```

2. **启动服务**：
   ```bash
   python app.py --host 0.0.0.0 --port 9924
   ```

3. **访问**：http://127.0.0.1:9924

### 项目结构
```
mt-platform/
├── app.py                    # 主应用
├── requirements.txt          # 依赖列表
├── static/                   # 静态资源
├── templates/
│   ├── base.html             # 基模板
│   └── training.html         # 训练页面
├── pre_models/               # 预训练模型（.pt）
├── uploads/
│   └── training_datasets/    # 训练数据集
├── runs/                     # 训练输出
└── tmp/                      # 临时文件
```

### 技术栈
Flask + Flask-SocketIO | Ultralytics YOLO11 | Socket.IO

### 授权协议
MIT
