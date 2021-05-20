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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437992"
---
# <a name="sccountnotifications"></a>ScCountNotifications

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
确定事件通知数组的大小（以字节为单位）并验证与该数组关联的内存。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
SCODE ScCountNotifications(
  int cntf,
  LPNOTIFICATION rgntf,
  ULONG FAR * pcb
);
```

## <a name="parameters"></a>参数

 _cntf_
  
> [in]_rgntf_ 参数指示的数组中的 [NOTIFICATION](notification.md)结构计数。 
    
 _rgntf_
  
> [in]指向要确定其大小的 **NOTIFICATION** 结构的数组的指针。 
    
 _这些_
  
> [out]  _Rgntf_ 参数指向的数组大小的可选指针（以字节为单位）。 如果为 NULL， **则 ScCountNotifications** 将验证通知数组。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 已成功确定计数。
    
MAPI_E_INVALID_PARAMETER
  
> 遇到无效通知。
    
## <a name="remarks"></a>备注

如果 NULL 在 _向该参数传递_，**则 ScCountNotifications** 函数仅验证通知数组，但不进行计数;If a non-null value is passed in _设置_， **ScCountNotifications** determines the size of the array and stores the cause _向。_ _此参数_ 必须足够大，以包含整个数组。 
  

