---
title: 集中处理收到的 NDR
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: fbe1f4f6-28f8-40b8-b551-192c0ba48c18
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: af2531076755d1e183409f50fe1a0c97d28063f7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405854"
---
# <a name="centralizing-the-receipt-of-ndrs"></a>集中处理收到的 NDR

**适用于**：Outlook 2013 | Outlook 2016 
  
**若要让未送达报告 (当) 多个客户端实例同时运行时，未送达报告将到达中心位置**
  
1. 将 **PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md) **) 、PR_REPORT_NAME** ([PidTagReportName](pidtagreportname-canonical-property.md)) 和 **PR_REPORT_SEARCH_KEY** ([PidTagReportSearchKey](pidtagreportsearchkey-canonical-property.md)) 设置为要接收报告的帐户的适当值。 如有必要，通过调用 [IAddrBook：：CreateOneOff 创建](iaddrbook-createoneoff.md) 条目标识符。 
    
2. 请注意，有些邮件系统将忽略您请求的报告帐户，并将其发送给发起方。 请通过以下两种策略减少对需要移动报告管理员的影响：
    
- 为原始邮件提供一个不同的邮件类别，如 IPM。Note.MSNNews。 查找具有类 Report.IPM.Note.MSNNews.NDR 的传入邮件，然后将它们转发到预期报告到达的帐户。 同时，将电子邮件发送到忽略未送达报告帐户的邮件系统，以表明它应遵守 PR_REPORT_ENTRYID **属性。** 
    
- 大多数不遵守 MAPI 邮件 **PR_REPORT_ENTRYID** 也不遵守 MAPI 邮件类约定。 因此，您将收到类似于注释的一些内容。 这有点难以处理，因为输入是可变的。 如果您从表示"无法送达"的单词列表中找到内容或原始主题中的某些内容，请查看主题并转发主题。 请准备好随着时间的推移调整这些列表。 
    

