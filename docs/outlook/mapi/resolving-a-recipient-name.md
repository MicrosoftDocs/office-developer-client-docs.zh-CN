---
title: 解析收件人姓名
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2baed391-85bd-4e88-8800-c19bc2d2d54a
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: d9b52edf7f4633fdf9c925a8d8db4953590713b3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22562930"
---
# <a name="resolving-a-recipient-name"></a>解析收件人姓名

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
时，从而解决了一条消息，收件人列表是构建具有与每个收件人的属性。 发送邮件时，这些属性之一必须是收件人的长期条目标识符。 若要确保每个收件人，包括**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 属性，传递[ADRLIST](adrlist.md)结构描述您收件人列表中，将调用[IAddrBook _lpAdrList_参数的内容：ResolveName](iaddrbook-resolvename.md)。
  
 **ResolveName**开始处理通过忽略已解决， **ADRLIST**结构中的条目，由相应[ADRENTRY](adrentry.md)结构**SPropValue**中的项标识符的状态数组。 接下来， **ResolveName**自动将一次性条目标识符分配给两种类型的收件人： 
  
- 收件人地址的格式设置为 Internet 地址
    
- 收件人地址的格式，如下所示：
    
     `displayname[address type:email address]`
    
对于所有剩余的项， **ResolveName**完全匹配上的显示名称搜索通讯簿。 **ResolveName**使用**PR_AB_SEARCH_PATH** ([PidTagAbSearchPath](pidtagabsearchpath-canonical-property.md)) 属性来确定一组的搜索和搜索顺序的容器。 MAPI 调用每个容器试图解析所有名称的[IABContainer::ResolveNames](iabcontainer-resolvenames.md)方法。 因为一些容器不支持**ResolveNames**，如果容器返回 MAPI_E_NO_SUPPORT，MAPI 应用**PR_ANR** ([PidTagAnr](pidtaganr-canonical-property.md)) 属性限制对照其内容表。 所有通讯簿容器都需要支持名称解析此限制。 一旦所有名称都均已解析，不再进行容器呼叫。 如果所有容器都已被都调用，但不明确或无法解析名称保持，MAPI 显示尽可能对话框提示用户将其余的名称解析。
  
**PR_ANR**限制匹配**ADRLIST**结构中的显示名称对**PR_ANR**属性的值。 限制带**PR_ANR**属性限制的容器内容表的视图可使通讯簿提供程序执行搜索，针对合理性提供程序的属性匹配"最佳猜测"类型。 例如，一个通讯簿提供程序可能总是匹配针对**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 的收件人列表中的名称，而另一个可能允许管理员选择的属性。
  
 **对通讯簿容器内容表设置 PR_ANR 属性限制**
  
1. 创建[SRestriction](srestriction.md)结构，如以下代码所示： 
    
  ```cpp
  SRestriction SRestrict;
  SRestrict.rt = RES_PROPERTY;
  SRestrict.res.resProperty.relop = RELOP_EQ;
  SRestrict.res.resProperty.ulPropTag = PR_ANR;
  SRestrict.res.resProperty.lpProp->ulPropTag = PR_ANR;
  SRestrict.res.resProperty.lpProp->Value.LPSZ = lpszName;
   
  ```

2. 调用内容表的[IMAPITable::Restrict](imapitable-restrict.md)方法，并作为_lpRestriction_参数传递的**SRestriction**结构。 
    

