---
title: MAPI 报告邮件
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 824eb670-16b7-49bf-9992-39fe0586a552
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: aab5c76fb268729f1a50a33e4764905fe3d53405
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405763"
---
# <a name="mapi-report-messages"></a>MAPI 报告邮件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
报告邮件向发件人显示有关邮件的状态信息。
  
有两种常规类型的报告邮件：
  
- 读取状态报告。
    
- 传递状态报告。
    
## <a name="read-status-reports"></a>读取状态报告

阅读状态报告由邮件存储提供程序通过 [调用 IMAPISupport：：ReadReceipt](imapisupport-readreceipt.md) 方法启动，并发送给 **由 PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md)) 属性中的条目标识符表示的收件人。 不会自动生成读取状态报告;要接收的客户端应用程序必须显式请求它们。
  
阅读报告指示已设置邮件的阅读标志，该标记可在打开、打印、移动或复制邮件时发生。 邮件存储提供程序是否生成读取报告以响应移动或复制操作取决于邮件的发送位置。 如果正在将邮件移动或复制到其他邮件存储，则阅读报告很可能始终发送。 如果当前邮件存储中正在移动或复制邮件，则可能会发送读取报告，也可能不发送。 
  
未读报告指示未设置邮件的阅读标志，并且邮件在被放入"已删除邮件"文件夹或超过时间限制之前未打开。 客户端可以调用 [IMessage：：SetReadFlag](imessage-setreadflag.md) 或 [IMAPIFolder：：SetReadFlags](imapifolder-setreadflags.md) 方法来设置或清除邮件的读取标志。 
  
## <a name="delivery-status-reports"></a>传递状态报告

传递状态反映在送达报告（邮件到达预期收件人时发送）和未送达报告（邮件无法到达收件人时发送）。 传递状态报告将发送给由 **PR_REPORT_ENTRYID** 属性中的条目标识符表示的收件人，或发送给发件人（如果此属性不存在）。 
  
送达报告仅通过请求发送，不包括原始邮件。 除非发出取消送达报告的请求，否则将自动发送未送达报告。 未送达报告将原始邮件作为附件包含，以便报告收件人在阻止传递不再出现问题时重新发送邮件。 附加的邮件类似于最初调用 [IMessage：：SubmitMessage](imessage-submitmessage.md) 方法以发送它时的原始邮件。 
  
一个或多个传递状态报告由传输提供程序在调用 [IMAPISupport：：StatusRecips](imapisupport-statusrecips.md) 方法时生成。 传输提供程序为邮件撰写收件人列表。 收件人是否收到报告以及生成的报告类型取决于以下内容： 
  
- 送达报告将转到将 PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED ( [PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md)) 属性设置为 TRUE 的收件人，然后再将邮件放入邮件存储中。
    
- 未送达报告将转到未将 PR_ORIGINATOR_NON_DELIVERY_REPORT_REQUESTED ([PidTagOriginatorNonDeliveryReportRequested](pidtagoriginatornondeliveryreportrequested-canonical-property.md)) 设置为 FALSE 的收件人。  
    
显示未送达报告所需的几乎所有信息都包含在附加邮件的收件人表中。 一些属性来自报表本身。 对于送达报告，必要的信息包含在报告的收件人表和一些报告属性中。 
  
报告是具有不同邮件类别的邮件，基于已发送邮件的类。 大多数服务提供商都使用命名约定，其中邮件类由多个部分组成，由句点分隔。 第一部分是"Report"，最后一部分是一个代表报表类型的常量。 中间部分保留为已发送邮件的类。 例如，由于送达报告使用常量 DR，因此有关 IPM 的送达报告的邮件类。Note message would be **Report.IPM.Note.DR**.
  
下表显示了代表报告类型的常量。
  
|**报告类型**|**邮件类中使用的常量**|
|:-----|:-----|
|阅读  <br/> |IPNRN  <br/> |
|Nonread  <br/> |IPNNRN  <br/> |
|Delivery  <br/> |DR  <br/> |
|未送达  <br/> |NDR  <br/> |
   
交互式客户端可以使用 MAPI 提供的标准窗体显示报表邮件，或者使用窗体管理器为报表的邮件类注册的自定义窗体来显示报表邮件。 接收 IPM 未送达报告的客户端。例如，注释邮件可以显示标准的 MAPI 窗体，该窗体显示失败收件人的列表以及失败的建议原因。 该窗体还允许用户重新发送邮件（如果需要）。 
  
## <a name="see-also"></a>另请参阅



[MAPI 邮件](mapi-messages.md)

