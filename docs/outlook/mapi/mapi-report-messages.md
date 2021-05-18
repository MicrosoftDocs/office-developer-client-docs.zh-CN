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
# <a name="mapi-report-messages"></a><span data-ttu-id="f5f53-103">MAPI 报告邮件</span><span class="sxs-lookup"><span data-stu-id="f5f53-103">MAPI Report Messages</span></span>

  
  
<span data-ttu-id="f5f53-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f5f53-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f5f53-105">报告邮件向发件人显示有关邮件的状态信息。</span><span class="sxs-lookup"><span data-stu-id="f5f53-105">Report messages present status information about a message to its sender.</span></span>
  
<span data-ttu-id="f5f53-106">有两种常规类型的报告邮件：</span><span class="sxs-lookup"><span data-stu-id="f5f53-106">There are two general types of report messages:</span></span>
  
- <span data-ttu-id="f5f53-107">读取状态报告。</span><span class="sxs-lookup"><span data-stu-id="f5f53-107">Read status reports.</span></span>
    
- <span data-ttu-id="f5f53-108">传递状态报告。</span><span class="sxs-lookup"><span data-stu-id="f5f53-108">Delivery status reports.</span></span>
    
## <a name="read-status-reports"></a><span data-ttu-id="f5f53-109">读取状态报告</span><span class="sxs-lookup"><span data-stu-id="f5f53-109">Read Status Reports</span></span>

<span data-ttu-id="f5f53-110">阅读状态报告由邮件存储提供程序通过 [调用 IMAPISupport：：ReadReceipt](imapisupport-readreceipt.md) 方法启动，并发送给 **由 PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md)) 属性中的条目标识符表示的收件人。</span><span class="sxs-lookup"><span data-stu-id="f5f53-110">Read status reports are initiated by message store providers through a call to the [IMAPISupport::ReadReceipt](imapisupport-readreceipt.md) method and are sent to the recipient represented by the entry identifier in the **PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md)) property.</span></span> <span data-ttu-id="f5f53-111">不会自动生成读取状态报告;要接收的客户端应用程序必须显式请求它们。</span><span class="sxs-lookup"><span data-stu-id="f5f53-111">Read status reports are not generated automatically; client applications that want to receive them must explicitly request them.</span></span>
  
<span data-ttu-id="f5f53-112">阅读报告指示已设置邮件的阅读标志，该标记可在打开、打印、移动或复制邮件时发生。</span><span class="sxs-lookup"><span data-stu-id="f5f53-112">A read report indicates that the read flag of a message has been set, which can occur when the message is opened, printed, moved, or copied.</span></span> <span data-ttu-id="f5f53-113">邮件存储提供程序是否生成读取报告以响应移动或复制操作取决于邮件的发送位置。</span><span class="sxs-lookup"><span data-stu-id="f5f53-113">Whether or not a message store provider generates a read report in response to a move or copy operation depends on where the message is going.</span></span> <span data-ttu-id="f5f53-114">如果正在将邮件移动或复制到其他邮件存储，则阅读报告很可能始终发送。</span><span class="sxs-lookup"><span data-stu-id="f5f53-114">If it is being moved or copied to another message store, a read report will most likely always be sent.</span></span> <span data-ttu-id="f5f53-115">如果当前邮件存储中正在移动或复制邮件，则可能会发送读取报告，也可能不发送。</span><span class="sxs-lookup"><span data-stu-id="f5f53-115">If it is being moved or copied in the current message store, a read report might or might not be sent.</span></span> 
  
<span data-ttu-id="f5f53-116">未读报告指示未设置邮件的阅读标志，并且邮件在被放入"已删除邮件"文件夹或超过时间限制之前未打开。</span><span class="sxs-lookup"><span data-stu-id="f5f53-116">A nonread report indicates that the read flag of a message is not set and that the message was not opened either before being placed in the Deleted Items folder or before the expiration of a time limit.</span></span> <span data-ttu-id="f5f53-117">客户端可以调用 [IMessage：：SetReadFlag](imessage-setreadflag.md) 或 [IMAPIFolder：：SetReadFlags](imapifolder-setreadflags.md) 方法来设置或清除邮件的读取标志。</span><span class="sxs-lookup"><span data-stu-id="f5f53-117">Clients can call the [IMessage::SetReadFlag](imessage-setreadflag.md) or [IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md) method to set or clear a message's read flag.</span></span> 
  
## <a name="delivery-status-reports"></a><span data-ttu-id="f5f53-118">传递状态报告</span><span class="sxs-lookup"><span data-stu-id="f5f53-118">Delivery Status Reports</span></span>

