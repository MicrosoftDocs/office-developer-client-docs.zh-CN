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
ms.openlocfilehash: de31fe7d472b143ed8f3c108dca84a019b5ce103
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357293"
---
# <a name="mapiinit0"></a>MAPIINIT_0

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将选项传达给[MAPIInitialize](mapiinitialize.md)函数。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |MAPIX。水平  <br/> |
   
```cpp
typedef struct
{
  ULONG ulVersion;
  ULONG ulFlags;
} MAPIINIT_0, FAR *LPMAPIINIT_0;

```

## <a name="members"></a>Members

 **ulVersion**
  
> 一个整数值, 表示**MAPIINIT_0**结构的版本号。 **ulVersion**成员用于将来的扩展, 不代表 MAPI 接口的版本。 目前, **ulVersion**必须设置为 MAPI_INIT_VERSION。 
    
 **ulFlags**
  
> 用于控制 MAPI 会话初始化的标志位掩码。 可以设置以下标志:
    
MAPI_MULTITHREAD_NOTIFICATIONS 
  
> MAPI 应使用专用于通知处理的线程而不是第一个用于调用**MAPIInitialize**的线程生成通知。
    
MAPI_NT_SERVICE 
  
> 调用方以 Windows 服务的形式运行。 未作为 Windows 服务运行的调用方不应设置此标志;作为服务运行的调用方必须设置此标志。
    
MAPI_NO_COINIT
  
> 设置 MAPI_NO_COINT 标志, 以便**MAPIInitialize**不会尝试使用[CoInitialize](https://msdn.microsoft.com/library/0f171cf4-87b9-43a6-97f2-80ed344fe376%28Office.15%29.aspx)调用来初始化 COM。 如果将**MAPIINIT_0**结构传递到_ulFlags_设置为 MAPI_NO_COINIT 的**MAPIInitialize**中, MAPI 将假定 COM 已初始化, 并将绕过**CoInitialize**调用。
    
## <a name="remarks"></a>注解

多线程客户端应设置 MAPI_MULTITHREAD_NOTIFICATIONS 标志。 如果未设置标志, 则会在用于对**MAPIInitialize**的第一次调用的线程上生成通知。 
  
有关何时设置此标志以及如何在客户端中实现线程安全的详细信息, 请参阅[MAPI 中的线程处理](threading-in-mapi.md)。 
  
## <a name="see-also"></a>另请参阅



[MAPIInitialize](mapiinitialize.md)


[MAPI 结构](mapi-structures.md)

