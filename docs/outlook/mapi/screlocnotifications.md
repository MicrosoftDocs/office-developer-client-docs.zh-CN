---
title: ScRelocNotifications
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ScRelocNotifications
api_type:
- COM
ms.assetid: 22de5d38-7be6-48b3-90a7-bc553dcdb042
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 81da4b77f0d2162a1119b7945b1e0ceb87ba9fb8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360709"
---
# <a name="screlocnotifications"></a>ScRelocNotifications

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在指定的事件通知数组中调整指针。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
SCODE ScRelocNotifications(
  int cntf,
  LPNOTIFICATION rgntf,
  LPVOID pvBaseOld,
  LPVOID pvBaseNew,
  ULONG FAR * pcb
);
```

## <a name="parameters"></a>参数

 _cntf_
  
> 实时由_rgntf_参数指示的数组中的[通知](notification.md)结构的计数。 
    
 _rgntf_
  
> 实时指向用于定义要在其中调整指针的事件通知的**通知**结构数组的指针。 
    
 _pvBaseOld_
  
> 实时指向由_rgntf_参数指示的数组的原始基址的指针。 
    
 _pvBaseNew_
  
> 实时**ScRelocNotifications**写入由_rgntf_参数指示的数组的新基址的位置。 
    
 _pcb_
  
> 排除指向由_pvBaseNew_参数指示的数组的大小 (以字节为单位) 的指针。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 已成功调整指针。
    
MAPI_E_INVALID_PARAMETER
  
> 遇到无效的通知。
    
## <a name="remarks"></a>注解

**ScRelocNotifications**函数的_pcb_参数是可选的。 
  
## <a name="see-also"></a>另请参阅



[ScRelocProps](screlocprops.md)

