---
title: "Kotlin Native 运行时不显示控制台"
date: 2023-08-20T15:45:33+08:00
draft: false
---

# Kotlin/Native run without console

## 链接设置

在 `build.gradle.kts` 加入链接设置

```kotlin
kotlin {
    val nativeTarget = mingwX64("native")
    nativeTarget.apply {
        binaries {
            executable {
//                linkerOpts("-mwindows")
                linkerOpts("-Wl,--subsystem,windows")
                // 二选一，貌似两种方法都可以
            }
        }
    }
}
```

## 
