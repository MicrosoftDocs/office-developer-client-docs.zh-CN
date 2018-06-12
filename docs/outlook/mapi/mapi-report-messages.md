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
# <a name="mapi-report-messages"></a><span data-ttu-id="0619d-103">MAPI 报告邮件</span><span class="sxs-lookup"><span data-stu-id="0619d-103">MAPI Report Messages</span></span>

  
  
<span data-ttu-id="0619d-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0619d-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0619d-105">报告给其发件人的邮件上存在一条消息有关的状态信息。</span><span class="sxs-lookup"><span data-stu-id="0619d-105">Report messages present status information about a message to its sender.</span></span>
  
<span data-ttu-id="0619d-106">有两种常规报告消息：</span><span class="sxs-lookup"><span data-stu-id="0619d-106">There are two general types of report messages:</span></span>
  
- <span data-ttu-id="0619d-107">阅读状态报告。</span><span class="sxs-lookup"><span data-stu-id="0619d-107">Read status reports.</span></span>
    
- <span data-ttu-id="0619d-108">传递状态报告。</span><span class="sxs-lookup"><span data-stu-id="0619d-108">Delivery status reports.</span></span>
    
## <a name="read-status-reports"></a><span data-ttu-id="0619d-109">读取状态报告</span><span class="sxs-lookup"><span data-stu-id="0619d-109">Read Status Reports</span></span>

<span data-ttu-id="0619d-110">读取状态报告的消息存储提供程序通过调用[IMAPISupport::ReadReceipt](imapisupport-readreceipt.md)方法启动和发送给收件人由**PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md)) 中的项标识符属性。</span><span class="sxs-lookup"><span data-stu-id="0619d-110">Read status reports are initiated by message store providers through a call to the [IMAPISupport::ReadReceipt](imapisupport-readreceipt.md) method and are sent to the recipient represented by the entry identifier in the **PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md)) property.</span></span> <span data-ttu-id="0619d-111">不会自动; 生成读取状态报告要接收这些客户端应用程序必须明确请求它们。</span><span class="sxs-lookup"><span data-stu-id="0619d-111">Read status reports are not generated automatically; client applications that want to receive them must explicitly request them.</span></span>
  
<span data-ttu-id="0619d-112">读取的报表指示已会打开、 打印、 移动或复制邮件时设置消息的读取标志。</span><span class="sxs-lookup"><span data-stu-id="0619d-112">A read report indicates that the read flag of a message has been set, which can occur when the message is opened, printed, moved, or copied.</span></span> <span data-ttu-id="0619d-113">消息存储提供程序生成阅读的报告以响应移动或复制操作取决于该消息在何处。</span><span class="sxs-lookup"><span data-stu-id="0619d-113">Whether or not a message store provider generates a read report in response to a move or copy operation depends on where the message is going.</span></span> <span data-ttu-id="0619d-114">如果已发送正在移动或复制到另一个消息存储，很可能读取的报表将始终。</span><span class="sxs-lookup"><span data-stu-id="0619d-114">If it is being moved or copied to another message store, a read report will most likely always be sent.</span></span> <span data-ttu-id="0619d-115">如果它正在移动或复制当前邮件存储区，读取的报表可能或可能不会发送。</span><span class="sxs-lookup"><span data-stu-id="0619d-115">If it is being moved or copied in the current message store, a read report might or might not be sent.</span></span> 
  
<span data-ttu-id="0619d-116">Nonread 的报告指示邮件的读取标志未设置和之前在已删除邮件文件夹中放置或过期的时间限制，不打开邮件。</span><span class="sxs-lookup"><span data-stu-id="0619d-116">A nonread report indicates that the read flag of a message is not set and that the message was not opened either before being placed in the Deleted Items folder or before the expiration of a time limit.</span></span> <span data-ttu-id="0619d-117">客户端可以调用[IMessage::SetReadFlag](imessage-setreadflag.md)或[IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md)方法来设置或清除邮件阅读的标志。</span><span class="sxs-lookup"><span data-stu-id="0619d-117">Clients can call the [IMessage::SetReadFlag](imessage-setreadflag.md) or [IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md) method to set or clear a message's read flag.</span></span> 
  
## <a name="delivery-status-reports"></a><span data-ttu-id="0619d-118">传递状态报告</span><span class="sxs-lookup"><span data-stu-id="0619d-118">Delivery Status Reports</span></span>

