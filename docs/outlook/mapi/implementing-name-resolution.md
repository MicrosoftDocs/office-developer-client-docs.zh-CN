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
  
通讯簿提供程序负责支持名称解析 — 将条目标识符与通讯簿关联的显示名称。 客户端在调用 [IAddrBook：：ResolveName](iaddrbook-resolvename.md) 时启动名称解析，以确保传出邮件的收件人列表的每个成员都对应一个有效的地址。 
  
您的提供程序可以通过：
  
- 支持[PidTagAnr PR_ANR (PidTagAnr](pidtaganr-canonical-property.md)) 属性限制，这是所有通讯簿容器的要求。 
    
- 实现 [IABContainer：：ResolveNames](iabcontainer-resolvenames.md) 方法，这是所有通讯簿容器的一个选项。 
    
如果选择支持 **IABContainer：：ResolveNames，** 则尝试在传入 _lpAdrList_ 参数的 [ADRLIST](adrlist.md)结构中查找每个未解析 显示名称 的完全匹配项。 可以标识未解析的 显示名称因为它在 **ADRLIST** 结构的 **aEntries** 成员中的属性值数组中缺少 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性。 忽略任何具有零个关联的属性的条目。 
  
在  _lpFlagList_ 参数中报告尝试解析的结果，该参数是一个标志数组，对应于  _lpAdrList_ 中的显示名称数组。 标志具有位置性，因此第一个标志对应于 **ADRLIST** 结构中的第一个 **aEntries** 成员，第二个标志对应于第二个 **aEntries** 成员，以此类举。 
  
每个未解析条目有三个可能的结果：
  
- 未找到匹配项，这意味着容器条目中没有与 **ADRLIST** 结构中的条目匹配。 将  _lpFlagList_ 参数中的相应条目设置为MAPI_UNRESOLVED。 
    
- 可以发现多个匹配项，这意味着有多个与 **ADRLIST** 结构中条目匹配的容器条目。 将  _lpFlagList_ 参数中的相应条目设置为MAPI_AMBIGUOUS。 不要更改 **ADRLIST** 结构的条目数。 
    
- 可以找到完全匹配，这意味着只有一个容器条目与 **ADRLIST** 结构中的条目匹配。 将  _lpFlagList_ 参数中的对应成员设置为MAPI_RESOLVED条目标识符添加到与 **ADRLIST** 条目关联的属性数组。 
    
如果选择不支持 **IABContainer：：ResolveNames，** 则从MAPI_E_NO_SUPPORT返回值。
  
所有通讯簿提供程序都需要支持其容器的内容表上不明确的名称解析 **（PR_ANR** 属性限制）。 若要提供此支持，请处理 [IMAPITable：：Restrict](imapitable-restrict.md) 实现中的 PR_ANR 限制，具体方法为执行"最佳猜测"类型的搜索，与对提供程序有意义的一个或多个特定属性匹配。 可以选择每次使用相同的属性，如 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 或 **PR_ACCOUNT** ([PidTagAccount](pidtagaccount-canonical-property.md)) ，或者允许管理员从可接受的属性列表中选择。 
  
虽然大多数提供程序提供其自己的内容表实现，但您可以通过 [CreateTable](createtable.md) 函数自定义 MAPI 提供的实现。 但是，由于 MAPI 实现不支持任何类型的限制，因此必须创建包装对象以包含可截获调用的 **自定义版本的 Restrict。** 
  

