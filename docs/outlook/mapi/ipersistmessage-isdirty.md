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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 0d2ae556f4dd98b5f6e274a21c608d4ea364d4ec
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576202"
---
# <a name="ipersistmessageisdirty"></a>IPersistMessage::IsDirty

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
检查自上次保存以来所做的更改的表单。
  
```cpp
HRESULT IsDirty( void );
```

## <a name="parameters"></a>参数

无
  
## <a name="return-value"></a>返回值

S_OK 
  
> 窗体有自上次保存以来所做的更改。
    
S_FALSE 
  
> 窗体不具有自上次保存以来所做的更改。
    
## <a name="remarks"></a>注解

表单查看器调用**IPersistMessage::IsDirty**方法以确定是否邮件有未保存的数据。 
  
## <a name="see-also"></a>另请参阅



[IPersistMessage : IUnknown](ipersistmessageiunknown.md)

