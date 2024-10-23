---
sidebar_position: 0
---

# NeoGradle 文档

这里是[NeoGradle]官方文档, 一个[Gradle]插件用于开发 [NeoForge] 和模组

本文档只适用于NeoForge, **这不是一个Java,Groovy/Kotlin教程**.

如果想对本文档做出贡献,请阅读 [为Docs做贡献][contributing].

## 添加插件

NeoGradle 可以通过在 `settings.gradle` 中添加NeoForge的maven仓库添加进repositories中,在 `build.gradle` 中使用 `plugins` 块:

```gradle
// 在 settings.gradle 中
pluginManagement {
    repositories {
        // ...

        // 添加 NeoForge maven仓库
        maven { url = 'https://maven.neoforged.net/releases' }
    }
}
```

```gradle
// 在 build.gradle 中
plugins {
    // 添加 NeoGradle userdev p插件
    id 'net.neoforged.gradle.userdev' version '7.0.120'

    // ...
}
```

:::注意
虽然你可以使用NeoGradle插件的版本范围,但是不建议这样做,因为这样可能会导致更频繁的反编译和重新编译以及可能的行为更改,你可以在我们的 [列表][gradlelisting]查看.
:::

## 添加 NeoForge 依赖

为了在你的开发环境中获取反编译的Minecraft环境和NeoForge类,你只需要将 `net.neoforged:neoforge` 依赖项添加到运行时和编译时依赖项配置中(它通常是 `implementation`):

```gradle
dependencies {
    // highlight-next-line
    implementation 'net.neoforged:neoforge:20.6.43-beta'
}
```

:::注意
[NeoForge's MDK][mdk] 通过[gradle.properties][properties]设置NeoForge版本. 您可以在我们的网站找到最新的NeoForge版本[列表][neolisting].
:::

[NeoGradle]: https://github.com/neoforged/NeoGradle
[Gradle]: https://gradle.org/
[NeoForge]: https://github.com/neoforged/NeoForge
[contributing]: /contributing
[gradlelisting]: https://projects.neoforged.net/neoforged/neogradle
[neolisting]: https://projects.neoforged.net/neoforged/neoforge
[mdk]: https://github.com/neoforged/MDK
[properties]: https://github.com/neoforged/MDK/blob/a52ce16c8a1dd2d656edac482376f33385fe912c/gradle.properties#L19
