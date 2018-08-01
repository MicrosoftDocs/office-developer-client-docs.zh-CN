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
ms.openlocfilehash: e748427b39418a80cae88e98b4aa7eef6df24393
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775989"
---
# <a name="ipersistmessageisdirty"></a>IPersistMessage::IsDirty

  
  
**适用于**： Outlook 
  
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
    
## <a name="remarks"></a>说明

表单查看器调用**IPersistMessage::IsDirty**方法以确定是否邮件有未保存的数据。 
  
## <a name="see-also"></a>另请参阅



[IPersistMessage : IUnknown](ipersistmessageiunknown.md)

