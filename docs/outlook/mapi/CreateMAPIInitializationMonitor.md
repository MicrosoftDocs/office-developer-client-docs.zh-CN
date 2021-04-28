---
title: CreateMAPIInitializationMonitor
manager: lindalu
ms.date: 04/26/2021
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIWAITRESULT
api_type:
- COM
ms.assetid: 32a9758a-395d-4526-9610-3e4eeaf78c96
description: MAPI 初始化监视器
Last modified: April 26, 2021
ms.openlocfilehash: da7c48a6b026ccd4cbe4cbac192a1a0760202835
ms.sourcegitcommit: 289cececd9fa38a3f4b8a0d7fd1f86adb6be9689
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52062051"
---
# <a name="createmapiinitializationmonitor"></a>CreateMAPIInitializationMonitor

**适用于：** Outlook 2016 |Outlook 2019 年
  
## <a name="mapi-initialization-monitor"></a>MAPI 初始化监视器

有时，使用 MAPI 的应用程序可能想要知道初始化何时完成。 例如，它有多个线程，这些线程可以初始化 MAPI，或者为了响应正在初始化的 MAPI，应用程序希望执行一些工作，但不希望始终旋转 MAPI 堆栈。 初始化监视器通过从 (导出的函数OLMAPI32.DLL) 和下面介绍的一些简单接口提供此功能。

这是从 OLMAPI32.DLL导出的入口点，这允许调用方检索接口以查询当前初始化状态、设置回调以完成初始化或阻止当前线程，直到完成。 从此 API 返回的对象可重用且线程安全，并且可以从任何线程调用，而不只是从检索它的线程调用。 此外，与 MAPI 公开的其他对象不同，只要加载 DLL，此对象就有效，它可以跨初始化会话重新使用，并且可在调用 MAPIInitialize 之前或之后使用。 通过 COM 标准 HRESULT 返回成功或失败，并将 out 参数分配给 IMAPIInitMonitor 的实例。

```cpp
HRESULT CreateMAPIInitializationMonitor(IMAPIInitMonitor** ppInitMonitor); 
```
#### <a name="hresult-stdapicalltype-createmapiinitializationmonitorimapiinitmonitor-ppinitmonitor"></a>HRESULT STDAPICALLTYPE CreateMapiInitializationMonitor (IMAPIInitMonitor ppInitMonitor) 

通过从 OLMAPI32.DLL 导出的此入口点，调用方可以检索接口以查询当前初始化状态、设置初始化完成回调或阻止当前线程直到完成。 从此 API 返回的对象可重用且线程安全，并且可以从任何线程调用，而不只是从检索它的线程调用。 此外，与 MAPI 公开的其他对象不同，只要加载 DLL，此对象就有效，它可以跨初始化会话重新使用，并且可在调用 MAPIInitialize 之前或之后使用。 通过 COM 标准 HRESULT 返回成功或失败，并将 out 参数分配给 IMAPIInitMonitor 的实例。
  
## <a name="quick-info"></a>快速信息

| 标识符 | result |
|:-----|:-----|
|导出者：  <br/> |olmapi32.dll  <br/> |
|调用者：  <br/> |客户端  <br/> |
|实现者：  <br/> |Outlook  <br/> |

## <a name="parameters"></a>参数
  
 _ppInitMonitor_
> [out]用于接收新创建的 MAPI 初始化监视器实例的指针。
  
## <a name="return-values"></a>返回值

S_OK
> 已成功创建初始化监视器的新实例。

E_OUTOFMEMORY
> 没有足够的内存来为新对象创建文件。

## <a name="see-also"></a>另请参阅
[IMAPIInitMonitor](imapiinitmonitoriunknown.md)

[IMAPIWaitResult](imapiwaitresultiunknown.md)
