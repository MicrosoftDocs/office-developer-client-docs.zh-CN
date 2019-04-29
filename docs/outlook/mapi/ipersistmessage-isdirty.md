---
title: IPersistMessageIsDirty
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPersistMessage.IsDirty
api_type:
- COM
ms.assetid: 57f688db-3a1c-49ff-a15a-8508bda5de68
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 91985d3dc8a7816c3da3215e505097c57c63e035
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407569"
---
# <a name="ipersistmessageisdirty"></a>IPersistMessage::IsDirty

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检查表单的上次保存以来所做的更改。
  
```cpp
HRESULT IsDirty( void );
```

## <a name="parameters"></a>参数

无
  
## <a name="return-value"></a>返回值

S_OK 
  
> 表单包含自上次保存以来所做的更改。
    
S_FALSE 
  
> 表单不包含自上次保存以来所做的更改。
    
## <a name="remarks"></a>说明

表单查看者调用**IPersistMessage:: IsDirty**方法, 以确定邮件是否有未保存的数据。 
  
## <a name="see-also"></a>另请参阅



[IPersistMessage : IUnknown](ipersistmessageiunknown.md)

