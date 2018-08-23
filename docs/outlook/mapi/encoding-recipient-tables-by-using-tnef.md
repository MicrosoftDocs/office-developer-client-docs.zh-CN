---
title: 使用 TNEF 对收件人表编码
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cd2f595f-4dd0-4704-b670-6857d6c843ca
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: aa2120b5d64eece76f8882489de4388b04afa053
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591343"
---
# <a name="encoding-recipient-tables-by-using-tnef"></a>使用 TNEF 对收件人表编码

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
收件人表编码到 TNEF 流很少需要，因为大多数邮件系统直接支持收件人列表。 一般情况下，收件人属性传输邮件头中。 收件人表包含必要时，TNEF 可以对收件人表作为其往常处理的一部分进行编码。 此功能的初始 TNEF 处理阶段。 传输提供程序可以通过调用不带包含列表中指定的**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性[ITnef::AddProps](itnef-addprops.md)方法包括邮件的收件人表。 TNEF 从邮件中获取收件人的表、 查询列集，以及到 TNEF 流处理每个表的行。
  
一种方法是可用传输提供程序需要编码之前修改收件人的表。 传输提供程序可以构造必要的表，然后调用[ITnef::EncodeRecips](itnef-encoderecips.md)方法。 如果_lpRecipTable_参数中传递了 NULL，则收件人表不执行直接从邮件为**ITnef::AddProps**所述。
  

