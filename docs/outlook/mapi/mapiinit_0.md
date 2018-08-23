---
title: MAPIINIT_0
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MAPIINIT_0
api_type:
- COM
ms.assetid: 70739711-ff43-407d-bc8b-6baf7a476fef
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1eb4d7ac8d0287388a1bb76185f23636eddcf809
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591672"
---
# <a name="mapiinit0"></a>MAPIINIT_0

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
传达给[MAPIInitialize](mapiinitialize.md)函数的选项。 
  
|||
|:-----|:-----|
|头文件：  <br/> |MAPIX。H  <br/> |
   
```cpp
typedef struct
{
  ULONG ulVersion;
  ULONG ulFlags;
} MAPIINIT_0, FAR *LPMAPIINIT_0;

```

## <a name="members"></a>Members

 **ulVersion**
  
> 一个代表**MAPIINIT_0**结构的版本号的整数值。 **UlVersion**成员以供将来扩展并不表示的 MAPI 接口的版本。 目前， **ulVersion**必须设置为 MAPI_INIT_VERSION。 
    
 **ulFlags**
  
> 用于控制的 MAPI 会话初始化的标志位掩码。 可以设置以下标志：
    
MAPI_MULTITHREAD_NOTIFICATIONS 
  
> MAPI 应生成通知使用专用于通知而不用于调用**MAPIInitialize**的第一个线程处理线程。
    
MAPI_NT_SERVICE 
  
> 呼叫者作为 Windows 服务运行。 呼叫者的一项 Windows 服务不应设置此标志; 如未运行作为服务运行的呼叫者必须设置此标志。
    
MAPI_NO_COINIT
  
> 设置 MAPI_NO_COINT 标志，以便不会尝试通过调用[CoInitialize](http://msdn.microsoft.com/library/0f171cf4-87b9-43a6-97f2-80ed344fe376%28Office.15%29.aspx)初始化 COM **MAPIInitialize** 。 如果**MAPIINIT_0**结构与_ulFlags_设置为 MAPI_NO_COINIT 一起传递到**MAPIInitialize** ，MAPI 将假定 COM 已初始化和将绕过**CoInitialize**调用。
    
## <a name="remarks"></a>注解

多线程的客户端应设置 MAPI_MULTITHREAD_NOTIFICATIONS 标志。 如果未设置标志，用于使**MAPIInitialize**第一次调用的线程上会生成通知。 
  
有关何时将此标志设置以及如何在客户端中实现线程安全的详细信息，请参阅[MAPI 中的线程](threading-in-mapi.md)。 
  
## <a name="see-also"></a>另请参阅



[MAPIInitialize](mapiinitialize.md)


[MAPI 结构](mapi-structures.md)

