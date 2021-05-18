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
  
增加 MAPI 子系统引用计数并初始化 MAPI DLL 的全局数据。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapix.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序  <br/> |
   
```cpp
HRESULT MAPIInitialize(
  LPVOID lpMapiInit
);
```

## <a name="parameters"></a>参数

 _lpMapiInit_
  
> [in]指向结构 [MAPIINIT_0](mapiinit_0.md) 指针。 可以将  _lpMapiInit_ 参数设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> MAPI 子系统已成功初始化。
    
## <a name="remarks"></a>备注

**MAPIInitialize** 函数增加 MAPI 子系统的 MAPI 引用计数，[而 MAPIUninitialize](mapiuninitialize.md)函数会缩小内部引用计数。 因此，对一个函数的调用数必须等于对另一个函数的调用数。 **如果 MAPI 尚未S_OK，MAPIInitialize** 将返回值。 
  
客户端或服务提供商必须先调用 **MAPIInitialize，** 然后才能进行任何其他 MAPI 调用。 如果不这样做，客户端或服务提供商调用将返回MAPI_E_NOT_INITIALIZED值。 
  
从多 **线程应用程序调用 MAPIInitialize** 时，将 _lpMapiInit_ 参数设置为 [](mapiinit_0.md)MAPIINIT_0 结构，声明如下： 
  
 **MAPIINIT_0** MAPIINIT= { 0，MAPI_MULTITHREAD_NOTIFICATIONS} 
  
和 调用： 
  
 **MAPIInitialize** (&amp; MAPIINIT) ; 
  
声明此结构时，MAPI 将创建一个单独的线程来处理通知窗口，该窗口将一直持续到初始化引用计数为零。 Windows 服务必须将 _lpMapiInit_ 指向的 MAPIINIT_0 **ulflags** 成员设置为 MAPI_NT_SERVICE。 
  
> [!NOTE]
> 不能从 Win32 **DllMain** 函数或其他创建或终止线程的函数中调用 **MAPIInitialize** 或 **MAPIUninitialize。** 有关详细信息，请参阅使用对象 [Thread-Safe对象](using-thread-safe-objects.md)。 
  
 **MAPIInitialize** 不会返回任何扩展的错误信息。 与大多数其他 MAPI 调用不同，其返回值的含义严格定义为对应于失败的初始化的特定步骤： 
  
1. 检查参数和标志。
    
    MAPI_E_INVALID_PARAMETER 或 MAPI_E_UNKNOWN_FLAGS。 调用方传递的参数或标志无效。
    
2. 初始化 MAPI 所需的注册表项并确认操作系统的类型。 只有当客户端进程作为 Windows 下的服务运行，并设置 MAPI_NT 结构中的服务标记时，MAPIINIT_0 **执行此步骤** 。 
    
    MAPI_E_TOO_COMPLEX。 调用过程是 Windows 服务，无法初始化 MAPI 所需的注册表项。 
    
    应用程序事件日志中可能提供了其他信息。
    
3. 检查 MAPI 与 OLE 的兼容性，然后初始化 OLE。
    
1. 检查当前版本的 OLE 和 MAPI 之间的兼容性。 
    
    MAPI_E_VERSION。 工作站上安装的 OLE 版本与此版本的 MAPI 不兼容。
    
2. 初始化 OLE。 
    
    仅在此步骤中，此函数可能会返回此处未列出的错误代码。 应  _假定_ 此处未列出的任何错误来自 OLE 函数 **CoInitialize**。
    
4. 初始化每个进程全局变量。
    
    MAPI_E_SESSION_LIMIT。 MAPI 设置特定于当前进程的上下文。 如果进程数超过特定数量，则 Win16 上可能发生故障;如果可用内存已耗尽，则在任何系统上可能发生故障。
    
5. 初始化所有进程共享的全局变量。
    
    MAPI_E_NOT_ENOUGH_RESOURCES。 没有足够的系统资源来完成该操作。
    
6. 初始化通知引擎，创建其窗口及其线程（如果由 MAPI_MULTITHREAD_NOTIFICATIONS 请求）。 
    
    MAPI_E_INVALID_OBJECT。 如果系统资源用尽，可能会失败。 
    
7. 加载并初始化配置文件提供程序。 验证 **MAPIInitialize** 能否访问存储配置文件数据的注册表项。 
    
    MAPI_E_NOT_INITIALIZED。 配置文件提供程序遇到错误。 
    
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> ||MFCMAPI 使用 **MAPIInitialize** 方法初始化后台线程上的 MAPI 以执行一些表处理。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

