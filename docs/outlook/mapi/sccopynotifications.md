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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 28a802ffc43b08d3e2ec2be26dd98fa78f474d91
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778680"
---
# <a name="sccopynotifications"></a>ScCopyNotifications

  
  
**适用于**： Outlook 
  
将一组事件通知的复制到单个块的内存。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in][通知](notification.md)结构由_rgntf_参数指示在阵列中的计数。 
    
 _rgntf_
  
> [in]为数组定义要复制的事件通知的**通知**结构的指针。 
    
 _pvDst_
  
> [输出]返回的通知的指针。 
    
 _pcb_
  
> [输出]存储到其中的大小，以字节为单位的数组的_rgntf_参数指向变量的可选指针。 如果不为 NULL， _pcb_参数设置为_pvDst_参数中存储的字节数。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 已成功复制事件通知。
    
E_INVALIDARG
  
> 遇到无效的通知。
    
## <a name="remarks"></a>备注

如果_pcb_参数中传递 NULL，则会执行任何复制;如果在_pcb_传递一个非空值，则**ScCopyNotifications**函数将数组和阵列本身的大小复制到一个独立的内存块中。 如果_pcb_不为 NULL，则将它设置为_pvDst_参数中存储的字节数。 _PvDst_参数必须为足够大，使其包含整个数组。 
  

