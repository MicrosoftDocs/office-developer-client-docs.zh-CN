---
title: 集中 Ndr 的回执
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: fbe1f4f6-28f8-40b8-b551-192c0ba48c18
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 16a150105211231af54ccfdc5d1565aeecea729e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579436"
---
# <a name="centralizing-the-receipt-of-ndrs"></a>集中 Ndr 的回执

**适用于**： Outlook 2013 |Outlook 2016 
  
**具有未送达报告 (Ndr) 到达一个中心位置时同时运行多个客户端的实例**
  
1. 将**PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md))、 **PR_REPORT_NAME** ([PidTagReportName](pidtagreportname-canonical-property.md)) 和**PR_REPORT_SEARCH_KEY** ([PidTagReportSearchKey](pidtagreportsearchkey-canonical-property.md)) 设置为适当的值是接收的帐户报告。 通过调用[IAddrBook::CreateOneOff](iaddrbook-createoneoff.md) ，根据需要创建的项标识符。 
    
2. 了解将忽略帐户已请求报告并将它们发送到原始发件人的邮件系统。 减少这会在需要通过移动报告的管理员的影响：
    
- 提供您的原始邮件不同邮件类 IPM 如。Note.MSNNews。 查找与类 Report.IPM.Note.MSNNews.NDR 的传入消息，并将它们转发给您能报告前置的帐户。 同时，到忽略您原件报表帐户进行通信，它应服从**PR_REPORT_ENTRYID**属性的邮件系统发送电子邮件。 
    
- 大多数邮件系统的不遵守**PR_REPORT_ENTRYID**不将也遵守的 MAPI 邮件类约定。 因此，您会收到类似一条注释的。 这是有点更加复杂，因为输入因此变量处理。 查看主题，并将其转接，如果您发现任一从列表中的单词"未送达"该 mean 或内容从您的原始主题。 准备随着时间的推移调整这些列表。 
    