<span data-ttu-id="0619d-119">传递状态被反映在送达报告，将它发送一条消息已达到其预期接收人时，和一条消息无法到达收件人时，会发送原件报表。</span><span class="sxs-lookup"><span data-stu-id="0619d-119">Delivery status is reflected in a delivery report, which is sent when a message has reached its intended recipient, and in a nondelivery report, which is sent when a message could not reach a recipient.</span></span> <span data-ttu-id="0619d-120">如果该属性不存在此参数，传递状态报告会发送到由**PR_REPORT_ENTRYID**属性中的项标识符的收件人或发件人。</span><span class="sxs-lookup"><span data-stu-id="0619d-120">Delivery status reports are sent to the recipient represented by the entry identifier in the **PR_REPORT_ENTRYID** property or to the sender if this property is not present.</span></span> 
  
<span data-ttu-id="0619d-121">送达报告请求仅发送和不包含原始邮件。</span><span class="sxs-lookup"><span data-stu-id="0619d-121">Delivery reports are sent by request only and do not include the original message.</span></span> <span data-ttu-id="0619d-122">除非发出请求禁止它们，将自动发送未送达报告。</span><span class="sxs-lookup"><span data-stu-id="0619d-122">Nondelivery reports are sent automatically unless a request is made to suppress them.</span></span> <span data-ttu-id="0619d-123">未送达报告包括原始邮件作为附件启用报告的收件人，以防任何阻止传递不再是问题重新发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="0619d-123">Nondelivery reports include the original message as an attachment to enable the report's recipient to resend the message in case whatever blocked the delivery is no longer a problem.</span></span> <span data-ttu-id="0619d-124">附加的邮件类似于原始[IMessage::SubmitMessage](imessage-submitmessage.md)方法调用最初发送时存在。</span><span class="sxs-lookup"><span data-stu-id="0619d-124">The attached message resembles the original as it existed when the [IMessage::SubmitMessage](imessage-submitmessage.md) method was called to send it initially.</span></span> 
  
<span data-ttu-id="0619d-125">[IMAPISupport::StatusRecips](imapisupport-statusrecips.md)方法时由传输提供程序生成一个或多个传递状态报告。</span><span class="sxs-lookup"><span data-stu-id="0619d-125">One or more delivery status reports are generated by transport providers when they call the [IMAPISupport::StatusRecips](imapisupport-statusrecips.md) method.</span></span> <span data-ttu-id="0619d-126">传输提供程序撰写邮件的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="0619d-126">Transport providers compose a list of recipients for a message.</span></span> <span data-ttu-id="0619d-127">收件人收到报表和生成的报告类型取决于以下方面：</span><span class="sxs-lookup"><span data-stu-id="0619d-127">Whether or not a recipient receives a report and the type of report that is generated depends on the following:</span></span> 
  
- <span data-ttu-id="0619d-128">送达报告转到收件人的邮件发出邮件存储区之前将**邮件已被阅读**([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md)) 属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="0619d-128">Delivery reports go to recipients that set the **PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md)) property to TRUE before the message was placed in the message store.</span></span>
    
- <span data-ttu-id="0619d-129">未送达报告转到收件人的未按**PR_ORIGINATOR_NON_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorNonDeliveryReportRequested](pidtagoriginatornondeliveryreportrequested-canonical-property.md)) 属性设置为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="0619d-129">Nondelivery reports go to recipients that did not set the **PR_ORIGINATOR_NON_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorNonDeliveryReportRequested](pidtagoriginatornondeliveryreportrequested-canonical-property.md)) property to FALSE.</span></span> 
    
<span data-ttu-id="0619d-130">附加的邮件的收件人表中包含几乎所有显示原件报表所需的信息。</span><span class="sxs-lookup"><span data-stu-id="0619d-130">Almost all of the information necessary to display a nondelivery report is contained in the recipient table of the attached message.</span></span> <span data-ttu-id="0619d-131">从报表本身是几个属性。</span><span class="sxs-lookup"><span data-stu-id="0619d-131">A few properties are from the report itself.</span></span> <span data-ttu-id="0619d-132">送达报告和几个报告属性中报告的收件人表包含所需的信息。</span><span class="sxs-lookup"><span data-stu-id="0619d-132">For delivery reports, the necessary information is contained in the recipient table of the report and in a few report properties.</span></span> 
  
