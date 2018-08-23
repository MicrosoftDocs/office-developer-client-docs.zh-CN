---
title: 打开默认的邮件存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 670fb896-9aaf-4a96-83f7-76237409e956
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 0366e889f1c63e5fe40760ca80cec701cd6b3713
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573535"
---
# <a name="opening-the-default-message-store"></a>打开默认的邮件存储

**适用于**： Outlook 2013 |Outlook 2016 
  
在任何特定的会话中一个消息存储用作默认邮件存储区。 默认邮件存储区具有以下特征：
  
- **PR_DEFAULT_STORE** ([PidTagDefaultStore](pidtagdefaultstore-canonical-property.md)) 属性设置为 TRUE。
    
- **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中设置了 STATUS_DEFAULT_STORE 标志。
    
- 打开消息存储库时，MAPI 自动创建 IPM 子树和搜索结果、 公共视图和个人视图的根文件夹。 有关这些文件夹的详细信息，请参阅[IPM 子树](ipm-subtree.md)和[MAPI 特殊文件夹](mapi-special-folders.md)。 
    
若要检索默认的邮件存储的项标识符，必须调用[IMAPISession::GetMsgStoresTable](imapisession-getmsgstorestable.md)打开的消息存储表格并应用[HrQueryAllRows](hrqueryallrows.md)将调用适当的限制。 **HrQueryAllRows**将返回的行集与表示默认的邮件存储的一个行。 传递给**HrQueryAllRows**限制可以采用以下形式之一： 
  
1. 使用**SAndRestriction**结构组合**和**限制： 
    
   - 存在使用**SExistRestriction**结构**PR_DEFAULT_STORE**属性是否存在测试的限制。 
    
   - 使用[SPropertyRestriction](spropertyrestriction.md)结构**PR_DEFAULT_STORE**属性中的则返回 TRUE 值来检查属性限制。 
    
2. 位掩码限制为针对**PR_RESOURCE_FLAGS**属性掩码应用 STATUS_DEFAULT_STORE 使用[SBitMaskRestriction](sbitmaskrestriction.md)结构。 
    
## <a name="see-also"></a>另请参阅

- [SExistRestriction](sexistrestriction.md)
- [SAndRestriction](sandrestriction.md)

