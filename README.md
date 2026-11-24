# inknews-downloads
InkNews v0.1 — Android 墨水屏 RSS 阅读器
为文石 X3 Pro 优先设计的 Android 原生项目，首页按 国际 / 政治 / 科技 / 文化 / 经济 / 其他 分类。支持多语言 RSS/Atom 新闻源；界面是中文，但文章保留原语言。
已实现
Jetpack Compose 简洁黑白主题、主题筛选和文章列表
内置 5 个英文 RSS 示例来源（网络可达性随地区及媒体政策变化）
自定义添加/删除 HTTPS RSS 或 Atom，手动选择归属主题
刷新订阅（有 12 秒超时），解析文章标题、摘要、RSS 提供的正文
离线缓存最近最多 400 篇 RSS 文本、收藏、文章字号调节
浏览器打开文章原文
无账号、无服务端、无广告和分析 SDK
明确限制
RSS 不一定提供全文：本文显示的是订阅源给出的内容；没有自动网页全文提取。
不是全文离线网页镜像；图片不缓存；没有翻译、笔记和手写。
新增 RSS 只在刷新后取回文章；新闻主题为手动按来源分类，没有 AI 自动分类。
目前所有缓存通过 SharedPreferences JSON 保存在本机，适合试用，不是大规模阅读库。
尚未在文石 X3 Pro 实机验证刷新和触控性能。
当前下载包是源码，不是 APK；当前环境缺少 Android SDK / Gradle，未能执行编译验证。
用 Android Studio 打开
安装 Android Studio（建议近期稳定版），并安装 Android SDK Platform 35、Build-Tools 及 JDK 17。
解压 ZIP，选择 Open 并选择 InkNews/ 根目录。
本 ZIP 由于构建环境未包含官方 gradle-wrapper.jar，所以未放入官方 wrapper 二进制。请先在本机安装 Gradle 8.13，打开项目目录的 Terminal，运行：
gradle wrapper --gradle-version 8.13
./gradlew :app:assembleDebug
​
Windows 将第二条替换为 gradlew.bat :app:assembleDebug。
构建成功后，安装 app/build/outputs/apk/debug/app-debug.apk 到阅读器。
Android Studio 也可选择 USB 调试的设备，点击 Run。
如 Gradle Sync 显示版本兼容问题，请保留完整报错后调整，不要直接把所有插件升级成最新版。
技术栈
Kotlin 2.2.20, Android Gradle Plugin 8.13.2, Gradle 8.13
Compose BOM 2025.10.01, minSdk 26, targetSdk 35
Android XmlPullParser，不使用第三方 RSS SDK
许可与来源
这是全新编写的独立 Android 原型，没有复制 bg4hsi/rmnews 的源代码、素材或二进制。借鉴的是「电子墨水屏友好的新闻阅读器」这一通用产品理念；后续如复用第三方代码，须保留相应许可证及署名。