<span data-ttu-id="f5f53-119">传递状态反映在送达报告（邮件到达预期收件人时发送）和未送达报告（邮件无法到达收件人时发送）。</span><span class="sxs-lookup"><span data-stu-id="f5f53-119">Delivery status is reflected in a delivery report, which is sent when a message has reached its intended recipient, and in a nondelivery report, which is sent when a message could not reach a recipient.</span></span> <span data-ttu-id="f5f53-120">传递状态报告将发送给由 **PR_REPORT_ENTRYID** 属性中的条目标识符表示的收件人，或发送给发件人（如果此属性不存在）。</span><span class="sxs-lookup"><span data-stu-id="f5f53-120">Delivery status reports are sent to the recipient represented by the entry identifier in the **PR_REPORT_ENTRYID** property or to the sender if this property is not present.</span></span> 
  
<span data-ttu-id="f5f53-121">送达报告仅通过请求发送，不包括原始邮件。</span><span class="sxs-lookup"><span data-stu-id="f5f53-121">Delivery reports are sent by request only and do not include the original message.</span></span> <span data-ttu-id="f5f53-122">除非发出取消送达报告的请求，否则将自动发送未送达报告。</span><span class="sxs-lookup"><span data-stu-id="f5f53-122">Nondelivery reports are sent automatically unless a request is made to suppress them.</span></span> <span data-ttu-id="f5f53-123">未送达报告将原始邮件作为附件包含，以便报告收件人在阻止传递不再出现问题时重新发送邮件。</span><span class="sxs-lookup"><span data-stu-id="f5f53-123">Nondelivery reports include the original message as an attachment to enable the report's recipient to resend the message in case whatever blocked the delivery is no longer a problem.</span></span> <span data-ttu-id="f5f53-124">附加的邮件类似于最初调用 [IMessage：：SubmitMessage](imessage-submitmessage.md) 方法以发送它时的原始邮件。</span><span class="sxs-lookup"><span data-stu-id="f5f53-124">The attached message resembles the original as it existed when the [IMessage::SubmitMessage](imessage-submitmessage.md) method was called to send it initially.</span></span> 
  
<span data-ttu-id="f5f53-125">一个或多个传递状态报告由传输提供程序在调用 [IMAPISupport：：StatusRecips](imapisupport-statusrecips.md) 方法时生成。</span><span class="sxs-lookup"><span data-stu-id="f5f53-125">One or more delivery status reports are generated by transport providers when they call the [IMAPISupport::StatusRecips](imapisupport-statusrecips.md) method.</span></span> <span data-ttu-id="f5f53-126">传输提供程序为邮件撰写收件人列表。</span><span class="sxs-lookup"><span data-stu-id="f5f53-126">Transport providers compose a list of recipients for a message.</span></span> <span data-ttu-id="f5f53-127">收件人是否收到报告以及生成的报告类型取决于以下内容：</span><span class="sxs-lookup"><span data-stu-id="f5f53-127">Whether or not a recipient receives a report and the type of report that is generated depends on the following:</span></span> 
  
- <span data-ttu-id="f5f53-128">送达报告将转到将 PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED ( [PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md)) 属性设置为 TRUE 的收件人，然后再将邮件放入邮件存储中。</span><span class="sxs-lookup"><span data-stu-id="f5f53-128">Delivery reports go to recipients that set the **PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md)) property to TRUE before the message was placed in the message store.</span></span>
    
- <span data-ttu-id="f5f53-129">未送达报告将转到未将 PR_ORIGINATOR_NON_DELIVERY_REPORT_REQUESTED ([PidTagOriginatorNonDeliveryReportRequested](pidtagoriginatornondeliveryreportrequested-canonical-property.md)) 设置为 FALSE 的收件人。 </span><span class="sxs-lookup"><span data-stu-id="f5f53-129">Nondelivery reports go to recipients that did not set the **PR_ORIGINATOR_NON_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorNonDeliveryReportRequested](pidtagoriginatornondeliveryreportrequested-canonical-property.md)) property to FALSE.</span></span> 
    
<span data-ttu-id="f5f53-130">显示未送达报告所需的几乎所有信息都包含在附加邮件的收件人表中。</span><span class="sxs-lookup"><span data-stu-id="f5f53-130">Almost all of the information necessary to display a nondelivery report is contained in the recipient table of the attached message.</span></span> <span data-ttu-id="f5f53-131">一些属性来自报表本身。</span><span class="sxs-lookup"><span data-stu-id="f5f53-131">A few properties are from the report itself.</span></span> <span data-ttu-id="f5f53-132">对于送达报告，必要的信息包含在报告的收件人表和一些报告属性中。</span><span class="sxs-lookup"><span data-stu-id="f5f53-132">For delivery reports, the necessary information is contained in the recipient table of the report and in a few report properties.</span></span> 
  
