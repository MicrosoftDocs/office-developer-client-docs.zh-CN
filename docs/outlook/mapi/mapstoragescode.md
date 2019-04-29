---
title: MapStorageSCode
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.MapStorageSCode
api_type:
- COM
ms.assetid: f686a2bc-aba5-4ea3-9963-76d0e96eab50
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 5dce5de820c07e1fa7b25b87d87993a30961b3f2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33416522"
---
# <a name="mapstoragescode"></a>MapStorageSCode

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将 SCODE 返回值从 OLE 存储对象映射到 HRESULT 类型。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Imessage  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
SCODE MapStorageSCode(
  SCODE StgSCode
);
```

## <a name="parameters"></a>参数

 _StgSCode_
  
> 实时MAPI SCODE 从 OLE 存储对象返回要映射到 HRESULT 值的值。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功, 并返回所需的值。
    
MAPI_E_CALL_FAILED 
  
> 函数找不到匹配的值。
    
## <a name="remarks"></a>说明

mapi 提供了**MapStorageSCode**函数, 用于在邮件 DLL 中基于其邮件实现的 MAPI 组件的内部使用。 由于这些组件本身打开的是 ole 存储, 因此它们必须能够将 OLE 存储问题返回的错误值映射到 HRESULT 值。 
  
有关详细信息, 请参阅[结构化存储](structured-storage-in-mapi.md)。 
  

