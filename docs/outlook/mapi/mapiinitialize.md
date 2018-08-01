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
ms.openlocfilehash: d22c24088960debcd18ccd818dad23656f6a01f2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776382"
---
# <a name="mapiinitialize"></a>MAPIInitialize

  
  
**适用于**： Outlook 
  
增加 MAPI 子系统引用计数和 MAPI dll 初始化全局数据。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapix.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序  <br/> |
   
```cpp
HRESULT MAPIInitialize(
  LPVOID lpMapiInit
);
```

## <a name="parameters"></a>参数

 _lpMapiInit_
  
> [in]指向[MAPIINIT_0](mapiinit_0.md)结构。 _LpMapiInit_参数可以设置为 NULL。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> MAPI 子系统初始化成功。
    
## <a name="remarks"></a>说明

MAPI 引用计数 MAPI 子系统和[MAPIUninitialize](mapiuninitialize.md)函数递减**MAPIInitialize**函数增量内部引用计数。 因此，一个函数调用次数必须等于到其他呼叫的数目。 如果未以前初始化 MAPI， **MAPIInitialize**返回 S_OK。 
  
客户端或服务提供程序必须在进行任何其他 MAPI 调用之前调用**MAPIInitialize** 。 否则，使客户端或服务提供程序调用 MAPI_E_NOT_INITIALIZED 值返回。 
  
从多线程应用程序中调用**MAPIInitialize**时, 将_lpMapiInit_参数设置为[MAPIINIT_0](mapiinit_0.md)结构的声明，如下所示： 
  
 **MAPIINIT_0**MAPIINIT = {0，MAPI_MULTITHREAD_NOTIFICATIONS} 
  
和呼叫： 
  
 **MAPIInitialize**(&amp;MAPIINIT); 
  
在声明此结构，MAPI 将创建一个单独的线程，来处理通知窗口中，将一直为零属于 initialize 引用计数。 Windows 服务，必须设置所指的_lpMapiInit_到 MAPI_NT_SERVICE **MAPIINIT_0**结构的**ulflags**成员。 
  
> [!NOTE]
> 不能调用**MAPIInitialize**或从**MAPIUninitialize** Win32 **DllMain**函数或创建或终止线程的任何其他函数中。 有关详细信息，请参阅[使用线程安全对象](using-thread-safe-objects.md)。 
  
 **MAPIInitialize**不返回任何扩展的错误的信息。 与大多数其他 MAPI 调用，其返回值的含义严格定义对应于初始化失败的特定步骤： 
  
1. 检查参数和标志。
    
    MAPI_E_INVALID_PARAMETER 或 MAPI_E_UNKNOWN_FLAGS。 呼叫者传递参数无效或标志。
    
2. 初始化 MAPI 所需的注册表项，并确认操作系统的类型。 此步骤只发生如果客户端进程作为下 Windows 服务运行，并将 MAPI_NT 服务标志设置**MAPIINIT_0**结构中。 
    
    MAPI_E_TOO_COMPLEX。 调用过程是一个 Windows 服务，并且无法初始化 MAPI 所需的注册表项。 
    
    其他信息可能会在应用程序事件日志中可用。
    
3. 检查 OLE，使用 MAPI 的兼容性，然后初始化 OLE。
    
1. MAPI 和 OLE 当前版本之间的兼容性检查。 
    
    MAPI_E_VERSION。 OLE 工作站上安装的版本不是与此版本的 MAPI 兼容的。
    
2. 初始化 OLE。 
    
    在此步骤仅，此函数可以返回未在此处列出的错误代码。 任何错误_未_列出此处应假定来自 OLE 函数**CoInitialize**。
    
4. 初始化每个过程的全局变量。
    
    MAPI_E_SESSION_LIMIT。 MAPI 将上下文设置特定于当前过程。 可能会失败或任何系统上 Win16 如果进程数超过特定数量，如果耗尽可用内存。
    
5. 初始化共享所有进程的全局的变量。
    
    MAPI_E_NOT_ENOUGH_RESOURCES。 没有足够的系统资源已无法完成操作。
    
6. 初始化通知引擎，创建其窗口和其线程，如果请求 MAPI_MULTITHREAD_NOTIFICATIONS 标志。 
    
    MAPI_E_INVALID_OBJECT。 如果用完系统资源可能失败。 
    
7. 加载并初始化配置文件提供程序。 验证**MAPIInitialize**可以访问存储配置文件数据的注册表项。 
    
    MAPI_E_NOT_INITIALIZED。 配置文件提供程序出错。 
    
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|ContentsTableListCtrl.cpp  <br/> ||MFCMAPI 使用**MAPIInitialize**方法在后台线程执行一些表处理初始化 MAPI。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

