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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329741"
---
# <a name="mapi-report-messages"></a><span data-ttu-id="1d4a9-103">MAPI 报告邮件</span><span class="sxs-lookup"><span data-stu-id="1d4a9-103">MAPI Report Messages</span></span>

  
  
<span data-ttu-id="1d4a9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1d4a9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1d4a9-105">报告邮件向其发件人显示有关邮件的状态信息。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-105">Report messages present status information about a message to its sender.</span></span>
  
<span data-ttu-id="1d4a9-106">有两种常规类型的报告消息:</span><span class="sxs-lookup"><span data-stu-id="1d4a9-106">There are two general types of report messages:</span></span>
  
- <span data-ttu-id="1d4a9-107">阅读状态报告。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-107">Read status reports.</span></span>
    
- <span data-ttu-id="1d4a9-108">传递状态报告。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-108">Delivery status reports.</span></span>
    
## <a name="read-status-reports"></a><span data-ttu-id="1d4a9-109">阅读状态报告</span><span class="sxs-lookup"><span data-stu-id="1d4a9-109">Read Status Reports</span></span>

<span data-ttu-id="1d4a9-110">读取状态报告由邮件存储提供程序通过调用[IMAPISupport:: ReadReceipt](imapisupport-readreceipt.md)方法启动, 并发送给由**PR_REPORT_ENTRYID**中的条目标识符表示的收件人 ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md))财产.</span><span class="sxs-lookup"><span data-stu-id="1d4a9-110">Read status reports are initiated by message store providers through a call to the [IMAPISupport::ReadReceipt](imapisupport-readreceipt.md) method and are sent to the recipient represented by the entry identifier in the **PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md)) property.</span></span> <span data-ttu-id="1d4a9-111">读取状态报告不会自动生成;要接收它们的客户端应用程序必须显式请求它们。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-111">Read status reports are not generated automatically; client applications that want to receive them must explicitly request them.</span></span>
  
<span data-ttu-id="1d4a9-112">"已读" 报告指示已设置邮件的读取标志, 在打开、打印、移动或复制邮件时可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-112">A read report indicates that the read flag of a message has been set, which can occur when the message is opened, printed, moved, or copied.</span></span> <span data-ttu-id="1d4a9-113">邮件存储提供程序是否生成读取报告以响应移动或复制操作取决于邮件的目标位置。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-113">Whether or not a message store provider generates a read report in response to a move or copy operation depends on where the message is going.</span></span> <span data-ttu-id="1d4a9-114">如果要将其移动或复制到另一个邮件存储区, 则可能总是会发送一个阅读报告。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-114">If it is being moved or copied to another message store, a read report will most likely always be sent.</span></span> <span data-ttu-id="1d4a9-115">如果要将其移动或复制到当前邮件存储区中, 则可能会发送或不发送阅读报告。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-115">If it is being moved or copied in the current message store, a read report might or might not be sent.</span></span> 
  
<span data-ttu-id="1d4a9-116">未读报告指示邮件的阅读标志未设置, 邮件在被置于 "已删除邮件" 文件夹中之前或在时间限制到期之前未打开。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-116">A nonread report indicates that the read flag of a message is not set and that the message was not opened either before being placed in the Deleted Items folder or before the expiration of a time limit.</span></span> <span data-ttu-id="1d4a9-117">客户端可以调用[IMessage:: SetReadFlag](imessage-setreadflag.md)或[IMAPIFolder:: SetReadFlags](imapifolder-setreadflags.md)方法来设置或清除邮件的阅读标志。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-117">Clients can call the [IMessage::SetReadFlag](imessage-setreadflag.md) or [IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md) method to set or clear a message's read flag.</span></span> 
  
## <a name="delivery-status-reports"></a><span data-ttu-id="1d4a9-118">传递状态报告</span><span class="sxs-lookup"><span data-stu-id="1d4a9-118">Delivery Status Reports</span></span>

