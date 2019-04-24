---
title: ScCountNotifications
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ScCountNotifications
api_type:
- COM
ms.assetid: 13e80bdc-cb59-47a5-8de0-404e22f87f82
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f5298620239d1e42e4ba613c22a98f0cf6f7d457
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32351369"
---
# <a name="sccountnotifications"></a>ScCountNotifications

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
确定事件通知数组的大小 (以字节为单位), 并验证与该数组关联的内存。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
SCODE ScCountNotifications(
  int cntf,
  LPNOTIFICATION rgntf,
  ULONG FAR * pcb
);
```

## <a name="parameters"></a>参数

 _cntf_
  
> 实时由_rgntf_参数指示的数组中的[通知](notification.md)结构的计数。 
    
 _rgntf_
  
> 实时指向要确定其大小的**通知**结构数组的指针。 
    
 _pcb_
  
> 排除可选指针, 指向由_rgntf_参数指向的数组的大小 (以字节为单位)。 如果为 NULL, 则**ScCountNotifications**验证通知数组。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 已成功确定 Count。
    
MAPI_E_INVALID_PARAMETER
  
> 遇到无效的通知。
    
## <a name="remarks"></a>注解

如果在_pcb_参数中传递 NULL, 则**ScCountNotifications**函数仅验证通知数组, 但不会进行计数。如果在_pcb_中传递非 null 值, **ScCountNotifications**将确定数组的大小并存储原因_pcb_。 _pcb_参数的大小必须足以包含整个数组。 
  

