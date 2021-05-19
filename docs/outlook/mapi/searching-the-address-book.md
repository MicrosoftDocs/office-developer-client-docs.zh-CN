---
title: 搜索通讯簿
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 20ff2b63-e4a3-4ba9-bad0-2c1873fb69b5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d40419291f4b09c5880a769ce231015511e8f269
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424369"
---
# <a name="searching-the-address-book"></a>搜索通讯簿

**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 使通讯簿提供程序可以实现两个级别的搜索功能：
  
- 与指定名称与通讯簿条目的[PidTagDisplayName PR_DISPLAY_NAME (PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 匹配的基本级别。  例如，此级别允许用户查看名称以 Northwest 开头的通讯组列表，或查找姓氏为 Brown 的单个邮件用户。
    
- 与属性匹配而非属性的高级 **PR_DISPLAY_NAME。** 例如，此级别允许用户进一步缩小搜索范围，并查找具有特定地址类型的名为"Brown"的邮件用户。
    
由于通讯簿提供程序可以支持在基本级别（在两个级别）搜索每个容器，或者选择完全不支持搜索，因此不要期望搜索作为标准功能实现。 若要确定特定容器是否支持搜索，尝试在调用 [其 IMAPIContainer：：SetSearchCriteria](imapicontainer-setsearchcriteria.md) 方法时建立搜索条件。 如果 **SetSearchCriteria** MAPI_E_NO_SUPPORT，则容器不支持搜索。 
  
在支持搜索的容器中，通过调用 [IMAPIContainer：：GetSearchCriteria](imapicontainer-getsearchcriteria.md)检索已建立的条件。 还可以请求在显示容器的内容表之前提示用户输入搜索条件。 若要选择此选项，请AB_FIND_ON_OPEN [PidTagContainerFlags](pidtagcontainerflags-canonical-property.md) PR_CONTAINER_FLAGS (容器的) 标志。  用户输入条件后，它将存储为限制并传递给 **SetSearchCriteria** 方法。 如果AB_FIND_ON_OPEN联机服务或任何链接到其数据的通讯簿提供商，则设置 AB_FIND_ON_OPEN 尤其有用。 
  
### <a name="to-perform-a-basic-search-in-an-address-book-container"></a>在通讯簿容器中执行基本搜索
  
1. 调用容器的 [IMAPIContainer：：GetContentsTable](imapicontainer-getcontentstable.md) 方法以打开其内容表。 
    
2. 选择满足您需求的搜索技术。 选项包括：
    
   - [IMAPITable：：FindRow，](imapitable-findrow.md) 用于查找表格中的特定行。 
    
   - [IMAPITable：：SortTable](imapitable-sorttable.md) 对表中的行进行排序。 
    
   - [IMAPITable：：Restrict](imapitable-restrict.md) 限制表视图。 
    
   - 使用 PidTagAnr **PR_ANR (** [PidTagAnr](pidtaganr-canonical-property.md)) 属性来解析不明确的名称。 调用 **IMAPITable：：Restrict** 以施加此限制。 
    
   - [IABContainer：：ResolveNames](iabcontainer-resolvenames.md) 可解析不明确的名称。 
    
3. 调用 [IMAPITable：：QueryRows](imapitable-queryrows.md) 以检索符合所应用的搜索条件的任何行。 **QueryRows** 可以返回零个或多个匹配行。 
    
**FindRow** **、SortTable** 和 **Restrict** 方法是表方法，可供客户端或服务提供商创建的任何表使用。 **PR \_ ANR 属性** 限制和 **IABContainer：：ResolveNames** 方法特定于通讯簿提供程序，用于解析不明确的名称。 不明确名称是收件人列表中的条目，这些条目没有 **PR_ENTRYID关联的属性** 。 
  
**PR \_ ANR** 限制调用一种算法，该算法将字符串分隔为单词，并且使用前缀匹配将那些单词与通讯簿中的信息相匹配。 用于匹配的信息取决于通讯簿提供程序。 所有通讯簿提供程序都需要支持其PR_ANR容器的通讯簿限制。 有关详细信息，请参阅 [实现名称解析](implementing-name-resolution.md)。
  
**IABContainer：：ResolveNames** **PR_ANR对** 多个名称执行限制处理，而无需打开容器的内容表。 调用 **ResolveNames** 一次来解析多个名称比多次调用 **PR \_ ANR** 限制要快得多。 但是，通讯簿提供程序不需要支持 **ResolveNames**。
  

