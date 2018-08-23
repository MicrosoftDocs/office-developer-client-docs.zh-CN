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
ms.openlocfilehash: 923864c625cb032c3b351bb999ff7cc782eae588
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567165"
---
# <a name="sccountnotifications"></a>ScCountNotifications

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
确定大小，以字节为单位的数组的事件通知，并验证与数组关联的内存。
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
SCODE ScCountNotifications(
  int cntf,
  LPNOTIFICATION rgntf,
  ULONG FAR * pcb
);
```

## <a name="parameters"></a>参数

 _cntf_
  
> [in][通知](notification.md)结构由_rgntf_参数指示在阵列中的计数。 
    
 _rgntf_
  
> [in]指向其大小是确定**通知**结构的数组的指针。 
    
 _pcb_
  
> [输出]指向的大小，以字节为单位的数组_rgntf_参数指向的可选指针。 如果为空，则**ScCountNotifications**验证通知的数组。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 已成功确定计数。
    
MAPI_E_INVALID_PARAMETER
  
> 遇到无效的通知。
    
## <a name="remarks"></a>注解

如果_pcb_参数中传递 NULL，则**ScCountNotifications**函数仅验证通知的数组，但没有计数完成;如果在_pcb_传递一个非空值，则**ScCountNotifications**确定数组的大小，并将存储原因_pcb_。 _Pcb_参数必须为足够大，使其包含整个数组。 
  