<span data-ttu-id="1d4a9-119">传递状态反映在送达报告中, 在邮件到达其预期收件人时发送, 并且在邮件无法到达收件人时发送的 nondelivery 报告中。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-119">Delivery status is reflected in a delivery report, which is sent when a message has reached its intended recipient, and in a nondelivery report, which is sent when a message could not reach a recipient.</span></span> <span data-ttu-id="1d4a9-120">传递状态报告将发送给**PR_REPORT_ENTRYID**属性中的条目标识符表示的收件人, 如果该属性不存在, 则发送给发件人。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-120">Delivery status reports are sent to the recipient represented by the entry identifier in the **PR_REPORT_ENTRYID** property or to the sender if this property is not present.</span></span> 
  
<span data-ttu-id="1d4a9-121">传递报告仅按请求发送, 不包括原始邮件。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-121">Delivery reports are sent by request only and do not include the original message.</span></span> <span data-ttu-id="1d4a9-122">Nondelivery 报告将自动发送, 除非发出请求禁止显示这些报告。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-122">Nondelivery reports are sent automatically unless a request is made to suppress them.</span></span> <span data-ttu-id="1d4a9-123">Nondelivery 报告将原始邮件作为附件包括在内, 以便在阻止传递不再存在问题的情况下, 使报告的收件人能够重新发送邮件。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-123">Nondelivery reports include the original message as an attachment to enable the report's recipient to resend the message in case whatever blocked the delivery is no longer a problem.</span></span> <span data-ttu-id="1d4a9-124">在最初调用[IMessage:: SubmitMessage](imessage-submitmessage.md)方法时, 附加的邮件类似于原始的邮件。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-124">The attached message resembles the original as it existed when the [IMessage::SubmitMessage](imessage-submitmessage.md) method was called to send it initially.</span></span> 
  
<span data-ttu-id="1d4a9-125">在调用[IMAPISupport:: StatusRecips](imapisupport-statusrecips.md)方法时, 传输提供程序会生成一个或多个传递状态报告。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-125">One or more delivery status reports are generated by transport providers when they call the [IMAPISupport::StatusRecips](imapisupport-statusrecips.md) method.</span></span> <span data-ttu-id="1d4a9-126">传输提供程序撰写邮件的收件人列表。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-126">Transport providers compose a list of recipients for a message.</span></span> <span data-ttu-id="1d4a9-127">收件人是否收到报告以及生成的报告类型取决于以下内容:</span><span class="sxs-lookup"><span data-stu-id="1d4a9-127">Whether or not a recipient receives a report and the type of report that is generated depends on the following:</span></span> 
  
- <span data-ttu-id="1d4a9-128">送达报告转到在邮件放入邮件存储区之前将**PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md)) 属性设置为 TRUE 的收件人。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-128">Delivery reports go to recipients that set the **PR_ORIGINATOR_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorDeliveryReportRequested](pidtagoriginatordeliveryreportrequested-canonical-property.md)) property to TRUE before the message was placed in the message store.</span></span>
    
- <span data-ttu-id="1d4a9-129">Nondelivery 报告转到未将**PR_ORIGINATOR_NON_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorNonDeliveryReportRequested](pidtagoriginatornondeliveryreportrequested-canonical-property.md)) 属性设置为 FALSE 的收件人。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-129">Nondelivery reports go to recipients that did not set the **PR_ORIGINATOR_NON_DELIVERY_REPORT_REQUESTED** ([PidTagOriginatorNonDeliveryReportRequested](pidtagoriginatornondeliveryreportrequested-canonical-property.md)) property to FALSE.</span></span> 
    
<span data-ttu-id="1d4a9-130">显示 nondelivery 报告所需的几乎所有信息都包含在附加邮件的 "收件人" 表中。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-130">Almost all of the information necessary to display a nondelivery report is contained in the recipient table of the attached message.</span></span> <span data-ttu-id="1d4a9-131">有些属性来自报告本身。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-131">A few properties are from the report itself.</span></span> <span data-ttu-id="1d4a9-132">对于送达报告, 报告的 "收件人" 表和一些报告属性中包含必要的信息。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-132">For delivery reports, the necessary information is contained in the recipient table of the report and in a few report properties.</span></span> 
  
