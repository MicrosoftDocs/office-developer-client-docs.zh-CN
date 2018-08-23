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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 244087c41e33e470c42434e9d57cee7317bcb78c
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571687"
---
# <a name="imapisupportnewuid"></a>IMAPISupport::NewUID

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
创建一个新的[MAPIUID](mapiuid.md)结构用作唯一标识符。 
  
```cpp
HRESULT NewUID(
LPMAPIUID lpMuid
);
```

## <a name="parameters"></a>参数

 _lpMuid_
  
> 指向新**MAPIUID**结构的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 创建新的**MAPIUID**结构。 
    
## <a name="remarks"></a>注解

对于所有支持对象实现**IMAPISupport::NewUID**方法。 服务提供商和消息服务调用**NewUID** ，只要他们需要生成的长期的唯一标识符。 消息存储提供程序，例如，可能会调用**NewUID**获取**MAPIUID**将放入新创建的消息的**PR_SEARCH_KEY** ([PidTagSearchKey](pidtagsearchkey-canonical-property.md)) 属性。
  
## <a name="notes-to-callers"></a>给调用方的说明

请勿将在登录时与**NewUID**方法创建的**MAPIUID**结构注册**MAPIUID**结构混淆。 注册调用[IMAPISupport::SetProviderUID](imapisupport-setprovideruid.md)方法时**MAPIUID**结构表示通讯簿或消息存储到 MAPI 提供程序和用于区分不同的提供程序创建的项标识符。 此**MAPIUID**结构应硬编码，并通过**NewUID**调用未获得。
  
## <a name="see-also"></a>另请参阅



[MAPIUID](mapiuid.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

