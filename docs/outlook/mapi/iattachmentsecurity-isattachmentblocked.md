---
title: IAttachmentSecurityIsAttachmentBlocked
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IAttachmentSecurity.IsAttachmentBlocked
api_type:
- COM
ms.assetid: 6986d27a-9602-e44a-0797-4c47f2184ef7
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: d255d7b6e80fe0c080fa0a27a7976db758a8c2ec
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32350846"
---
# <a name="iattachmentsecurityisattachmentblocked"></a>IAttachmentSecurity::IsAttachmentBlocked

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检查指定的附件是否被 microsoft outlook 2010 或 microsoft outlook 2013 阻止, 以供查看和编制索引。
  
```cpp
HRESULT IAttachmentSecurity::IsAttachmentBlocked( 
    LPCWSTR pwszFileName,  
    BOOL *pfBlocked 
);
```

## <a name="parameters"></a>参数

 _pwszFileName_
  
> 实时指向附件的文件名的指针。
    
 _pfBlocked_
  
> 排除指向一个值的指针, 该值指示如果指定的附件被阻止, 则为**true** ;否则**为 false**。
    
## <a name="see-also"></a>另请参阅



[MAPI 常量](mapi-constants.md)
  
[验证附件是否已被阻止](how-to-verify-an-attachment-is-blocked.md)

