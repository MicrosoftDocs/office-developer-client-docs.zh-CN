---
title: MAPIInitialize
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPIInitialize
api_type:
- HeaderDef
ms.assetid: b9584226-79d2-4d83-8f31-dbfbc50f16c5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6464f16d9ad73b332ff20dc007ef162b9525c6d5
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411174"
---
# <a name="mapiinitialize"></a>MAPIInitialize

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
递增 mapi 子系统引用计数并为 mapi DLL 初始化全局数据。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapix  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
   
```cpp
HRESULT MAPIInitialize(
  LPVOID lpMapiInit
);
```

## <a name="parameters"></a>参数

 _lpMapiInit_
  
> 实时指向[MAPIINIT_0](mapiinit_0.md)结构的指针。 可以将_lpMapiInit_参数设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> MAPI 子系统已成功初始化。
    
## <a name="remarks"></a>说明

**MAPIInitialize**函数递增 mapi 子系统的 mapi 引用计数, [MAPIUninitialize](mapiuninitialize.md)函数递减内部引用计数。 因此, 对一个函数的调用次数必须等于对另一个函数的调用次数。 如果 MAPI 以前尚未初始化, 则**MAPIInitialize**将返回 S_OK。 
  
在进行任何其他 MAPI 呼叫之前, 客户端或服务提供程序必须调用**MAPIInitialize** 。 如果不这样做, 则会导致客户端或服务提供程序调用返回 MAPI_E_NOT_INITIALIZED 值。 
  
从多线程应用程序调用**MAPIInitialize**时, 请将_lpMapiInit_参数设置为以下声明的[MAPIINIT_0](mapiinit_0.md)结构: 
  
 **MAPIINIT_0**MAPIINIT = {0, MAPI_MULTITHREAD_NOTIFICATIONS} 
  
和呼叫: 
  
 **MAPIInitialize**(&amp;MAPIINIT); 
  
声明此结构时, MAPI 将创建单独的线程来处理通知窗口, 这将一直持续到初始化引用计数降为零。 Windows 服务必须将_lpMapiInit_指向的**MAPIINIT_0**结构的**ulflags**成员设置为 MAPI_NT_SERVICE。 
  
> [!NOTE]
> 无法从 Win32 **DllMain**函数或任何其他创建或终止线程的函数中调用**MAPIInitialize**或**MAPIUninitialize** 。 有关详细信息, 请参阅[使用线程安全对象](using-thread-safe-objects.md)。 
  
 **MAPIInitialize**不会返回任何扩展的错误消息。 与大多数其他 MAPI 调用不同的是, 其返回值的含义严格定义为与失败的初始化的特定步骤相对应: 
  
1. 检查参数和标志。
    
    MAPI_E_INVALID_PARAMETER 或 MAPI_E_UNKNOWN_FLAGS。 呼叫者传递了无效参数或标志。
    
2. 初始化 MAPI 所需的注册表项, 并确认操作系统的类型。 仅当客户端进程在 Windows 下作为服务运行, 并在**MAPIINIT_0**结构中设置 MAPI_NT 服务标记时, 才会发生此步骤。 
    
    MAPI_E_TOO_COMPLEX。 调用进程是一种 Windows 服务, 无法初始化 MAPI 所需的注册表项。 
    
    应用程序事件日志中可能提供了其他信息。
    
3. 请检查 MAPI 与 ole 的兼容性, 然后初始化 ole。
    
1. 检查当前版本的 OLE 和 MAPI 之间的兼容性。 
    
    MAPI_E_VERSION。 在工作站上安装的 OLE 版本与此版本的 MAPI 不兼容。
    
2. 初始化 OLE。 
    
    在此步骤中, 此函数可能返回未在此处列出的错误代码。 此处_未_列出的任何错误都应假定为来自 OLE 函数**CoInitialize**。
    
4. 初始化每个进程的全局变量。
    
    MAPI_E_SESSION_LIMIT。 MAPI 设置特定于当前进程的上下文。 如果进程数超过一定数量, 或者如果可用内存耗尽, 则在 Win16 上可能会发生失败。
    
5. 初始化所有进程的共享全局变量。
    
    MAPI_E_NOT_ENOUGH_RESOURCES。 可用的系统资源不足, 无法完成此操作。
    
6. 初始化通知引擎, 如果 MAPI_MULTITHREAD_NOTIFICATIONS 标志请求, 则会创建其窗口及其线程。 
    
    MAPI_E_INVALID_OBJECT。 如果系统资源耗尽, 可能会失败。 
    
7. 加载并初始化配置文件提供程序。 验证**MAPIInitialize**是否可以访问存储配置文件数据的注册表项。 
    
    MAPI_E_NOT_INITIALIZED。 配置文件提供程序遇到错误。 
    
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|ContentsTableListCtrl  <br/> ||MFCMAPI 使用**MAPIInitialize**方法在后台线程上初始化 MAPI, 以执行某些表处理。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

