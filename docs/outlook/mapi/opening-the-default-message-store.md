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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436025"
---
# <a name="opening-the-default-message-store"></a>打开默认邮件存储

**适用于**：Outlook 2013 | Outlook 2016 
  
在任何特定会话中，一个邮件存储充当默认邮件存储。 默认邮件存储具有以下特征：
  
- [PidTagDefaultStore PR_DEFAULT_STORE (PidTagDefaultStore](pidtagdefaultstore-canonical-property.md)) 设置为 TRUE。 
    
- The STATUS_DEFAULT_STORE flag is set in the **PR_RESOURCE_FLAGS (** [PidTagResourceFlags](pidtagresourceflags-canonical-property.md)) property.
    
- MAPI 会在打开邮件存储时自动为搜索结果、常见视图和个人视图创建 IPM 子树和根文件夹。 有关这些文件夹详细信息，请参阅 [IPM 子树](ipm-subtree.md) 和 [MAPI 特殊文件夹](mapi-special-folders.md)。 
    
若要检索默认邮件存储的条目标识符，必须调用 [IMAPISession：：GetMsgStoresTable](imapisession-getmsgstorestable.md) 以打开邮件存储表，在调用 [HrQueryAllRows](hrqueryallrows.md)时应用适当的限制。 **HrQueryAllRows** 将返回一个行集，该行代表默认邮件存储。 传递给 **HrQueryAllRows 的限制** 可以针对以下表单之一： 
  
1. 使用 **SAndRestriction 结构进行组合** 的 **AND** 限制： 
    
   - 存在一个使用 **SExistRestriction** 结构来测试是否存在 PR_DEFAULT_STORE **属性的限制** 。 
    
   - 使用 [SPropertyRestriction](spropertyrestriction.md)结构检查属性中的 TRUE 值 **PR_DEFAULT_STORE限制。** 
    
2. 一个位掩码限制，它使用 [SBitMaskRestriction](sbitmaskrestriction.md)结构对 STATUS_DEFAULT_STORE 属性应用该 **PR_RESOURCE_FLAGS掩码。** 
    
## <a name="see-also"></a>另请参阅

- [SExistRestriction](sexistrestriction.md)
- [SAndRestriction](sandrestriction.md)

