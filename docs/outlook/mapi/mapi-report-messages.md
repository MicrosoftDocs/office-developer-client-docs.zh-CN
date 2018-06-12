---
title: MAPI 报告邮件
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 824eb670-16b7-49bf-9992-39fe0586a552
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: addf93cadae418017a40ba448328d2e1fc1decf6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776307"
---
# <a name="mapi-report-messages"></a>MAPI 报告邮件

  
  
**适用于**： Outlook 
  
报告给其发件人的邮件上存在一条消息有关的状态信息。
  
有两种常规报告消息：
  
- 阅读状态报告。
    
- 传递状态报告。
    
## <a name="read-status-reports"></a>读取状态报告

读取状态报告的消息存储提供程序通过调用[IMAPISupport::ReadReceipt](imapisupport-readreceipt.md)方法启动和发送给收件人由**PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md)) 中的项标识符属性。 不会自动; 生成读取状态报告要接收这些客户端应用程序必须明确请求它们。
  
读取的报表指示已会打开、 打印、 移动或复制邮件时设置消息的读取标志。 消息存储提供程序生成阅读的报告以响应移动或复制操作取决于该消息在何处。 如果已发送正在移动或复制到另一个消息存储，很可能读取的报表将始终。 如果它正在移动或复制当前邮件存储区，读取的报表可能或可能不会发送。 
  
Nonread 的报告指示邮件的读取标志未设置和之前在已删除邮件文件夹中放置或过期的时间限制，不打开邮件。 客户端可以调用[IMessage::SetReadFlag](imessage-setreadflag.md)或[IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md)方法来设置或清除邮件阅读的标志。 
  
## <a name="delivery-status-reports"></a>传递状态报告

传递状态被反映在送达报告，将它发送一条消息已达到其预期接收人时，和一条消息无法到达收件人时，会发送原件报表。 如果该属性不存在此参数，传递状态报告会发送到由**PR_REPORT_ENTRYID**属性中的项标识符的收件人或发件人。 
  
送达报告请求仅发送和不包含原始邮件。 除非发出请求禁止它们，将自动发送未送达报告。 未送达报告包括原始邮件作为附件启用报告的收件人，以防任何阻止传递不再是问题重新发送的邮件。 附加的邮件类似于原始[IMessage::SubmitMessage](imessage-submitmessage.md)方法调用最初发送时存在。 
  
[IMAPISupport::StatusRecips](imapisupport-statusrecips.md)方法时由传输提供程序生成一个或多个传递状态报告。 传输提供程序撰写邮件的收件人列表。 收件人收到报表和生成的报告类型取决于以下方面： 
  
- 送达报告转到收件人的邮件发出邮件存储区之前将**邮件已被阅读**([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md)) 属性设置为 TRUE。
    
- 未送达报告转到收件人的未按**PR_ORIGINATOR_NON_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorNonDeliveryReportRequested](pidtagoriginatornondeliveryreportrequested-canonical-property.md)) 属性设置为 FALSE。 
    
附加的邮件的收件人表中包含几乎所有显示原件报表所需的信息。 从报表本身是几个属性。 送达报告和几个报告属性中报告的收件人表包含所需的信息。 
  
报告是邮件的与不同邮件类，基于已发送类的邮件。 大多数服务提供商使用的命名约定，借此邮件类是多个部分组成句点隔开。 第一部分是"报告"，最后部分是一个常量，代表报表类型。 已发送的邮件类专门的中间部分。 例如，由于送达报告使用常量的灾难恢复，传递的邮件类 IPM 有关报告。注意邮件采用**Report.IPM.Note.DR**。
  
下表显示了表示的报告类型的常量。
  
|**报告类型**|**邮件类中使用的常量**|
|:-----|:-----|
|已阅读  <br/> |IPNRN  <br/> |
|Nonread  <br/> |IPNNRN  <br/> |
|传递  <br/> |灾难恢复  <br/> |
|原件  <br/> |NDR  <br/> |
   
交互式客户端可以通过使用由 MAPI，提供的标准窗体或报表的邮件类的窗体管理器与已注册的自定义窗体显示报告消息。 接收 IPM 原件报表的客户端。注意消息，例如，可以显示标准 MAPI 表单提供失败的收件人和建议的失败原因的列表。 如果需要，窗体还允许用户重新发送的邮件。 
  
## <a name="see-also"></a>另请参阅



[MAPI 邮件](mapi-messages.md)

