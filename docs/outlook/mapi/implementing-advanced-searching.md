---
title: 实现高级搜索
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 08cc60d4-cac8-4ba5-bd7f-a56e63697be3
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 0ba9958588c476ae330b0f4a413361e80d54667a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571967"
---
# <a name="implementing-advanced-searching"></a>实现高级搜索

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
一些地址簿容器支持高级搜索功能，允许客户端搜索之外**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 的属性。 若要支持高级的搜索，您的提供商必须实现通过您的其他容器的**PR_SEARCH** ([PidTagSearch](pidtagsearch-canonical-property.md)) 属性可访问的特殊容器。 **PR_SEARCH**包含容器对象提供对显示表介绍用于输入和编辑高级的搜索条件对话框中的访问权。 
  
 **若要支持高级搜索**
  
1. 定义您的搜索条件的每个属性。
    
2. 在容器的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法中的代码部分的处理**PR_SEARCH**属性： 
    
1. 检查客户端请求**IMAPIContainer**接口。 请求不合适接口时，如果失败，并返回 MAPI_E_INTERFACE_NOT_SUPPORTED。 
    
2. 创建新的搜索对象支持**IMAPIContainer**接口的。 
    
3. 此时，将您的搜索容器**IMAPIProp::OpenProperty**方法进行调用，若要检索其**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性。 您的提供商必须提供显示表，通常通过调用[BuildDisplayTable](builddisplaytable.md)，描述容器的高级的搜索对话框。
    
4. MAPI 显示搜索对话框，允许用户输入适当的条件。 完成用户后，MAPI 调用容器的[IMAPIProp::SetProps](imapiprop-setprops.md)方法，以存储搜索条件。 
    
5. 将进行调用以请求您搜索容器内容表。 填充使用的所有符合条件的容器中条目的内容表。
    

