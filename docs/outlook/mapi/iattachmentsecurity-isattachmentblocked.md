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
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: 45e4362fc025c1784e9432c5d641e865a044bd00
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775280"
---
# <a name="iattachmentsecurityisattachmentblocked"></a>IAttachmentSecurity::IsAttachmentBlocked

  
  
**适用于**： Outlook 
  
检查是否指定的附件阻止通过 Microsoft Outlook 2010 或 Microsoft Outlook 2013 的查看和编制索引。
  
```cpp
HRESULT IAttachmentSecurity::IsAttachmentBlocked( 
    LPCWSTR pwszFileName,  
    BOOL *pfBlocked 
);
```

## <a name="parameters"></a>参数

 _pwszFileName_
  
> [in]指向附件的文件名。
    
 _pfBlocked_
  
> [输出]为值，该值指示**true**将阻止指定的附件; 如果指针否则为**false**。
    
## <a name="see-also"></a>另请参阅



[MAPI 常量](mapi-constants.md)
  
[验证附件是否已遭阻止](how-to-verify-an-attachment-is-blocked.md)

