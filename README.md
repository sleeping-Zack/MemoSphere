![](https://raw.githubusercontent.com/sleeping-Zack/my-images/main/img/screenshot2025-09-24.png)
---

# 📄 README.md

```markdown
# MemoSphere - AI Virtual Companion in a Crystal Ball

MemoSphere 是一个基于 **AI + 语音交互 + 虚拟人物渲染** 的创新项目。  
用户可以通过语音与“水晶球中的虚拟人物”自然对话，角色会实时回复、动嘴、变表情，带来沉浸式的陪伴体验。  
预期效果图如上

---

## ✨ Features
- **语音交互**：实时语音识别（ASR）+ AI 对话（LLM）+ 语音合成（TTS）  
- **虚拟人物渲染**：圆形屏幕显示人物，支持嘴型动画和表情切换  
- **角色人设**：可设定性格、语气和身份（如初恋、前女友、治愈系伙伴）  
- **对话记忆**：本地保存聊天记录，支持短期上下文  
- **本地运行 & 云端支持**：树莓派或 PC + 云 API  

---

## 🖼️ System Architecture
```

用户语音 → ASR → LLM → TTS → 音频播放 + viseme → 虚拟人物渲染 → 水晶球显示

````

模块：
1. **唤醒模块**（按键/语音触发）  
2. **ASR 模块**（语音转文字）  
3. **LLM 模块**（AI 对话逻辑 + 人设）  
4. **TTS 模块**（文字转语音 + viseme 时间戳）  
5. **渲染模块**（嘴型 & 表情驱动，pygame/Live2D）  
6. **音频播放模块**（同步输出语音）  
7. **数据存储模块**（SQLite 保存对话记录）  

---

## ⚙️ Requirements
- 硬件：  
  - Raspberry Pi 4 (推荐)  
  - 圆形 HDMI 屏幕（480×480）  
  - USB/I2S 麦克风 + 小型扬声器  
  - 亚克力水晶球外壳  

- 软件依赖：  
  ```bash
  Python 3.9+
  pip install pyaudio sounddevice pygame requests sqlite3
````

* 云服务（任选）：

  * Azure Speech-to-Text (ASR)
  * Azure Text-to-Speech (TTS)
  * OpenAI API (ChatGPT / GPT-4o-mini)

---

## 🚀 Quick Start

1. 克隆仓库

   ```bash
   git clone https://github.com/yourname/crystalmate.git
   cd crystalmate
   ```

2. 配置 API Key
   在 `config.json` 中填入：

   ```json
   {
     "openai_api_key": "your_api_key",
     "azure_speech_key": "your_api_key",
     "azure_region": "eastasia"
   }
   ```

3. 运行主程序

   ```bash
   python main.py
   ```

4. 对着水晶球说话，享受和虚拟人物的互动！

---

## 📂 Project Structure

```
crystalmate/
│── assets/          # 人物立绘、嘴型、表情 PNG
│── config.json      # API Key 配置
│── main.py          # 主程序入口
│── asr.py           # 语音识别
│── llm.py           # 对话逻辑
│── tts.py           # 语音合成 + viseme
│── render.py        # 渲染模块
│── audio.py         # 音频播放
│── memory.py        # 对话存储 (SQLite)
│── utils/           # 工具函数
```

---

## 🔮 Future Work

* 捏脸功能：允许用户创建独特的虚拟人物
* 多场景模式：虚拟约会、学习助手、心理陪伴
* 本地化部署：支持离线 ASR + TTS
* AR/VR 版本：结合头显增强沉浸感

---



