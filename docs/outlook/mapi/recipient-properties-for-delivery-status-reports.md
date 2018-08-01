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
ms.openlocfilehash: a6ff82fa3cc4a7ad243285e9eb93b0ec880a3bd4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778581"
---
# <a name="recipient-properties-for-delivery-status-reports"></a>传递状态报告的收件人属性

  
  
**适用于**： Outlook 
  
以下属性都存在的收件人的传递状态报告。 **PR_DELIVER_TIME**未送达报告不用于 ([PidTagDeliverTime](pidtagdelivertime-canonical-property.md))。 **PR_NDR_DIAG_CODE**([PidTagNonDeliveryReportDiagCode](pidtagnondeliveryreportdiagcode-canonical-property.md)) 和**PR_NDR_REASON_CODE** ([PidTagNonDeliveryReportReasonCode](pidtagnondeliveryreportreasoncode-canonical-property.md)) 仅用于未送达报告。
  
**表标题**

|**属性**|**说明**|
|:-----|:-----|
|**PR_DELIVER_TIME**([PidTagDeliverTime](pidtagdelivertime-canonical-property.md))  <br/> |包含的日期和时间的原始邮件已送达。  <br/> |
|**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))  <br/> |包含给定的 MAPI 对象的显示名称。  <br/> |
|**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))  <br/> |包含用于打开和编辑特定的 MAPI 对象的属性的 MAPI 条目标识符。  <br/> |
|**PR_NDR_DIAG_CODE**([PidTagNonDeliveryReportDiagCode](pidtagnondeliveryreportdiagcode-canonical-property.md))  <br/> |包含诊断代码的表单未送达报告的一部分。  <br/> |
|**PR_MESSAGE_CLASS**([PidTagMessageClass](pidtagmessageclass-canonical-property.md))  <br/> |包含标识-定义发件人的邮件类 IPM 如文本字符串。请注意。  <br/> |
|**PR_NDR_REASON_CODE**([PidTagNonDeliveryReportReasonCode](pidtagnondeliveryreportreasoncode-canonical-property.md))  <br/> |包含未送达的窗体未送达报告的一部分编码的原因。  <br/> |
|**PR_ORIGINAL_DISPLAY_NAME**([PidTagOriginalDisplayName](pidtagoriginaldisplayname-canonical-property.md))  <br/> |包含通讯簿中复制到个人通讯簿或其他可写通讯簿条目的原始显示名称。  <br/> |
|**PR_ORIGINAL_ENTRYID**([PidTagOriginalEntryId](pidtagoriginalentryid-canonical-property.md))  <br/> |包含复制到个人通讯簿通讯簿或其他写通讯簿条目的原始项标识符。  <br/> |
|**PR_ORIGINAL_SEARCH_KEY**([PidTagOriginalSearchKey](pidtagoriginalsearchkey-canonical-property.md))  <br/> |包含原始搜索密钥复制到个人通讯簿通讯簿或其他写通讯簿中的条目。  <br/> |
|**PR_RECIPIENT_TYPE**([PidTagRecipientType](pidtagrecipienttype-canonical-property.md))  <br/> |包含邮件收件人的收件人类型。  <br/> |
|**PR_REPORT_TEXT**([PidTagReportText](pidtagreporttext-canonical-property.md))  <br/> |包含可选文字由消息系统生成的报告。  <br/> |
|**PR_REPORT_TIME**([PidTagReportTime](pidtagreporttime-canonical-property.md))  <br/> |包含的日期和时间在邮件系统时生成报表。  <br/> |
|**PR_SEARCH_KEY**([PidTagSearchKey](pidtagsearchkey-canonical-property.md))  <br/> |包含一个标识用于搜索的相关的对象的二进制相当关键字。  <br/> |
|**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))  <br/> |包含用于将图标与特定的表格行关联的值。  <br/> |
|**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))  <br/> |包含对象的类型。  <br/> |
   

