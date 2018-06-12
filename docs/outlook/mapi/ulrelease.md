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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 5b34e2c21ac967b0874872986c0cf484750f4e72
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779037"
---
# <a name="ulrelease"></a>UlRelease

  
  
**适用于**： Outlook 
  
提供一种方法来调用 OLE 方法**IUnknown::Release**。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
ULONG UlRelease(
  LPVOID punk
);
```

## <a name="parameters"></a>参数

 _punk_
  
> [in]从**IUnknown**接口，换句话说任何 MAPI 接口派生的接口的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。 
    
MAPI_E_CALL_FAILED 
  
> 意外或未知的原点出现错误，无法完成操作。
    
## <a name="remarks"></a>备注

引用计数是现有指向必须释放的对象数。 
  
如果_punk_参数为 NULL，则函数返回立即而无需调用**IUnknown::Release**
  
 **UlRelease**返回返回**IUnknown::Release**方法，该数据库可以等于必须释放的对象的引用计数的值。 
  
有关**IUnknown::Release**的详细信息，请参阅[实现 IUnknown 接口](implementing-the-iunknown-interface.md)。 
  

