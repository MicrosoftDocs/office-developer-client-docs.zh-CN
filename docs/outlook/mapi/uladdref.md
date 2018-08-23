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
ms.openlocfilehash: baf45fa33ca085f51a6f9c20f72ec1fd1545ad79
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592368"
---
# <a name="uladdref"></a>UlAddRef

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
提供一种方法来调用 OLE 方法**IUnknown::AddRef**。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
ULONG UlAddRef(
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
    
## <a name="remarks"></a>注解

 **UlAddRef**返回**IUnknown::AddRef**方法，这是新的接口的引用计数值返回的值。 值为非零值。 
  
有关**IUnknown::AddRef**的详细信息，请参阅[实现 IUnknown 接口](implementing-the-iunknown-interface.md)。 
  

