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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439777"
---
# <a name="iattachmentsecurityisattachmentblocked"></a>IAttachmentSecurity::IsAttachmentBlocked

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检查指定的附件是否被邮件Microsoft Outlook 2010或Microsoft Outlook 2013查看和编制索引。
  
```cpp
HRESULT IAttachmentSecurity::IsAttachmentBlocked( 
    LPCWSTR pwszFileName,  
    BOOL *pfBlocked 
);
```

## <a name="parameters"></a>参数

 _pwszFileName_
  
> [in]指向附件文件名的指针。
    
 _pfBlocked_
  
> [out]指向指示 **true（** 如果指定的附件被阻止）的值的指针;否则为 **false**。
    
## <a name="see-also"></a>另请参阅



[MAPI 常量](mapi-constants.md)
  
[验证附件被阻止](how-to-verify-an-attachment-is-blocked.md)

