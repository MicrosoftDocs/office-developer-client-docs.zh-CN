---
title: 传递状态报表的收件人属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 9b2e287e-1cf8-4b8f-b92c-a065ed264d02
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 784cac21aac5de18952f3768af9b8f189f604981
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411083"
---
# <a name="recipient-properties-for-delivery-status-reports"></a>传递状态报表的收件人属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
收件人的传递状态报告具有以下属性。 **PR_DELIVER_TIME (** 未送达报告) [PidTagDeliverTime](pidtagdelivertime-canonical-property.md) 报告。 **PR_NDR_DIAG_CODE (** [PidTagNonDeliveryReportDiagCode](pidtagnondeliveryreportdiagcode-canonical-property.md)) 和 **PR_NDR_REASON_CODE** ([PidTagNonDeliveryReportReasonCode](pidtagnondeliveryreportreasoncode-canonical-property.md)) 仅用于未送达报告。
  
**表标题**

|**Property**|**描述**|
|:-----|:-----|
|**PR_DELIVER_TIME (** [PidTagDeliverTime](pidtagdelivertime-canonical-property.md))   <br/> |包含传递原始邮件的日期和时间。  <br/> |
|**PR_DISPLAY_NAME (** [PidTagDisplayName](pidtagdisplayname-canonical-property.md))   <br/> |包含显示名称 MAPI 对象的属性。  <br/> |
|**PR_ENTRYID (** [PidTagEntryId](pidtagentryid-canonical-property.md))   <br/> |包含一个 MAPI 条目标识符，该标识符用于打开和编辑特定 MAPI 对象的属性。  <br/> |
|**PR_NDR_DIAG_CODE (** [PidTagNonDeliveryReportDiagCode](pidtagnondeliveryreportdiagcode-canonical-property.md))   <br/> |包含构成未送达报告的一部分的诊断代码。  <br/> |
|**PR_MESSAGE_CLASS (** [PidTagMessageClass](pidtagmessageclass-canonical-property.md))   <br/> |包含标识发件人定义的消息类别的文本字符串，例如 IPM.Note。  <br/> |
|**PR_NDR_REASON_CODE (** [PidTagNonDeliveryReportReasonCode](pidtagnondeliveryreportreasoncode-canonical-property.md))   <br/> |包含未送达的编码原因，该原因构成未送达报告的一部分。  <br/> |
|**PR_ORIGINAL_DISPLAY_NAME (** [PidTagOriginalDisplayName](pidtagoriginaldisplayname-canonical-property.md))   <br/> |包含从通讯簿显示名称个人通讯簿或其他可写通讯簿的条目的原始记录。  <br/> |
|**PR_ORIGINAL_ENTRYID (** [PidTagOriginalEntryId)](pidtagoriginalentryid-canonical-property.md)  <br/> |包含从通讯簿复制到个人通讯簿或其他可写通讯簿的条目的原始条目标识符。  <br/> |
|**PR_ORIGINAL_SEARCH_KEY (** [PidTagOriginalSearchKey)](pidtagoriginalsearchkey-canonical-property.md)  <br/> |包含从通讯簿复制到个人通讯簿或其他可写通讯簿的条目的原始搜索键。  <br/> |
|**PR_RECIPIENT_TYPE (** [PidTagRecipientType](pidtagrecipienttype-canonical-property.md))   <br/> |包含邮件收件人的收件人类型。  <br/> |
|**PR_REPORT_TEXT (** [PidTagReportText](pidtagreporttext-canonical-property.md))   <br/> |包含邮件系统生成的报告的可选文本。  <br/> |
|**PR_REPORT_TIME (** [PidTagReportTime](pidtagreporttime-canonical-property.md))   <br/> |包含邮件系统生成报告的日期和时间。  <br/> |
|**PR_SEARCH_KEY (** [PidTagSearchKey](pidtagsearchkey-canonical-property.md))   <br/> |包含标识搜索的相关对象的二进制比较键。  <br/> |
|**PR_DISPLAY_TYPE (** [PidTagDisplayType](pidtagdisplaytype-canonical-property.md))   <br/> |包含一个值，该值用于将图标与表的特定行关联。  <br/> |
|**PR_OBJECT_TYPE (** [PidTagObjectType](pidtagobjecttype-canonical-property.md))   <br/> |包含对象的类型。  <br/> |
   

