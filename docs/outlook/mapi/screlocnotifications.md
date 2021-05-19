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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415199"
---
# <a name="screlocnotifications"></a>ScRelocNotifications

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
调整指定事件通知数组中的指针。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapiutil.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in]_rgntf_ 参数指示的数组中的 [NOTIFICATION](notification.md)结构计数。 
    
 _rgntf_
  
> [in]指向定义要调整指针的事件通知的 **NOTIFICATION** 结构的数组的指针。 
    
 _pvBaseOld_
  
> [in]指向由 rgntf 参数指示的数组  _的原始基地址_ 的指针。 
    
 _pvBaseNew_
  
> [in] **ScRelocNotifications** 写入  _rgntf_ 参数指示的数组的新基地址的位置。 
    
 _这些_
  
> [out]指向  _pvBaseNew_ 参数指示的数组的大小（以字节为单位）的指针。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 指针已成功调整。
    
MAPI_E_INVALID_PARAMETER
  
> 遇到无效通知。
    
## <a name="remarks"></a>备注

**ScRelocNotifications** 函数的 _为可选_ 参数。 
  
## <a name="see-also"></a>另请参阅



[ScRelocProps](screlocprops.md)

