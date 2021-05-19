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
  
地图 OLE 存储对象向 HRESULT 类型返回 SCODE 返回值。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Imessage.h  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
SCODE MapStorageSCode(
  SCODE StgSCode
);
```

## <a name="parameters"></a>参数

 _StgSCode_
  
> [in]MAPI SCODE 返回要映射到 HRESULT 值的 OLE 存储对象中的值。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回预期值。
    
MAPI_E_CALL_FAILED 
  
> 函数找不到匹配值。
    
## <a name="remarks"></a>备注

MAPI 提供 **MapStorageSCode** 函数，供内部使用 MAPI 组件，这些组件基于消息 DLL 实现其邮件实现。 因为这些组件自行打开 OLE 存储，所以它们必须能够将针对 OLE 存储问题返回的错误值映射到 HRESULT 值。 
  
有关详细信息，请参阅结构化[存储。](structured-storage-in-mapi.md) 
  

