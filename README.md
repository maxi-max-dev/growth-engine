# 内容增长引擎 · Max 版

复刻 engine.zcchr.com(飞书 AI 绝活大会展示的「企业流量增长引擎」)的 dashboard 工作流,**并把原版演示中规划、开源代码尚未包含的「自进化闭环」做成可运行实现**。

单文件、零依赖。

**在线版:https://maxi-max-dev.github.io/growth-engine/** (达人雷达页直达:[#radar](https://maxi-max-dev.github.io/growth-engine/#radar))

## 跑
```bash
cd ~/code/growth-engine
python3 -m http.server 8752
# 浏览器打开 http://127.0.0.1:8752/index.html
```
(直接双击 index.html 也行,但飞书 SDK 类的真接入需要 http 环境。)

## 有什么
- 首页:一个人的内容增长闭环(6 环)+ 今日 Top3 可解释打分卡
- 选题:三层(精准获客/沾边引流/涨粉热点)白盒可解释打分。同一引擎切 creator 模式 = 影石达人雷达
- 🎯 达人雷达(**真数据**,直达 `index.html#radar`):1,106 个真实 YouTube 频道的盲测回测,26 个已验证影石合作达人当标准答案。6 个真实合作达人被引擎排进前 5%(4.6× 随机基线),每张卡白盒可解释。数据源:`~/Documents/creator-radar` 7/6-7/7 回测
- 数据回流:12 条已发布作品的「发布前AI预判 vs 发布后实测」对照
- 🔁 自进化(核心):系统用皮尔逊相关自己找出哪些维度真和爆款相关,把打分权重朝那边挪。实测 MAE 17.3→1.5 单调下降,权重自动从「热度」搬到「相关性/差异化」
- 文案工坊:可选接 OpenAI 兼容大模型(设置页填,不填走本地模板降级)
- 素材工厂:Phase 0 未铺,真实现见 ai-xunjian

## 诚实说明
- 数据是种子样本,用于演示工作流。
- Cookie 采集只用于本次跑通/demo;**正式交付走官方开放平台 API(YouTube/星图/巨量/RSS),不上 cookie 爬。**
- 打分引擎、可解释卡、自进化闭环与数据源解耦,换源不改核心。

完整拆解 + 整合蓝图见 vault:`🚀项目/AI先锋大赛-影石/冯兴龙流量引擎-拆解与复刻-2026-07-16.md`
