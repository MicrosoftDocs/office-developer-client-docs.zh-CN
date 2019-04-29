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
  
**当同时运行客户端的多个实例时, 将 nondelivery 报告 (ndr) 到达一个中心位置**
  
1. 将**PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md))、 **PR_REPORT_NAME** ([PidTagReportName](pidtagreportname-canonical-property.md)) 和**PR_REPORT_SEARCH_KEY** ([PidTagReportSearchKey](pidtagreportsearchkey-canonical-property.md)) 设置为要接收的帐户的相应值报告。 通过调用[IAddrBook:: CreateOneOff (](iaddrbook-createoneoff.md)如有必要) 创建条目标识符。 
    
2. 了解邮件系统将忽略您为报告请求的帐户, 并将其发送给原始发件人。 降低此操作将对将报告移动所需的管理员的影响, 具体取决于:
    
- 为原始邮件提供一个不同的邮件类, 如 IPM。MSNNews。 查找带有类 Report 的传入邮件。 MSNNews, 并将其转发到您希望报告转到的帐户。 同时, 将电子邮件发送到忽略您的 nondelivery 报告帐户的邮件系统, 以传达它应服从**PR_REPORT_ENTRYID**属性。 
    
- 大多数不服从**PR_REPORT_ENTRYID**的邮件系统将不服从 MAPI 邮件类约定。 因此, 你将收到看上去像是注释的内容。 由于输入是如此变量, 因此处理起来要困难一些。 查看主题并将其转发, 前提是您找到的内容来自表示 "无法送达" 或原始主题中的内容的单词列表。 准备好在一段时间后调整这些列表。 
    

