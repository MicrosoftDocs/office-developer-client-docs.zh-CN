---
title: 实现名称解析
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: a4c71b08-c47a-4421-8603-d5356d32dca9
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 15c1d502947865c02973f4950b6b6fa8109b8e78
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434702"
---
# <a name="implementing-name-resolution"></a>实现名称解析

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
通讯簿提供程序负责支持名称解析, 即将条目标识符与显示名称关联的过程。 客户端在调用[IAddrBook:: ResolveName](iaddrbook-resolvename.md)时启动名称解析, 以确保传出邮件的收件人列表的每个成员都对应于一个有效的地址。 
  
提供程序可以通过以下方式支持名称解析:
  
- 支持**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性限制, 这是对所有通讯簿容器的要求。
    
- 实现[IABContainer:: ResolveNames](iabcontainer-resolvenames.md)方法, 一个适用于所有通讯簿容器的选项。 
    
如果选择支持**IABContainer:: ResolveNames**, 请尝试查找与使用_lpAdrList_参数传入的[ADRLIST](adrlist.md)结构中的每个未解析的显示名称完全匹配的项。 您可以 identifiy 一个未解析的显示名称, 因为它在**ADRLIST**结构的**aEntries**成员的属性值数组中缺少**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。 忽略任何与零属性相关联的条目。 
  
报告_lpFlagList_参数中的解析结果, 即与_lpAdrList_中的显示名称数组相对应的标志数组。 这些标志的位置如下: 第一个标志对应于**ADRLIST**结构中的第一个**aEntries**成员, 第二个标志对应于第二个**aEntries**成员, 依此类推。 
  
每个未解析的条目都有三个可能的结果:
  
- 找不到匹配项, 这意味着容器条目中的任何条目都与**ADRLIST**结构中的条目不匹配。 将_lpFlagList_参数中对应的条目设置为 MAPI_UNRESOLVED。 
    
- 可以找到多个匹配项, 这意味着有多个容器条目与**ADRLIST**结构中的条目相匹配。 将_lpFlagList_参数中对应的条目设置为 MAPI_AMBIGUOUS。 请勿更改**ADRLIST**结构中的条目数。 
    
- 可以找到完全匹配的, 这意味着只有一个容器条目与**ADRLIST**结构中的条目相匹配。 将_lpFlagList_参数中对应的成员设置为 MAPI_RESOLVED, 并将条目标识符添加到与**ADRLIST**条目关联的属性数组中。 
    
如果您选择不支持**IABContainer:: ResolveNames**, 请从您的实现返回 MAPI_E_NO_SUPPORT。
  
所有通讯簿提供程序都需要在其容器的内容表上支持不明确的名称解析 ( **PR_ANR**属性限制)。 若要提供此支持, 请在您的[IMAPITable:: Restrict](imapitable-restrict.md)中通过执行 "最佳推测" 类型的搜索来处理 PR_ANR 限制, 使其与对您的提供商有意义的一个或多个特定属性相匹配。 您可以选择每次使用相同的属性或属性, 例如**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 或**PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md)), 或允许管理员从可接受的属性列表中进行选择。 
  
尽管大多数提供程序都提供其自己的内容表实现, 但您可以通过[CreateTable](createtable.md)函数自定义 MAPI 提供的实现。 但是, 由于 MAPI 实现不支持任何种类的限制, 因此您必须创建一个包装对象, 以包含截获该调用的自定义版本的**限制**。 
  

