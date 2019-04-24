---
title: 打开默认邮件存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 670fb896-9aaf-4a96-83f7-76237409e956
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d8e620516e2b3e61cd07f3a08af989cc4ed5b61e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348599"
---
# <a name="opening-the-default-message-store"></a>打开默认邮件存储

**适用于**：Outlook 2013 | Outlook 2016 
  
在任何特定的会话中, 一个邮件存储将充当默认邮件存储区。 默认邮件存储区具有以下特征:
  
- **PR_DEFAULT_STORE** ([PidTagDefaultStore](pidtagdefaultstore-canonical-property.md)) 属性设置为 TRUE。
    
- 在**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) 属性中设置 STATUS_DEFAULT_STORE 标志。
    
- MAPI 在打开邮件库时, 会自动为搜索结果、常见视图和个人视图创建 IPM 子树和根文件夹。 有关这些文件夹的详细信息, 请参阅[IPM 子树](ipm-subtree.md)和[MAPI 特殊文件夹](mapi-special-folders.md)。 
    
若要检索默认邮件存储的条目标识符, 必须调用[IMAPISession:: GetMsgStoresTable](imapisession-getmsgstorestable.md)打开邮件存储表, 并在对[HrQueryAllRows](hrqueryallrows.md)的调用中应用适当的限制。 **HrQueryAllRows**将返回行集, 其中的一行表示默认邮件存储区。 传递给**HrQueryAllRows**的限制可采用以下形式之一: 
  
1. 一个**和**限制, 它使用**SAndRestriction**结构来进行组合: 
    
   - 存在一个限制, 它使用**SExistRestriction**结构来测试**PR_DEFAULT_STORE**属性是否存在。 
    
   - 使用[SPropertyRestriction](spropertyrestriction.md)结构检查**PR_DEFAULT_STORE**属性中的 TRUE 值的属性限制。 
    
2. 一个位掩码限制, 它使用[SBitMaskRestriction](sbitmaskrestriction.md)结构将 STATUS_DEFAULT_STORE 应用于**PR_RESOURCE_FLAGS**属性的掩码。 
    
## <a name="see-also"></a>另请参阅

- [SExistRestriction](sexistrestriction.md)
- [SAndRestriction](sandrestriction.md)