<span data-ttu-id="f5f53-133">报告是具有不同邮件类别的邮件，基于已发送邮件的类。</span><span class="sxs-lookup"><span data-stu-id="f5f53-133">Reports are messages with distinct message classes, based on the class of the sent message.</span></span> <span data-ttu-id="f5f53-134">大多数服务提供商都使用命名约定，其中邮件类由多个部分组成，由句点分隔。</span><span class="sxs-lookup"><span data-stu-id="f5f53-134">Most service providers use a naming convention whereby the message class is composed of several parts separated by periods.</span></span> <span data-ttu-id="f5f53-135">第一部分是"Report"，最后一部分是一个代表报表类型的常量。</span><span class="sxs-lookup"><span data-stu-id="f5f53-135">The first part is "Report" and the last part is a constant that represents the report type.</span></span> <span data-ttu-id="f5f53-136">中间部分保留为已发送邮件的类。</span><span class="sxs-lookup"><span data-stu-id="f5f53-136">The middle part is reserved for the class of the sent message.</span></span> <span data-ttu-id="f5f53-137">例如，由于送达报告使用常量 DR，因此有关 IPM 的送达报告的邮件类。Note message would be **Report.IPM.Note.DR**.</span><span class="sxs-lookup"><span data-stu-id="f5f53-137">For example, because a delivery report uses the constant DR, the message class for a delivery report about an IPM.Note message would be **Report.IPM.Note.DR**.</span></span>
  
<span data-ttu-id="f5f53-138">下表显示了代表报告类型的常量。</span><span class="sxs-lookup"><span data-stu-id="f5f53-138">The following table shows the constants that represent the types of reports.</span></span>
  
|<span data-ttu-id="f5f53-139">**报告类型**</span><span class="sxs-lookup"><span data-stu-id="f5f53-139">**Report type**</span></span>|<span data-ttu-id="f5f53-140">**邮件类中使用的常量**</span><span class="sxs-lookup"><span data-stu-id="f5f53-140">**Constant used in message class**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f5f53-141">阅读</span><span class="sxs-lookup"><span data-stu-id="f5f53-141">Read</span></span>  <br/> |<span data-ttu-id="f5f53-142">IPNRN</span><span class="sxs-lookup"><span data-stu-id="f5f53-142">IPNRN</span></span>  <br/> |
|<span data-ttu-id="f5f53-143">Nonread</span><span class="sxs-lookup"><span data-stu-id="f5f53-143">Nonread</span></span>  <br/> |<span data-ttu-id="f5f53-144">IPNNRN</span><span class="sxs-lookup"><span data-stu-id="f5f53-144">IPNNRN</span></span>  <br/> |
|<span data-ttu-id="f5f53-145">Delivery</span><span class="sxs-lookup"><span data-stu-id="f5f53-145">Delivery</span></span>  <br/> |<span data-ttu-id="f5f53-146">DR</span><span class="sxs-lookup"><span data-stu-id="f5f53-146">DR</span></span>  <br/> |
|<span data-ttu-id="f5f53-147">未送达</span><span class="sxs-lookup"><span data-stu-id="f5f53-147">Nondelivery</span></span>  <br/> |<span data-ttu-id="f5f53-148">NDR</span><span class="sxs-lookup"><span data-stu-id="f5f53-148">NDR</span></span>  <br/> |
   
<span data-ttu-id="f5f53-149">交互式客户端可以使用 MAPI 提供的标准窗体显示报表邮件，或者使用窗体管理器为报表的邮件类注册的自定义窗体来显示报表邮件。</span><span class="sxs-lookup"><span data-stu-id="f5f53-149">Interactive clients can display report messages by using standard forms provided by MAPI, or custom forms that have been registered with the form manager for the report's message class.</span></span> <span data-ttu-id="f5f53-150">接收 IPM 未送达报告的客户端。例如，注释邮件可以显示标准的 MAPI 窗体，该窗体显示失败收件人的列表以及失败的建议原因。</span><span class="sxs-lookup"><span data-stu-id="f5f53-150">Clients that receive a nondelivery report for an IPM.Note message, for example, can display the standard MAPI form that presents a list of the failed recipients and a suggested reason for the failure.</span></span> <span data-ttu-id="f5f53-151">该窗体还允许用户重新发送邮件（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="f5f53-151">The form also enables the user to resend the message, if desired.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f5f53-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5f53-152">See also</span></span>



[<span data-ttu-id="f5f53-153">MAPI 邮件</span><span class="sxs-lookup"><span data-stu-id="f5f53-153">MAPI Messages</span></span>](mapi-messages.md)