<span data-ttu-id="1d4a9-133">报告是具有不同邮件类别的邮件, 基于发送的邮件的类。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-133">Reports are messages with distinct message classes, based on the class of the sent message.</span></span> <span data-ttu-id="1d4a9-134">大多数服务提供商使用一种命名约定, 通过此约定, 邮件类由用句点分隔的多个部分组成。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-134">Most service providers use a naming convention whereby the message class is composed of several parts separated by periods.</span></span> <span data-ttu-id="1d4a9-135">第一部分是 "报告", 而最后一部分是代表报告类型的常量。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-135">The first part is "Report" and the last part is a constant that represents the report type.</span></span> <span data-ttu-id="1d4a9-136">中间部件是为已发送邮件的类保留的。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-136">The middle part is reserved for the class of the sent message.</span></span> <span data-ttu-id="1d4a9-137">例如, 由于送达报告使用常量 DR, 因此关于 IPM 的送达报告的邮件类。注释消息将为 "报告"。 **IPM. dr.**。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-137">For example, because a delivery report uses the constant DR, the message class for a delivery report about an IPM.Note message would be **Report.IPM.Note.DR**.</span></span>
  
<span data-ttu-id="1d4a9-138">下表显示了代表报告类型的常量。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-138">The following table shows the constants that represent the types of reports.</span></span>
  
|<span data-ttu-id="1d4a9-139">**报告类型**</span><span class="sxs-lookup"><span data-stu-id="1d4a9-139">**Report type**</span></span>|<span data-ttu-id="1d4a9-140">**邮件类中使用的常量**</span><span class="sxs-lookup"><span data-stu-id="1d4a9-140">**Constant used in message class**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1d4a9-141">读取</span><span class="sxs-lookup"><span data-stu-id="1d4a9-141">Read</span></span>  <br/> |<span data-ttu-id="1d4a9-142">IPNRN</span><span class="sxs-lookup"><span data-stu-id="1d4a9-142">IPNRN</span></span>  <br/> |
|<span data-ttu-id="1d4a9-143">未读</span><span class="sxs-lookup"><span data-stu-id="1d4a9-143">Nonread</span></span>  <br/> |<span data-ttu-id="1d4a9-144">IPNNRN</span><span class="sxs-lookup"><span data-stu-id="1d4a9-144">IPNNRN</span></span>  <br/> |
|<span data-ttu-id="1d4a9-145">Delivery</span><span class="sxs-lookup"><span data-stu-id="1d4a9-145">Delivery</span></span>  <br/> |<span data-ttu-id="1d4a9-146">DR</span><span class="sxs-lookup"><span data-stu-id="1d4a9-146">DR</span></span>  <br/> |
|<span data-ttu-id="1d4a9-147">Nondelivery</span><span class="sxs-lookup"><span data-stu-id="1d4a9-147">Nondelivery</span></span>  <br/> |<span data-ttu-id="1d4a9-148">发送</span><span class="sxs-lookup"><span data-stu-id="1d4a9-148">NDR</span></span>  <br/> |
   
<span data-ttu-id="1d4a9-149">交互客户端可以使用 MAPI 提供的标准窗体或在报表的邮件类的窗体管理器中注册的自定义窗体来显示报告消息。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-149">Interactive clients can display report messages by using standard forms provided by MAPI, or custom forms that have been registered with the form manager for the report's message class.</span></span> <span data-ttu-id="1d4a9-150">接收 IPM 的 nondelivery 报告的客户端。例如, 邮件可以显示标准 MAPI 表单, 该窗体显示失败收件人的列表和错误的建议原因。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-150">Clients that receive a nondelivery report for an IPM.Note message, for example, can display the standard MAPI form that presents a list of the failed recipients and a suggested reason for the failure.</span></span> <span data-ttu-id="1d4a9-151">表单还允许用户根据需要重新发送邮件。</span><span class="sxs-lookup"><span data-stu-id="1d4a9-151">The form also enables the user to resend the message, if desired.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1d4a9-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1d4a9-152">See also</span></span>



[<span data-ttu-id="1d4a9-153">MAPI 邮件</span><span class="sxs-lookup"><span data-stu-id="1d4a9-153">MAPI Messages</span></span>](mapi-messages.md)

