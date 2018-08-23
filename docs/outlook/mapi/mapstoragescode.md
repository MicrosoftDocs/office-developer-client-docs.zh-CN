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
ms.openlocfilehash: 8dbb871a234d94f8bb2e21b15ce5de6f0db0e4ee
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581830"
---
# <a name="mapstoragescode"></a>MapStorageSCode

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
地图 SCODE 向 HRESULT 类型返回从 OLE 存储对象的值。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Imessage.h  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |客户端应用程序和服务提供商  <br/> |
   
```cpp
SCODE MapStorageSCode(
  SCODE StgSCode
);
```

## <a name="parameters"></a>参数

 _StgSCode_
  
> [in]MAPI SCODE 值从 OLE 存储对象返回要映射到 HRESULT 值。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功，并返回预期值。
    
MAPI_E_CALL_FAILED 
  
> 该函数找不到匹配值。
    
## <a name="remarks"></a>注解

MAPI 内部使用的基础上消息 DLL 其消息实现的 MAPI 组件提供了**MapStorageSCode**函数。 由于这些组件中打开 OLE 存储本身，它们必须能够映射 HRESULT 值问题与 OLE 存储返回错误值。 
  
有关详细信息，请参阅[结构化存储文件](structured-storage-in-mapi.md)。 
  

