---
title: IMAPISupportSetProviderUID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.SetProviderUID
api_type:
- COM
ms.assetid: 58855843-9a2b-4e5d-9332-b1bfad8b45e4
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: df842e633f1586d6d77441126d51b2ce44ec3beb
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589068"
---
# <a name="imapisupportsetprovideruid"></a>IMAPISupport::SetProviderUID

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
注册[MAPIUID](mapiuid.md)结构，它唯一表示服务提供商。 
  
```cpp
HRESULT SetProviderUID(
LPMAPIUID lpProviderID,
ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpProviderID_
  
> [in]指向标识的通讯簿或消息存储提供程序的**MAPIUID**结构的指针。 
    
 _ulFlags_
  
> 保留;必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功注册**MAPIUID**结构。 
    
## <a name="remarks"></a>注解

对于通讯簿和消息存储提供程序支持对象实现**IMAPISupport::SetProviderUID**方法。 这些提供程序调用**SetProviderUID**注册_lpProviderID_所指向的**MAPIUID**结构中所述的唯一标识符。 提供程序中的项标识符为他们创建的所有包含此标识符。 
  
MAPI 到 MAPI 后台处理程序并确定相应的提供程序，用于处理客户端请求发送出站邮件时使用的**MAPIUID**结构。 例如，当客户端调用[IMAPISession::OpenEntry](imapisession-openentry.md)方法，则 MAPI 将检查的项标识符的**MAPIUID**部分，将其映射到传递给**SetProviderUID**，并调用该提供商的**OpenEntry**的提供程序. 
  
## <a name="notes-to-callers"></a>给调用方的说明

在登录时，若要注册**MAPIUID**结构调用**SetProviderUID** 。 MAPI 允许通讯簿和消息存储提供程序注册多个标识符。 当您进行多次调用**SetProviderUID**时，它始终向**MAPIUID**结构**MAPIUID**结构的提供程序的设置即使**MAPIUID**副本。 **SetProviderUID**不能删除**MAPIUID**。 
  
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

