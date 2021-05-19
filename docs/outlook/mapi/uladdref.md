---
title: UlAddRef
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.UlAddRef
api_type:
- COM
ms.assetid: 9b897cbc-90b2-4c60-b5f1-dc78e7e7952d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f9e55153830dbe41a2b4a48454157c900d96cf90
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432833"
---
# <a name="uladdref"></a>UlAddRef

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供另一种调用 OLE 方法 **IUnknown：：AddRef 的方法**。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
ULONG UlAddRef(
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

 **UlAddRef** 返回 **IUnknown：：AddRef** 方法返回的值，这是接口的引用计数的新值。 该值为非零。 
  
有关 **IUnknown：：AddRef** 详细信息，请参阅 [实现 IUnknown 接口](implementing-the-iunknown-interface.md)。 
  

