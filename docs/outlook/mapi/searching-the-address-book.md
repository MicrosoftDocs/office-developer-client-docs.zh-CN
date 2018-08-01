---
title: 搜索通讯簿
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 20ff2b63-e4a3-4ba9-bad0-2c1873fb69b5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 6673e1d51a7c030a35a7c5c3cbc955341afba299
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778725"
---
# <a name="searching-the-address-book"></a>搜索通讯簿

**适用于**： Outlook 
  
MAPI 启用通讯簿提供程序实现两个级别的搜索功能：
  
- 基本级别与通讯簿条目的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性指定的名称相匹配。 此级别允许用户，例如，可以使用名称开头西北查看通讯组列表或找到其 last name 是褐色的单个消息用户。
    
- 匹配属性之外**PR_DISPLAY_NAME**高级级别。 此级别允许用户，例如，若要进一步缩小其搜索和查找消息名褐色为与特定地址类型的用户。
    
因为通讯簿提供程序可以支持在基本级别，这两个级别，其容器的每个搜索或选择不在所有支持，不需要搜索作为标准功能实现。 若要确定某个特定的容器是否支持搜索，尝试建立对其[IMAPIContainer::SetSearchCriteria](imapicontainer-setsearchcriteria.md)方法的调用中的搜索条件。 如果**SetSearchCriteria**返回 MAPI_E_NO_SUPPORT，容器不支持搜索。 
  
在支持搜索的容器，通过调用[IMAPIContainer::GetSearchCriteria](imapicontainer-getsearchcriteria.md)中检索已建立的条件。 您还可以请求，将提示用户输入搜索条件显示容器内容表之前。 若要选择此选项，设置的容器的**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) 属性 AB_FIND_ON_OPEN 标志。 用户输入条件后，它是存储为限制，并传递给**SetSearchCriteria**方法。 设置 AB_FIND_ON_OPEN 是特别有用，如果您使用联机服务或具有慢速链接到其数据的任何通讯簿提供程序。 
  
### <a name="to-perform-a-basic-search-in-an-address-book-container"></a>若要执行的通讯簿容器中的基本搜索
  
1. 调用容器的[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)方法以打开其内容的表格。 
    
2. 选择满足您需求的搜索技术。 选项包括：
    
   - [IMAPITable::FindRow](imapitable-findrow.md) ，以便在表中查找特定行。 
    
   - 对表中的行进行排序[IMAPITable::SortTable](imapitable-sorttable.md) 。 
    
   - [IMAPITable::Restrict](imapitable-restrict.md)限制表视图。 
    
   - 属性限制的模糊名称解析使用**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性。 调用**IMAPITable::Restrict**要实施此限制。 
    
   - [IABContainer::ResolveNames](iabcontainer-resolvenames.md) ，若要解决不明确的名称。 
    
3. 调用[IMAPITable::QueryRows](imapitable-queryrows.md)检索符合应用的搜索条件的任何行。 **QueryRows**可以返回零个或多个匹配的行。 
    
**FindRow**、 **SortTable**和**Restrict**方法是可用于任何可以创建，通过客户端或服务提供商的表的表方法。 **PR\_ANR**属性限制**IABContainer::ResolveNames**方法特定于通讯簿提供程序和用于解析不明确的名称。 不明确的名称是在收件人列表中的条目，没有与其关联的**PR_ENTRYID**属性。 
  
**PR\_ANR**限制调用算法，单词到分隔的字符串匹配这些单词与使用前缀匹配在通讯簿中的信息。 用于匹配的信息取决于通讯簿提供程序。 所有通讯簿提供程序都需要支持其通讯簿容器**PR_ANR**限制。 有关详细信息，请参阅[实现名称解析](implementing-name-resolution.md)。
  
**IABContainer::ResolveNames**执行**PR_ANR**限制而无需容器的内容表，才能开放的处理多个名称。 调用**ResolveNames**一次将多个名称解析可以速度大于调用**PR\_ANR**限制多次。 但是，无需通讯簿提供程序支持**ResolveNames**。
  

