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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a60ac0d7ab139f77aea87080e1ce37fee870e97b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437537"
---
# <a name="imapisupportsetprovideruid"></a>IMAPISupport::SetProviderUID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
注册一个唯一表示服务提供商的 [MAPIUID](mapiuid.md) 结构。 
  
```cpp
HRESULT SetProviderUID(
LPMAPIUID lpProviderID,
ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpProviderID_
  
> [in]指向标识通讯簿或邮件存储提供程序的 **MAPIUID** 结构的指针。 
    
 _ulFlags_
  
> 保留;必须为零。
    
## <a name="return-value"></a>返回值

S_OK 
  
> **已成功注册 MAPIUID** 结构。 
    
## <a name="remarks"></a>备注

**IMAPISupport：：SetProviderUID** 方法针对通讯簿和邮件存储提供程序支持对象实现。 这些提供程序调用 **SetProviderUID** 以注册 **MAPIUID** 结构中描述的唯一标识符，该结构由  _lpProviderID 指向_。 提供程序在它们创建的所有条目标识符中包括此标识符。 
  
MAPI 在将出站邮件发送到 MAPI 后台处理程序并确定用于处理客户端请求的适当提供程序时，使用 **MAPIUID** 结构。 例如，当客户端调用 [IMAPISession：：OpenEntry](imapisession-openentry.md) 方法时，MAPI 将检查条目标识符的 **MAPIUID** 部分，将 MAPIUID 部分映射到传递到 **SetProviderUID** 的提供程序，并调用该提供程序的 **OpenEntry**。 
  
## <a name="notes-to-callers"></a>给调用方的说明

在 **登录时调用 SetProviderUID** 以注册 **MAPIUID** 结构。 MAPI 允许通讯簿和邮件存储提供程序注册多个标识符。 当您多次调用 **SetProviderUID** 时，它始终会将 **MAPIUID** 结构添加到提供程序的 **MAPIUID** 结构集，即使 **MAPIUID** 是重复的。 **SetProviderUID** 无法删除 **MAPIUID**。 
  
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

