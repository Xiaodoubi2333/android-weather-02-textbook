# android-weather-02-textbook v1.0

教材《第一行代码》coolweather 项目的复刻版（课程「项目 2」）：严格按课本环境搭建 Gradle 与包结构，先把地区选择界面画出来，业务逻辑留待后续版本。

包名 `com.oldweatherapp.android`，`compileSdk 34 / minSdk 23`。

## 文件结构

```text
app/src/main/java/com/coolweather/android/
├── MainActivity.java      仅 setContentView，无业务逻辑
└── db/
    ├── Province.java      省
    ├── City.java          市（provinceId 关联）
    └── County.java        县（cityId 关联）
app/src/main/res/layout/
├── activity_main.xml      主界面
└── choose_area.xml        省 / 市 / 县选择界面（已画完，未接入逻辑）
app/build.gradle           课本版依赖：litepal / okhttp / gson / glide / appcompat
```

## 启动

1. Android Studio 打开工程，Gradle 同步；
2. 运行 `app` 模块 —— 当前只渲染 `activity_main.xml`，`choose_area.xml` 需手动改 `setContentView` 才能预览；
3. 这一版没有网络请求，不产生任何数据。

依赖：`appcompat 1.0.2`、`constraintlayout 1.1.3`、`litepal 1.3.2`、`okhttp 3.4.1`、`gson 2.7`、`glide 3.7.0`。

## 功能落点表

| # | 功能 | 状态 | 落点 |
|---|---|---|---|
| 1 | 课本环境 Gradle 配置 | 完成 | `app/build.gradle`、`build.gradle` |
| 2 | 地区三表实体 | 完成 | `db/` 三个类 |
| 3 | 地区选择界面布局 | 完成 | `res/layout/choose_area.xml` |
| 4 | 地区选择逻辑 | 未实现 | 后续补 `ChooseAreaFragment` |
| 5 | 天气接口与解析 | 未实现 | — |

## 版本记录

### v0.1 · 建库

- `chore: 初始化仓库（LICENSE / .gitignore）`：网页端建库。

### v0.2 · 工程首推

- `feat: 按课本环境导入 coolweather 工程`：工程首次推送。

### v1.0 · 课本环境对齐

- `build: 严格按教材版本锁定 build.gradle 与依赖`：按教材锁定依赖与插件版本，三张表实体与 `choose_area` 布局落地。

## 已知限制

- `applicationId` 与 [`android-weather-01-skeleton`](https://github.com/Xiaodoubi2333/android-weather-01-skeleton)、[`android-weather-03-source`](https://github.com/Xiaodoubi2333/android-weather-03-source) 相同，三者不可同时安装。
- 属于「样式与结构先行」的中间版本，功能完整版见 [`android-weather-05-navigation`](https://github.com/Xiaodoubi2333/android-weather-05-navigation)。
