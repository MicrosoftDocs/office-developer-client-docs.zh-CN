---
title: 解析收件人姓名
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2baed391-85bd-4e88-8800-c19bc2d2d54a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a3faed3dda2461cab749c824fc97c2074e62375f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405862"
---
# <a name="resolving-a-recipient-name"></a>解析收件人姓名

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
当对邮件进行寻址时，会使用与每个收件人相关的属性构建收件人列表。 在发送邮件时，其中一个属性必须是收件人的长期条目标识符。 若要确保每个收件人包括 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性，在调用 [IAddrBook：：ResolveName](iaddrbook-resolvename.md)时，在 _lpAdrList_ 参数的内容中传递描述收件人列表的 [ADRLIST](adrlist.md)结构。
  
 **ResolveName** 通过忽略 **ADRLIST** 结构中已解析的条目开始处理，如相应 [ADRENTRY](adrentry.md) 结构的 **SPropValue** 数组中是否存在条目标识符所指示。 接下来 **，ResolveName** 自动为两种类型的收件人分配一次条目标识符： 
  
- 地址格式设置为 Internet 地址的收件人
    
- 地址格式如下的收件人：
    
     `displayname[address type:email address]`
    
对于所有其他条目 **，ResolveName** 在通讯簿中搜索通讯簿中的完全显示名称。 **ResolveName** 使用PR_AB_SEARCH_PATH ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) 属性来确定要搜索的容器集和搜索顺序。 MAPI 调用 [每个容器的 IABContainer：：ResolveNames](iabcontainer-resolvenames.md) 方法以尝试解析所有名称。 由于某些容器不支持 **ResolveNames，** 因此，如果容器返回 MAPI_E_NO_SUPPORT，MAPI 将 PR_ANR **(** [PidTagAnr](pidtaganr-canonical-property.md)) 内容表应用属性限制。 需要所有通讯簿容器才能支持具有此限制的名称解析。 解析所有名称后，不会进行其他容器调用。 如果已调用所有容器，但名称不明确或未解析，MAPI 将显示一个对话框（如果可能）提示用户解析其余名称。
  
the **PR_ANR** restriction matches the value of the **PR_ANR** property against the 显示名称 in the **ADRLIST** structure. 使用 **PR_ANR** 属性限制限制容器的内容表的视图将导致通讯簿提供程序执行"最佳猜测"类型的搜索，与提供程序有意义的属性相匹配。 例如，一个通讯簿提供程序可能始终将收件人列表中的名称与 **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 而另一个通讯簿提供程序可能允许管理员选择属性。
  
 **设置PR_ANR对通讯簿容器的内容表设置属性限制**
  
1. 创建 [SRestriction](srestriction.md) 结构，如以下代码所示： 
    
  ```cpp
  SRestriction SRestrict;
  SRestrict.rt = RES_PROPERTY;
  SRestrict.res.resProperty.relop = RELOP_EQ;
  SRestrict.res.resProperty.ulPropTag = PR_ANR;
  SRestrict.res.resProperty.lpProp->ulPropTag = PR_ANR;
  SRestrict.res.resProperty.lpProp->Value.LPSZ = lpszName;
   
  ```

2. 调用内容表的 [IMAPITable：：Restrict](imapitable-restrict.md) 方法，将 **SRestriction** 结构作为  _lpRestriction_ 参数传递。 
    

