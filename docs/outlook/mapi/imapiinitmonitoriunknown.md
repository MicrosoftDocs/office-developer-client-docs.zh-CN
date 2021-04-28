---
title: IMAPIInitMonitor ： IUnknown
manager: lindalu
26ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIInitMonitor
api_type:
- COM
ms.assetid: ad71ea65-394d-4be2-a9da-cd23099bc2cc
description: IMAPIInitMonitor
Last modified: April 26, 2021
ms.openlocfilehash: dd17d50b04755d9d9c2a10a9b02cd821faf1f7ec
ms.sourcegitcommit: 289cececd9fa38a3f4b8a0d7fd1f86adb6be9689
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52062044"
---
# <a name="imapiinitmonitor--iunknown"></a>IMAPIInitMonitor ： IUnknown

**适用于：** Outlook 2013 |Outlook 2016 |Outlook 2019 年

有时，使用 MAPI 的应用程序可能想要知道初始化何时完成。 例如，它有多个线程，这些线程可以初始化 MAPI，或者为了响应正在初始化的 MAPI，应用程序希望执行一些工作，但不希望始终向上旋转 MAPI 堆栈。 初始化监视器通过 [CreateMAPIInitializationMonitor](createmapiinitializationmonitor.md) 对象提供此功能。

| 快速信息 | result |
|:-----|:-----|
|继承自：  <br/> |IUnknown  <br/> |
|实现者：  <br/> | OLMAPI32.DLL <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
|接口标识符：  <br/> |IID_IMAPIInitMonitor  <br/> |

## <a name="vtable-order"></a>Vtable 顺序

| function | 说明 |
|:-----|:-----|
|[IMAPIInitMonitor：：IsInitialized](imapiinitmonitor-isinitialized.md) <br/> |返回 MAPI 初始化的当前状态。  <br/> |
|[IMAPIInitMonitor：：Wait](imapiinitmonitor-wait.md) <br/> |在此线程上启动 BLOCKING 调用，该调用将在指定的毫秒数已过或 MAPI 已初始化时返回。  INFINITE 可用于无限等待。  <br/> |
|[IMAPIInitMonitor：：BeginWait](imapiinitmonitor-beginwait.md) <br/> |开始等待 MAPI 初始化或经过的指定毫秒数。 这将返回 IMAPIWaitResult 接口，该接口应调用"End"，以便开始等待。  这允许调用方控制我们在等待时被阻止的线程。 <br/> |
