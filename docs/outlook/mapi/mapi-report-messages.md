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
  
报告邮件向其发件人显示有关邮件的状态信息。
  
有两种常规类型的报告消息:
  
- 阅读状态报告。
    
- 传递状态报告。
    
## <a name="read-status-reports"></a>阅读状态报告

读取状态报告由邮件存储提供程序通过调用[IMAPISupport:: ReadReceipt](imapisupport-readreceipt.md)方法启动, 并发送给由**PR_REPORT_ENTRYID**中的条目标识符表示的收件人 ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md))财产. 读取状态报告不会自动生成;要接收它们的客户端应用程序必须显式请求它们。
  
"已读" 报告指示已设置邮件的读取标志, 在打开、打印、移动或复制邮件时可能会发生这种情况。 邮件存储提供程序是否生成读取报告以响应移动或复制操作取决于邮件的目标位置。 如果要将其移动或复制到另一个邮件存储区, 则可能总是会发送一个阅读报告。 如果要将其移动或复制到当前邮件存储区中, 则可能会发送或不发送阅读报告。 
  
未读报告指示邮件的阅读标志未设置, 邮件在被置于 "已删除邮件" 文件夹中之前或在时间限制到期之前未打开。 客户端可以调用[IMessage:: SetReadFlag](imessage-setreadflag.md)或[IMAPIFolder:: SetReadFlags](imapifolder-setreadflags.md)方法来设置或清除邮件的阅读标志。 
  
## <a name="delivery-status-reports"></a>传递状态报告

传递状态反映在送达报告中, 在邮件到达其预期收件人时发送, 并且在邮件无法到达收件人时发送的 nondelivery 报告中。 传递状态报告将发送给**PR_REPORT_ENTRYID**属性中的条目标识符表示的收件人, 如果该属性不存在, 则发送给发件人。 
  
传递报告仅按请求发送, 不包括原始邮件。 Nondelivery 报告将自动发送, 除非发出请求禁止显示这些报告。 Nondelivery 报告将原始邮件作为附件包括在内, 以便在阻止传递不再存在问题的情况下, 使报告的收件人能够重新发送邮件。 在最初调用[IMessage:: SubmitMessage](imessage-submitmessage.md)方法时, 附加的邮件类似于原始的邮件。 
  
在调用[IMAPISupport:: StatusRecips](imapisupport-statusrecips.md)方法时, 传输提供程序会生成一个或多个传递状态报告。 传输提供程序撰写邮件的收件人列表。 收件人是否收到报告以及生成的报告类型取决于以下内容: 
  
- 送达报告转到在邮件放入邮件存储区之前将**PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md)) 属性设置为 TRUE 的收件人。
    
- Nondelivery 报告转到未将**PR_ORIGINATOR_NON_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorNonDeliveryReportRequested](pidtagoriginatornondeliveryreportrequested-canonical-property.md)) 属性设置为 FALSE 的收件人。 
    
显示 nondelivery 报告所需的几乎所有信息都包含在附加邮件的 "收件人" 表中。 有些属性来自报告本身。 对于送达报告, 报告的 "收件人" 表和一些报告属性中包含必要的信息。 
  
报告是具有不同邮件类别的邮件, 基于发送的邮件的类。 大多数服务提供商使用一种命名约定, 通过此约定, 邮件类由用句点分隔的多个部分组成。 第一部分是 "报告", 而最后一部分是代表报告类型的常量。 中间部件是为已发送邮件的类保留的。 例如, 由于送达报告使用常量 DR, 因此关于 IPM 的送达报告的邮件类。注释消息将为 "报告"。 **IPM. dr.**。
  
下表显示了代表报告类型的常量。
  
|**报告类型**|**邮件类中使用的常量**|
|:-----|:-----|
|读取  <br/> |IPNRN  <br/> |
|未读  <br/> |IPNNRN  <br/> |
|Delivery  <br/> |DR  <br/> |
|Nondelivery  <br/> |发送  <br/> |
   
交互客户端可以使用 MAPI 提供的标准窗体或在报表的邮件类的窗体管理器中注册的自定义窗体来显示报告消息。 接收 IPM 的 nondelivery 报告的客户端。例如, 邮件可以显示标准 MAPI 表单, 该窗体显示失败收件人的列表和错误的建议原因。 表单还允许用户根据需要重新发送邮件。 
  
## <a name="see-also"></a>另请参阅



[MAPI 邮件](mapi-messages.md)

