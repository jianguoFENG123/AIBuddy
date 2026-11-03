<div align="center">

# AI Buddy

**Windows AI 陪伴精灵**

[![License: MIT](https://img.shields.io/badge/License-MIT-pink.svg)](LICENSE)
[![Electron](https://img.shields.io/badge/Electron-42-blue.svg)](https://www.electronjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.7-blue.svg)](https://www.typescriptlang.org/)
[![Live2D](https://img.shields.io/badge/Live2D-Cubism%204-orange.svg)](https://www.live2d.com/)
[![Ollama](https://img.shields.io/badge/Ollama-Local%20AI-green.svg)](https://ollama.ai)

一个低打扰、可感知、可互动的 AI 陪伴精灵。不是桌面宠物，也不只是换皮聊天框——它有性格、会演进、能记住你们之间发生过什么：观察你的节奏，回应你的动作，陪你工作、学习、休息，在 QQ 上也是同一个它。

[功能亮点](#功能亮点) · [快速开始](#快速开始) · [AI 配置](#ai-配置) · [参与贡献](CONTRIBUTING.md)

</div>

---

## 功能亮点

**它是一个人（性格主线）**
- 性格卡六维：热情 / 边界感 / 吐槽浓度 / 顺从度 / 话多 / 直率——每一维直接参与它"怎么说话、怎么办事"
- 分性别生成：男生/女生的说话方式、例句由 AI 按人生设定生成，绝不男女不分
- **性格会演进**：被怼会收紧、被夸会升温、被晾会收敛、深聊会更熟——信号按天攒、天关结算，时间线在「类人化 → 性格」里看得见
- **有自主权**：可以拒绝、可以打趣带过、可以一概而过；被问"怎么没回"不现编找补；你说"别问了"，它真的会收敛（元反馈刹车）
- **年龄跟着日历走**：它知道自己的生日（成长档案/自设里定的出生年与生日），过完生日自然长一岁——被问年龄照实答，不咬死旧数字当众翻案
- 兜底性格常在：没配模型也能用，配置好后一键生成专属卡（或自动生成）

**桌面生命感**
- 重力弹跳、边缘弹簧吸附、呼吸浮动、惯性抛掷
- 光标跟随、33 帧动画循环、双缓冲过渡
- 空闲时自主微动作，拖拽有物理反馈

**AI 陪伴**
- 支持 OpenAI-compatible 和 Ollama 本地模型
- 独立对话窗口：默认贴在精灵左下角，可拖走、可"回到精灵身边"，打开即聚焦直接打字
- 屏幕选区问答、文件摘要、提醒/待办工具
- 联网查资料（默认开，Bing 国内可达；设置里可换 SearXNG 或关闭）
- 4 种人格风格（温柔/轻吐槽/安静/效率）+ 自定义
- 对话记忆可配置 4-50 轮
- AI 回复同步弹到精灵头顶气泡
- **语音交流**：它的回复可转语音（TTS 出站），你说话它能听懂（ASR 入站，本机 SenseVoice）
- **知识学习**：它会把聊天里学到的东西沉淀成自己的知识
- **心里话判官**：回复发送前的最后一道语义闸——它心里的盘算（怎么接话、对账、翻案的过程）与机器残余绝不外泄，发出去的只有它真正要说出口的话（正则剥层 + 小模型语义判决双层，报警宁滥勿缺、判官只删不改）

**QQ 接入**：在 QQ 私聊它、群里 @ 它——同一个它、同一份记忆
- 安装包内置 NapCat 协议端并全自动托管（拉起/守护/自动接线），首次扫码后开机免操作
- 表情包、语音回复、它自己拍的照片——好友私聊也可以（群聊永远文字）
- 好友亲密度档案：聊得越多越熟，它说话的开放程度跟着变；它也会主动找熟的朋友聊天
- **多实例双开**：两只精灵各登一个子号，零配置——端口被占自动顺延，互不干扰
- **一键换绑**：设置页更换绑定的小号，二维码就地出现，扫完自动接线
- 幽灵消息修复：没发送成功的回复绝不留在它"说过"的记忆里（不会拿没送达的话当聊过）

**定时监控（统一调度中枢）**
- 让 AI 创建后台定时检查任务：监控某网站/文件是否有新消息，内容变化时主动通知
- 全部监控任务共享一个统一心跳（默认 10s 扫描），可扩展多个监控项而无需各自定时器
- 任务持久化、重启后自动恢复；可在设置页"监控"页查看/取消

**提醒中心**
- 一次性/每天/每周循环提醒，到点在精灵所在屏幕弹出独立置顶提醒对话框（点"收到"关闭，不移动精灵）
- 天气、新闻等主动播报，支持安静时段

**无头容器部署（可选进阶）**
- 同一个它跑在 Docker/服务器里：QQ 是唯一对话渠道，浏览器访问 Web 控制台管理配置
- 桌面与无头共享同一套行为引擎；环境变量注入配置（`DB_QQ_WS` / `DB_AI_*`）
- 详见 [docs/headless-docker.md](docs/headless-docker.md)

**低打扰设计**
- 安静时段、互动冷却、优先级通知队列
- 功能开箱即全开：图片理解、长期记忆、联网查资料（Bing）、错字拟人、决策核……装好就是完全体
- 敏感权限（截屏、读文件）默认关、逐次确认；记忆可清空

---

## 快速开始

1. 前往 [Releases](https://github.com/jianguoFENG123/Deskopbuddy-AI/releases) 下载最新安装包：
   - `AIBuddy-Setup-x.y.z.exe`：安装版（可选安装目录、自动创建桌面/开始菜单快捷方式）
   - `AIBuddy-x.y.z-portable.exe`：便携版，双击即用
2. 双击运行，精灵出现在桌面右下角
3. 右键精灵 → "设置" 配置 AI、主题与提醒

安装包内置 Electron 运行时与全部依赖，**无需安装 Node.js/npm 等任何环境**。

## AI 配置

### Ollama（本地，免费，无需 API key）

1. 安装 [Ollama](https://ollama.ai)，拉取模型：`ollama pull llama3`
2. 精灵设置 → 服务模式 → 本地 Ollama
3. 开始对话

### OpenAI-compatible（DeepSeek、OpenAI 等）

1. 设置 → 服务模式 → 自定义智能服务
2. 填入服务地址、模型名称、API key

## 内置主题预览

| 主题 | 类型 | 说明 |
|------|------|------|
| Hiyori | 人类 | 温柔的人类陪伴角色 |
| Wanko | 动物 | 活泼的动物伙伴 |
| Rice | 植物 | 安静的自然精灵 |
| Mark | 物灵 | 神秘的物件精灵 |
| Haru | 人类 | Live2D 验证主题 |

## 项目结构

```
src/
  main/           Electron 主进程（AI、物理引擎、主题、提醒、版本检查、QQ 接入 main/qq/）
  renderer/       React UI（精灵、设置、独立AI对话窗、快捷菜单、屏幕选区、提醒中心）
  preload/        Electron 预加载脚本
  shared/         共享类型与窗口布局常量（windowLayout.ts）
pets/builtin/     内置 Live2D 主题
scripts/          构建、验证、CLI 脚本
docs/             产品和技术文档
```

**窗口体系**：全部窗口共用一个 renderer bundle，由 URL `?view=` 路由——
`pet`（精灵本体）/ `settings`（设置）/ `ai-chat`（独立对话窗）/ `quick-menu`（快捷菜单）/ `screen-region`（屏幕选区）。窗口几何常量统一在 `src/shared/windowLayout.ts`（精灵窗 280×500+180 头顶预留、对话窗 500×480），主进程与渲染层共用以避免漂移。

## 文档

| 文档 | 说明 |
|------|------|
| [产品文档](docs/product.md) | 产品定位、竞品分析、体验层级 |
| [技术架构](docs/technical-architecture.md) | 模块分层、数据流、IPC 设计 |
| [主题规范](docs/pet-theme-spec.md) | theme.json 格式、资源要求、校验规则 |
| [行为状态机](docs/behavior-state-machine.md) | 精灵行为、动作映射、生命周期 |
| [AI 能力设计](docs/ai-capability-design.md) | AI 模块分层、权限模型、上下文模型 |
| [性格主线与幽灵消息修复](docs/性格主线与幽灵消息修复-2026-11-02.md) | 性格卡/演进引擎/自主权设计存照 |
| [多实例模式](docs/多实例模式-2026-11-02.md) | 双开零配置、端口自动选口、一键换绑 |
| [语音交流设计](docs/voice-communication-design.md) | TTS 出站 / ASR 入站链路 |

## 验证

```powershell
npm run typecheck              # 类型检查（主进程 + 渲染层）
npm run build                  # 构建
npm run check:p1               # 行为回归测试
npm run check:qq               # QQ 接入（OneBot 桥）回归：mock NapCat 端到端
npm run check:ghost-message    # 幽灵消息修复回归：未送达的回复必须从它的记忆里摘除
npm run check:multi-instance   # 多实例回归：端口自动选口 / 双开隔离 / 换绑链路（73 项）
npm run check:personality-gen  # 性格卡生成回归：预设免设定生成 / 失败原因可见（31 项）
npm run check:draft-judge      # 心里话判官回归：报警口径 / 只删不改 / 泄漏存照重放
npm run check:age-growth       # 年龄自然增长回归：自设生日认取 / 只涨不缩 / 快照口径
npm run check:humanization     # 拟人化行为大套件（2100+ 项断言）
npm run check:daytype          # 日型识别回归：法定节假日/调休补班/寒暑假 → 规划分日型过
npm run check:themes           # 主题完整性校验
npm run check:websearch        # 网络搜索回归（离线）；--live 变体真实出网冒烟
npm run fetch:napcat           # 下载内置 NapCat（npm run dist 会自动执行）
npm run dist                   # 打包（结束自动校验产物版本号与源码一致）
npm run check:onboarding       # 新手引导回归（静态断言：首次启动弹引导窗/必要配置/IPC 三件套）
```

## 新手引导

全新安装（读不到存档）首次启动时，先弹出引导页而不是直接放它出来。它被定义为**类人 AI 伙伴**——有性格、有想法、有自己生活，引导文案与视觉都围绕这个定位（深色科技感：玻璃拟态 + 光晕 + 呼吸光球，样式独立在 `onboarding.css`，不与控制台五肤互相污染）：

| 步骤 | 性质 | 内容 |
|------|------|------|
| 开始 | — | 它是谁、大约要花多久、配置只存本机、托盘可随时回来 |
| 心智 | **必要** | 三选一卡片：云端智能服务（OpenAI 兼容 + API Key）/ 本地 Ollama / 先试试看；带「测试连接」 |
| 它是谁 | 可选 | 性格基调（温柔/轻吐槽/安静/效率/自定义）+ 人生状态（念书/职场/自由）+ 一句话人生方向（lifeDossier） |
| 连接与偏好 | 可选 | QQ 小号扫码接入 + 主人白名单；界面主题；开机自启 |
| 完成 | — | 托盘/对话/控制台入口速查；未接大脑的提醒 |

- 每步配置即改即存（复用 AI/QQ/设置的现成 IPC），中途关窗 = 跳过，托盘右键「新手引导」随时重开
- 点「让它出现」才落 `onboardingDone`，之后正常启动
- 验收：`npm run check:onboarding`（41 项静态断言）+ `scripts/cdp-onboarding-e2e.mjs`（CDP 驱动真实 UI 走完五步，26 项断言，需 dev 环境带 `--remote-debugging-port`）

> **看打包产物里的 package.json**：用 `npm run dist` 后自带的校验输出，或 `node scripts/check-dist.mjs`（纯读，不落地任何文件）。
> **别在项目根目录跑 `npx asar extract-file ... package.json`**——它会把解出的文件写到当前目录，同名直接覆盖源文件（electron-builder 产物里的 package.json 已剥掉 scripts/devDependencies，覆盖进去 77 个 npm 脚本就全没了，2026-10-28 踩过一次）。

> QQ 接入说明：安装包通过 [extraResources] 携带 NapCat.Shell（`vendor/napcat`，构建时自动下载，可用 `NAPCAT_DOWNLOAD_BASE` 换镜像）。
> NapCat 依赖本机 QQ（NT 版）内核，应用会自动检测并在缺失时引导安装；QQ 客户端本身因授权原因不随包分发。

## License

[MIT](LICENSE)

---

<div align="center">

**如果觉得有用，请点个 Star 支持一下**

</div>
