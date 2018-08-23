---
title: 实现名称解析
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a4c71b08-c47a-4421-8603-d5356d32dca9
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 489a5888014fa9299b407ebf91759627427b69bc
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571386"
---
# <a name="implementing-name-resolution"></a>实现名称解析

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
通讯簿提供程序负责支持名称解析 — 将条目标识符显示名称相关联的过程。 客户端启动名称解析致电[IAddrBook::ResolveName](iaddrbook-resolvename.md)以确保每个成员的传出邮件的收件人列表对应于有效的地址。 
  
您的提供商可以支持名称解析的：
  
- 支持**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性限制，所有通讯簿容器的要求。
    
- 实现[IABContainer::ResolveNames](iabcontainer-resolvenames.md)方法，用于所有通讯簿容器的选项。 
    
如果您选择支持**IABContainer::ResolveNames**，尝试在使用_lpAdrList_参数传递的[ADRLIST](adrlist.md)结构中找到的每个未解析的显示名称的准确匹配。 您可以标识未解析的显示名称，因为它缺少**ADRLIST**结构中的其**aEntries**成员中的属性值数组中的**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。 忽略具有零个属性及其相关联的任何项。 
  
报告您尝试分辨率_lpFlagList_参数，对应于_lpAdrList_中的显示名称的数组的标志数组中的结果。 Flags 位置以便第一个标志对应于**ADRLIST**结构中的第一个**aEntries**成员，第二个标志对应于第二个**aEntries**成员，依此类推。 
  
有三种可能的结果，为每个未解析的项：
  
- 未找到匹配，这意味着无容器条目中的条目匹配**ADRLIST**结构中的条目。 设置 MAPI_UNRESOLVED 的_lpFlagList_参数中的相应项。 
    
- 可以找到多个匹配，这意味着有多个容器条目相匹配的**ADRLIST**结构中的条目。 设置 MAPI_AMBIGUOUS 的_lpFlagList_参数中的相应项。 不要更改**ADRLIST**结构中的条目数。 
    
- 可以找到精确的匹配，这意味着只有一个容器条目相匹配的**ADRLIST**结构中的条目。 MAPI_RESOLVED _lpFlagList_参数中设置的相应成员并将条目标识符添加到与**ADRLIST**条目关联的属性的数组。 
    
如果您选择不支持**IABContainer::ResolveNames**，返回 MAPI_E_NO_SUPPORT 从您的实现。
  
所有通讯簿提供程序都需要支持模糊名称解析- **PR_ANR**属性限制 — 对其容器的内容表。 提供支持，请通过执行搜索，针对一个或多个提供程序有意义的特定属性的匹配"最佳猜测"类型处理的[IMAPITable::Restrict](imapitable-restrict.md)实现中 PR_ANR 限制。 您可以选择使用同一个或多个属性每次时，如**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 或**PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md))，或允许管理员可供选择的可接受的属性的列表。 
  
尽管大多数提供程序提供自己的内容表实现，可以自定义由 MAPI 提供通过[CreateTable](createtable.md)函数的实现。 但是，由于 MAPI 实现不支持任何类型的限制，您必须创建包装对象包含截取调用的**限制**的自定义的版本。 
  

