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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328670"
---
# <a name="resolving-a-recipient-name"></a>解析收件人姓名

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
发送邮件时, 将使用与每个收件人相关的属性生成收件人列表。 在发送邮件时, 其中一个属性必须是收件人的长期条目标识符。 若要确保每个收件人都包含**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性, 请在对 IAddrBook 的调用中传递在_lpAdrList_参数的内容中描述您的收件人列表的[ADRLIST](adrlist.md)结构[::ResolveName](iaddrbook-resolvename.md)。
  
 **ResolveName**通过忽略已解决的**ADRLIST**结构中的条目来开始处理, 如相应[ADRENTRY](adrentry.md)结构的**SPropValue**中的条目标识符的存在所示。数组. 接下来, **ResolveName**自动为两种类型的收件人分配一次性条目标识符: 
  
- 地址格式为 Internet 地址的收件人
    
- 地址格式如下所示的收件人:
    
     `displayname[address type:email address]`
    
对于其余的所有条目, **ResolveName**在通讯簿中搜索显示名称的精确匹配项。 **ResolveName**使用**PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) 属性确定要搜索的容器集和搜索顺序。 MAPI 调用每个容器的[IABContainer:: ResolveNames](iabcontainer-resolvenames.md)方法来尝试解析所有名称。 由于某些容器不支持**ResolveNames**, 如果容器返回 MAPI_E_NO_SUPPORT, 则 MAPI 会对其内容表应用**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性限制。 必须使用所有通讯簿容器来支持此限制中的名称解析。 解析所有名称后, 将不会再进行容器调用。 如果所有容器都已被调用, 但保留不明确或未解析的名称, MAPI 将显示一个对话框, 提示用户解决其余的名称。
  
**PR_ANR**限制将**PR_ANR**属性的值与**ADRLIST**结构中的显示名称相匹配。 使用**PR_ANR**属性限制限制容器的内容表的视图会导致通讯簿提供程序执行 "最佳推测" 类型的搜索, 使其符合对提供程序有意义的属性。 例如, 一个通讯簿提供程序可能始终会将收件人列表中的名称与**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 相匹配, 而另一个通讯簿提供程序可能允许管理员选择该属性。
  
 **在通讯簿容器的内容表上设置 PR_ANR 属性限制**
  
1. 创建[SRestriction](srestriction.md)结构, 如以下代码所示: 
    
  ```cpp
  SRestriction SRestrict;
  SRestrict.rt = RES_PROPERTY;
  SRestrict.res.resProperty.relop = RELOP_EQ;
  SRestrict.res.resProperty.ulPropTag = PR_ANR;
  SRestrict.res.resProperty.lpProp->ulPropTag = PR_ANR;
  SRestrict.res.resProperty.lpProp->Value.LPSZ = lpszName;
   
  ```

2. 调用内容表的[IMAPITable:: Restrict](imapitable-restrict.md)方法, 并将**SRestriction**结构作为_lpRestriction_参数进行传递。 
    

