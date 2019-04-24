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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32315370"
---
# <a name="uladdref"></a>UlAddRef

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供了调用 OLE 方法**IUnknown:: AddRef**的另一种方法。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
ULONG UlAddRef(
  LPVOID punk
);
```

## <a name="parameters"></a>参数

 _punk_
  
> 实时指向从**IUnknown**接口派生的接口的指针, 换句话说, 是任何 MAPI 接口。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回了所需的值或值。 
    
MAPI_E_CALL_FAILED 
  
> 意外或未知来源的错误阻止操作完成。
    
## <a name="remarks"></a>注解

 **UlAddRef**返回由**IUnknown:: AddRef**方法返回的值, 它是接口的引用计数的新值。 值为非零值。 
  
有关**IUnknown:: AddRef**的详细信息, 请参阅[实现 IUnknown 接口](implementing-the-iunknown-interface.md)。 
  

