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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: bb4ff6a128b9fed29ff0be5325c21e5600389740
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778732"
---
# <a name="screlocnotifications"></a>ScRelocNotifications

  
  
**适用于**： Outlook 
  
调整指定的事件通知阵列中的指针。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapiutil.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
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
  
> [in][通知](notification.md)结构由_rgntf_参数指示在阵列中的计数。 
    
 _rgntf_
  
> [in]定义在其中指针是要调整的事件通知的**通知**结构的数组的指针。 
    
 _pvBaseOld_
  
> [in]指向原始基址_rgntf_参数指示的数组。 
    
 _pvBaseNew_
  
> [in]**ScRelocNotifications**向其中写入_rgntf_参数指示的数组的新基址位置。 
    
 _pcb_
  
> [输出]指向的大小，以字节为单位指示_pvBaseNew_参数的数组。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 已成功调整指针。
    
MAPI_E_INVALID_PARAMETER
  
> 遇到无效的通知。
    
## <a name="remarks"></a>备注

**ScRelocNotifications**函数_pcb_参数是可选的。 
  
## <a name="see-also"></a>另请参阅



[ScRelocProps](screlocprops.md)

