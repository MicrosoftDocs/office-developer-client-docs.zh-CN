---
title: IMAPISupportNewUID
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.NewUID
api_type:
- COM
ms.assetid: 7994477d-5207-4335-b538-69c98782d52d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a38f7ea475f8a5cbad4f1cc295c3e2550ea8cd66
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406995"
---
# <a name="imapisupportnewuid"></a>IMAPISupport::NewUID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
创建要用作唯一标识符的新 [MAPIUID](mapiuid.md) 结构。 
  
```cpp
HRESULT NewUID(
LPMAPIUID lpMuid
);
```

## <a name="parameters"></a>参数

 _lpMuid_
  
> 指向新 **MAPIUID 结构的** 指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 创建了 **新的 MAPIUID** 结构。 
    
## <a name="remarks"></a>备注

**IMAPISupport：：NewUID** 方法针对所有支持对象实现。 只要服务提供程序和邮件服务需要生成长期的唯一标识符，它们就会调用 **NewUID。** 例如，邮件存储提供程序可能调用 **NewUID** 以获取 **MAPIUID，** 以放入新创建的邮件的 **PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性中。
  
## <a name="notes-to-callers"></a>给调用方的说明

请勿将登录时注册的 **MAPIUID** 结构与 **NewUID** 方法创建的 **MAPIUID** 结构相混淆。 调用 [IMAPISupport：：SetProviderUID](imapisupport-setprovideruid.md)方法时注册的 **MAPIUID** 结构表示您的通讯簿或邮件存储提供程序到 MAPI，并用于区分不同提供程序创建的条目标识符。 此 **MAPIUID** 结构应硬编码，而不是通过调用 **NewUID 来获取**。
  
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