<span data-ttu-id="0619d-133">报告是邮件的与不同邮件类，基于已发送类的邮件。</span><span class="sxs-lookup"><span data-stu-id="0619d-133">Reports are messages with distinct message classes, based on the class of the sent message.</span></span> <span data-ttu-id="0619d-134">大多数服务提供商使用的命名约定，借此邮件类是多个部分组成句点隔开。</span><span class="sxs-lookup"><span data-stu-id="0619d-134">Most service providers use a naming convention whereby the message class is composed of several parts separated by periods.</span></span> <span data-ttu-id="0619d-135">第一部分是"报告"，最后部分是一个常量，代表报表类型。</span><span class="sxs-lookup"><span data-stu-id="0619d-135">The first part is "Report" and the last part is a constant that represents the report type.</span></span> <span data-ttu-id="0619d-136">已发送的邮件类专门的中间部分。</span><span class="sxs-lookup"><span data-stu-id="0619d-136">The middle part is reserved for the class of the sent message.</span></span> <span data-ttu-id="0619d-137">例如，由于送达报告使用常量的灾难恢复，传递的邮件类 IPM 有关报告。注意邮件采用**Report.IPM.Note.DR**。</span><span class="sxs-lookup"><span data-stu-id="0619d-137">For example, because a delivery report uses the constant DR, the message class for a delivery report about an IPM.Note message would be **Report.IPM.Note.DR**.</span></span>
  
<span data-ttu-id="0619d-138">下表显示了表示的报告类型的常量。</span><span class="sxs-lookup"><span data-stu-id="0619d-138">The following table shows the constants that represent the types of reports.</span></span>
  
|<span data-ttu-id="0619d-139">**报告类型**</span><span class="sxs-lookup"><span data-stu-id="0619d-139">**Report type**</span></span>|<span data-ttu-id="0619d-140">**邮件类中使用的常量**</span><span class="sxs-lookup"><span data-stu-id="0619d-140">**Constant used in message class**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0619d-141">已阅读</span><span class="sxs-lookup"><span data-stu-id="0619d-141">Read</span></span>  <br/> |<span data-ttu-id="0619d-142">IPNRN</span><span class="sxs-lookup"><span data-stu-id="0619d-142">IPNRN</span></span>  <br/> |
|<span data-ttu-id="0619d-143">Nonread</span><span class="sxs-lookup"><span data-stu-id="0619d-143">Nonread</span></span>  <br/> |<span data-ttu-id="0619d-144">IPNNRN</span><span class="sxs-lookup"><span data-stu-id="0619d-144">IPNNRN</span></span>  <br/> |
|<span data-ttu-id="0619d-145">传递</span><span class="sxs-lookup"><span data-stu-id="0619d-145">Delivery</span></span>  <br/> |<span data-ttu-id="0619d-146">灾难恢复</span><span class="sxs-lookup"><span data-stu-id="0619d-146">DR</span></span>  <br/> |
|<span data-ttu-id="0619d-147">原件</span><span class="sxs-lookup"><span data-stu-id="0619d-147">Nondelivery</span></span>  <br/> |<span data-ttu-id="0619d-148">NDR</span><span class="sxs-lookup"><span data-stu-id="0619d-148">NDR</span></span>  <br/> |
   
<span data-ttu-id="0619d-149">交互式客户端可以通过使用由 MAPI，提供的标准窗体或报表的邮件类的窗体管理器与已注册的自定义窗体显示报告消息。</span><span class="sxs-lookup"><span data-stu-id="0619d-149">Interactive clients can display report messages by using standard forms provided by MAPI, or custom forms that have been registered with the form manager for the report's message class.</span></span> <span data-ttu-id="0619d-150">接收 IPM 原件报表的客户端。注意消息，例如，可以显示标准 MAPI 表单提供失败的收件人和建议的失败原因的列表。</span><span class="sxs-lookup"><span data-stu-id="0619d-150">Clients that receive a nondelivery report for an IPM.Note message, for example, can display the standard MAPI form that presents a list of the failed recipients and a suggested reason for the failure.</span></span> <span data-ttu-id="0619d-151">如果需要，窗体还允许用户重新发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="0619d-151">The form also enables the user to resend the message, if desired.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="0619d-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0619d-152">See also</span></span>



[<span data-ttu-id="0619d-153">MAPI 邮件</span><span class="sxs-lookup"><span data-stu-id="0619d-153">MAPI Messages</span></span>](mapi-messages.md)

