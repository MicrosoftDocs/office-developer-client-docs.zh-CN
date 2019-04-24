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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357482"
---
# <a name="sccopynotifications"></a>ScCopyNotifications

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将一组事件通知复制到单个内存块。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
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
  
> 实时由_rgntf_参数指示的数组中的[通知](notification.md)结构的计数。 
    
 _rgntf_
  
> 实时指向定义要复制的事件通知的**通知**结构数组的指针。 
    
 _pvDst_
  
> 排除指向返回的通知的指针。 
    
 _pcb_
  
> 排除一个可选指针, 指向一个变量, 存储_rgntf_参数指向的数组的大小 (以字节为单位)。 如果不为 NULL, 则将_pcb_参数设置为_pvDst_参数中存储的字节数。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 已成功复制事件通知。
    
E_INVALIDARG
  
> 遇到无效的通知。
    
## <a name="remarks"></a>注解

如果在_pcb_参数中传递了 NULL 值, 则不会执行任何复制;如果在_pcb_中传递一个非 null 值, 则**ScCopyNotifications**函数会将数组和数组本身的大小复制到单个内存块。 如果_pcb_不为 NULL, 则将其设置为_pvDst_参数中存储的字节数。 _pvDst_参数的大小必须足以包含整个数组。 
  

