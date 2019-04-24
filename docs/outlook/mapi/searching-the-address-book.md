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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339737"
---
# <a name="searching-the-address-book"></a>搜索通讯簿

**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 允许通讯簿提供程序实现两个级别的搜索功能:
  
- 与通讯簿条目的**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性相匹配的指定名称的基本级别。 例如, 使用此级别, 用户可以查看名称从西北开始的通讯组列表, 或查找姓氏为褐色的单个邮件用户。
    
- 与**PR_DISPLAY_NAME**之外的属性匹配的高级级别。 例如, 此级别允许用户进一步缩小搜索范围, 并使用特定地址类型查找名为棕色的邮件用户。
    
由于通讯簿提供程序可以支持在基本级别搜索每个容器, 在这两个级别上, 或者选择根本不支持它, 因此不希望将搜索作为标准功能实现。 若要确定特定容器是否支持搜索, 请尝试在对其[IMAPIContainer:: SetSearchCriteria](imapicontainer-setsearchcriteria.md)方法的调用中建立搜索条件。 如果**SetSearchCriteria**返回 MAPI_E_NO_SUPPORT, 则该容器不支持搜索。 
  
在支持搜索的容器中, 通过调用[IMAPIContainer:: GetSearchCriteria](imapicontainer-getsearchcriteria.md)检索已建立的条件。 您还可以请求在显示容器的内容表之前, 提示用户输入搜索条件。 若要选择此选项, 请设置容器的**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) 属性的 AB_FIND_ON_OPEN 标志。 用户输入条件后, 它将存储为限制并传递给**SetSearchCriteria**方法。 如果使用的是联机服务或任何具有指向其数据的慢速链接的通讯簿提供程序, 则设置 AB_FIND_ON_OPEN 尤其有用。 
  
### <a name="to-perform-a-basic-search-in-an-address-book-container"></a>在通讯簿容器中执行基本搜索
  
1. 调用容器的[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)方法以打开其内容表。 
    
2. 选择符合你的需求的搜索技术。 选项包括:
    
   - [IMAPITable:: FindRow](imapitable-findrow.md) , 用于查找表中的特定行。 
    
   - [IMAPITable:: SortTable](imapitable-sorttable.md)对表中的行进行排序。 
    
   - [IMAPITable:: Restrict](imapitable-restrict.md)限制表格视图。 
    
   - 使用**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性解析不明确的名称的属性限制。 调用**IMAPITable:: Restrict**以施加此限制。 
    
   - [IABContainer:: ResolveNames](iabcontainer-resolvenames.md)解析不明确的名称。 
    
3. 调用[IMAPITable:: QueryRows](imapitable-queryrows.md)以检索符合应用的搜索条件的任何行。 **QueryRows**可以返回零个或多个匹配行。 
    
**FindRow**、 **SortTable**和**Restrict**方法是可用于可由客户端或服务提供商创建的任何表的表方法。 **\_PR ANR**属性限制和**IABContainer:: ResolveNames**方法特定于通讯簿提供程序, 用于解析不明确的名称。 不明确的名称是收件人列表中没有与之关联的**PR_ENTRYID**属性的条目。 
  
**PR\_ANR**限制调用将字符串分隔为单词的算法, 并将这些单词与使用前缀匹配的通讯簿中的信息相匹配。 用于匹配的信息取决于通讯簿提供程序。 所有通讯簿提供程序都需要支持其通讯簿容器的**PR_ANR**限制。 有关详细信息, 请参阅[实现名称解析](implementing-name-resolution.md)。
  
**IABContainer:: ResolveNames**对多个名称执行**PR_ANR**限制处理, 而无需打开容器的内容表。 调用**ResolveNames**一次以解析多个名称比多次调用**PR\_ANR**限制的速度要快得多。 但是, 通讯簿提供程序不需要支持**ResolveNames**。
  

