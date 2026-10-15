# HuiOS
HuiOS 低延迟游戏系统介绍
HuiOS is a low-latency gaming-oriented Windows ISO by 灰角 (NTLite-based). Not a reskin of Atlas / XOS / Revi — deep work on Timer, input queues, MSI/IRQ, power plans, and the network stack, plus Chinese tooling and support.
中文简介：面向游戏手感的 Windows 封装镜像（优化写进 ISO）。
## Why
- Push system / input latency and 1% lows for competitive games
- Keep a clean, slim environment without turning Windows into an unusable toy
- Public framing: strong measured results on real hardware — not “world #1”
## Latency (BoosterX)
| Run | Average | Min | Max | Std Dev | Samples |
|-----|--------:|----:|----:|--------:|--------:|
| A | **2.15 ms** | 1.94 | 2.41 | 0.06 | 100 |
| B | **1.97 ms** | 1.92 | 2.06 | 0.02 | 100 |
Hardware sets the floor; software mainly cleans jitter and the long tail.
![BoosterX ~2.15 ms]
![BoosterX ~1.97 ms]
## Positioning
Public framing: **upper tier of the first class** for gaming system + input latency (dual-stack: low latency + low jitter). Extreme-tier results around ~2 ms average with very low jitter are uncommon in public BoosterX-style runs. Fame is still catching up — publish measurements, never “#1 in the world”.
定位：游戏系统 / 输入延迟 **第一梯队上游、双优极限档**；公开可见约 2 ms 且抖动极低的结果较少。
## What’s inside
- Timer / keyboard & mouse data queues / priority
- MSI·IRQ (skip PCIe root ports; do not touch Wi‑Fi)
- Power plan + selective service / startup cleanup
- Wired NIC low-latency path
- Tools: startup/service manager, GPU background toggles, game helpers
## Notes
- Cannot lower server ping; FPS varies by hardware / game
- Slim builds may remove some security components — install software from trusted sources
- Contact: Douyin 灰角 · WeChat `Yuan08150323`
---
Public intro only. Full ISO / paid scripts are not distributed here.<img width="1920" height="1080" alt="boosterX2" src="https://github.com/user-attachments/assets/9fe60934-ed2c-4ec2-8ea5-82d4205ababe" />
<img width="575" height="545" alt="boosterX1" src="https://github.com/user-attachments/assets/2441e14b-62c9-444d-a4a7-51fd1af932d4" />


