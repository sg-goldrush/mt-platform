# mt-platform

机器视觉标注与训练一体化平台。

## 功能

- **数据集管理** — ZIP 上传、在线标注（YOLO OBB/检测）、类别筛选统计
- **模型训练** — YOLOv11，CPU/GPU，实时进度，断点恢复
- **AI 辅助标注** — 已训练模型批量推理，IoU 去重
- **多用户系统** — 鉴权登录、管理员看板、数据隔离、存储配额管控

## 快速开始

```bash
pip install -r requirements.txt
python app.py --host 0.0.0.0 --port 9924
```

访问 http://127.0.0.1:9924

## 生产部署

```bash
gunicorn -k gevent -w 2 -b 0.0.0.0:9924 app:app
```

## 项目结构

```
mt-platform/
├── app.py                    # 主应用
├── requirements.txt
├── static/                   # 静态资源
├── templates/                # 页面模板
│   ├── training.html         # 训练页面
│   ├── annotation.html       # 标注页面
│   └── dashboard.html        # 管理员看板
├── pre_models/               # 预训练模型
├── uploads/                  # 用户数据（按用户隔离）
├── runs/                     # 训练输出
└── tmp/                      # 临时文件
```

## 致谢

本项目基于 [xclabel](https://github.com/beixiaocai/xclabel) (MIT License) 二次开发，借鉴了其 UI 设计和标注交互逻辑。

## License

MIT
