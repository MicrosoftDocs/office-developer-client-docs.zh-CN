---
title: ScCopyNotifications
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ScCopyNotifications
api_type:
- COM
ms.assetid: ac31cf65-a2bc-4c8e-91a4-d2903aa98776
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 08b9b954f856d64214947d81cf700adee42bcce4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435920"
---
# <a name="sccopynotifications"></a>ScCopyNotifications

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将一组事件通知复制到单个内存块。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
SCODE ScCopyNotifications(
  int cntf,
  LPNOTIFICATION rgntf,
  LPVOID pvDst,
  ULONG FAR * pcb
);
```

## <a name="parameters"></a>参数

 _cntf_
  
> [in]_rgntf_ 参数指示的数组中的 [NOTIFICATION](notification.md)结构计数。 
    
 _rgntf_
  
> [in]指向定义要复制的事件通知的 **NOTIFICATION** 结构的数组的指针。 
    
 _pvDst_
  
> [out]指向返回的通知的指针。 
    
 _这些_
  
> [out]指向变量的可选指针，其中存储  _了 rgntf_ 参数指向的数组的大小（以字节为单位）。 如果不为 NULL，  _则向该_  _pvDst_ 参数中存储的字节数设置 pv 参数。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 已成功复制事件通知。
    
E_INVALIDARG
  
> 遇到无效通知。
    
## <a name="remarks"></a>备注

如果 null 在  _向该参数传递_ ，则不执行任何复制;如果将非 null 值传入  _到_ 中，则 **ScCopyNotifications** 函数将数组和数组本身的大小复制到单个内存块。 如果  _pv_ 不为 NULL，则设置为  _pvDst_ 参数中存储的字节数。 _pvDst_ 参数必须足够大，以包含整个数组。 
  

