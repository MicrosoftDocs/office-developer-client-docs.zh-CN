---
title: 传递状态报告的收件人属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9b2e287e-1cf8-4b8f-b92c-a065ed264d02
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 784cac21aac5de18952f3768af9b8f189f604981
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32328432"
---
# <a name="recipient-properties-for-delivery-status-reports"></a>传递状态报告的收件人属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
对于收件人的传递状态报告, 存在下列属性。 **PR_DELIVER_TIME**未在未送达报告中使用 ([PidTagDeliverTime](pidtagdelivertime-canonical-property.md))。 **PR_NDR_DIAG_CODE**([PidTagNonDeliveryReportDiagCode](pidtagnondeliveryreportdiagcode-canonical-property.md)) 和**PR_NDR_REASON_CODE** ([PidTagNonDeliveryReportReasonCode](pidtagnondeliveryreportreasoncode-canonical-property.md)) 仅用于未送达报告。
  
**表标题**

|**Property**|**Decription**|
|:-----|:-----|
|**PR_DELIVER_TIME**([PidTagDeliverTime](pidtagdelivertime-canonical-property.md))  <br/> |包含原始邮件的送达日期和时间。  <br/> |
|**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |包含给定 MAPI 对象的显示名称。  <br/> |
|**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))  <br/> |包含用于打开和编辑特定 MAPI 对象的属性的 MAPI 条目标识符。  <br/> |
|**PR_NDR_DIAG_CODE**([PidTagNonDeliveryReportDiagCode](pidtagnondeliveryreportdiagcode-canonical-property.md))  <br/> |包含构成未送达报告的一部分的诊断代码。  <br/> |
|**PR_MESSAGE_CLASS**([PidTagMessageClass](pidtagmessageclass-canonical-property.md))  <br/> |包含标识发件人定义的邮件类 (如 IPM) 的文本字符串。便笺.  <br/> |
|**PR_NDR_REASON_CODE**([PidTagNonDeliveryReportReasonCode](pidtagnondeliveryreportreasoncode-canonical-property.md))  <br/> |包含未送达的已编码原因, 不能形成未送达报告的一部分。  <br/> |
|**PR_ORIGINAL_DISPLAY_NAME**([PidTagOriginalDisplayName](pidtagoriginaldisplayname-canonical-property.md))  <br/> |包含从通讯簿复制到个人通讯簿或其他可写通讯簿的条目的原始显示名称。  <br/> |
|**PR_ORIGINAL_ENTRYID**([PidTagOriginalEntryId](pidtagoriginalentryid-canonical-property.md))  <br/> |包含从通讯簿复制到个人通讯簿或其他可写通讯簿的条目的原始条目标识符。  <br/> |
|**PR_ORIGINAL_SEARCH_KEY**([PidTagOriginalSearchKey](pidtagoriginalsearchkey-canonical-property.md))  <br/> |包含从通讯簿复制到个人通讯簿或其他可写通讯簿的条目的原始搜索关键字。  <br/> |
|**PR_RECIPIENT_TYPE**([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))  <br/> |包含邮件收件人的收件人类型。  <br/> |
|**PR_REPORT_TEXT**([PidTagReportText](pidtagreporttext-canonical-property.md))  <br/> |包含邮件系统生成的报告的可选文字。  <br/> |
|**PR_REPORT_TIME**([PidTagReportTime](pidtagreporttime-canonical-property.md))  <br/> |包含邮件系统生成报告的日期和时间。  <br/> |
|**PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))  <br/> |包含二进制可比较的键, 用于标识搜索的相关对象。  <br/> |
|**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))  <br/> |包含一个值, 该值用于将图标与表中的特定行相关联。  <br/> |
|**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))  <br/> |包含对象的类型。  <br/> |
   

