---
title: UlRelease
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.UlRelease
api_type:
- COM
ms.assetid: 95db96ef-f95f-41da-b216-f717c23bffd2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 288e34a159db48b1344524b87f02b045259f1565
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415843"
---
# <a name="ulrelease"></a>UlRelease

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供另一种调用 OLE 方法 **IUnknown：：Release 的方法**。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
ULONG UlRelease(
  LPVOID punk
);
```

## <a name="parameters"></a>参数

 _punk_
  
> [in]指向从 **IUnknown** 接口派生的接口的指针，即任何 MAPI 接口。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。 
    
MAPI_E_CALL_FAILED 
  
> 意外或未知来源的错误阻止了操作完成。
    
## <a name="remarks"></a>备注

引用计数是指向要释放的对象的现有指针数。 
  
如果  _punk_ 参数为 NULL，函数将立即返回，而不调用 **IUnknown：：Release**
  
 **UlRelease** 返回 **IUnknown：：Release** 方法返回的值，该值可以等于要释放的对象的引用计数。 
  
有关 **IUnknown：：Release** 有关详细信息，请参阅 [实现 IUnknown 接口](implementing-the-iunknown-interface.md)。 
  

