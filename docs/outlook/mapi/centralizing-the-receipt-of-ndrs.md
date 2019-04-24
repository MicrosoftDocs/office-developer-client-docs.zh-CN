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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332660"
---
# <a name="centralizing-the-receipt-of-ndrs"></a><span data-ttu-id="1b1c9-103">集中处理收到的 NDR</span><span class="sxs-lookup"><span data-stu-id="1b1c9-103">Centralizing the receipt of NDRs</span></span>

<span data-ttu-id="1b1c9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1b1c9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1b1c9-105">**当同时运行客户端的多个实例时, 将 nondelivery 报告 (ndr) 到达一个中心位置**</span><span class="sxs-lookup"><span data-stu-id="1b1c9-105">**To have nondelivery reports (NDRs) arrive at a central location when multiple instances of your client are running simultaneously**</span></span>
  
1. <span data-ttu-id="1b1c9-106">将**PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md))、 **PR_REPORT_NAME** ([PidTagReportName](pidtagreportname-canonical-property.md)) 和**PR_REPORT_SEARCH_KEY** ([PidTagReportSearchKey](pidtagreportsearchkey-canonical-property.md)) 设置为要接收的帐户的相应值报告。</span><span class="sxs-lookup"><span data-stu-id="1b1c9-106">Set **PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md)), **PR_REPORT_NAME** ([PidTagReportName](pidtagreportname-canonical-property.md)), and **PR_REPORT_SEARCH_KEY** ([PidTagReportSearchKey](pidtagreportsearchkey-canonical-property.md)) to the appropriate values for the account that is to receive the reports.</span></span> <span data-ttu-id="1b1c9-107">通过调用[IAddrBook:: CreateOneOff (](iaddrbook-createoneoff.md)如有必要) 创建条目标识符。</span><span class="sxs-lookup"><span data-stu-id="1b1c9-107">Create the entry identifier by calling [IAddrBook::CreateOneOff](iaddrbook-createoneoff.md) if necessary.</span></span> 
    
2. <span data-ttu-id="1b1c9-108">了解邮件系统将忽略您为报告请求的帐户, 并将其发送给原始发件人。</span><span class="sxs-lookup"><span data-stu-id="1b1c9-108">Understand that there are messaging systems that will ignore the account you've requested for reports and send them to the originator.</span></span> <span data-ttu-id="1b1c9-109">降低此操作将对将报告移动所需的管理员的影响, 具体取决于:</span><span class="sxs-lookup"><span data-stu-id="1b1c9-109">Reduce the impact that this will have on administrators that will need to move reports around by:</span></span>
    
- <span data-ttu-id="1b1c9-110">为原始邮件提供一个不同的邮件类, 如 IPM。MSNNews。</span><span class="sxs-lookup"><span data-stu-id="1b1c9-110">Giving your original message a distinct message class, such as IPM.Note.MSNNews.</span></span> <span data-ttu-id="1b1c9-111">查找带有类 Report 的传入邮件。 MSNNews, 并将其转发到您希望报告转到的帐户。</span><span class="sxs-lookup"><span data-stu-id="1b1c9-111">Look for incoming messages with class Report.IPM.Note.MSNNews.NDR and forward them to the account you intended reports to come to.</span></span> <span data-ttu-id="1b1c9-112">同时, 将电子邮件发送到忽略您的 nondelivery 报告帐户的邮件系统, 以传达它应服从**PR_REPORT_ENTRYID**属性。</span><span class="sxs-lookup"><span data-stu-id="1b1c9-112">At the same time, send email to the messaging system that ignored your nondelivery report account to communicate that it should honor the **PR_REPORT_ENTRYID** property.</span></span> 
    
- <span data-ttu-id="1b1c9-113">大多数不服从**PR_REPORT_ENTRYID**的邮件系统将不服从 MAPI 邮件类约定。</span><span class="sxs-lookup"><span data-stu-id="1b1c9-113">Most messaging systems which do not honor **PR_REPORT_ENTRYID** will not honor the MAPI message class conventions either.</span></span> <span data-ttu-id="1b1c9-114">因此, 你将收到看上去像是注释的内容。</span><span class="sxs-lookup"><span data-stu-id="1b1c9-114">Therefore, you'll receive something that looks like a note.</span></span> <span data-ttu-id="1b1c9-115">由于输入是如此变量, 因此处理起来要困难一些。</span><span class="sxs-lookup"><span data-stu-id="1b1c9-115">This is a little harder to deal with because the input is so variable.</span></span> <span data-ttu-id="1b1c9-116">查看主题并将其转发, 前提是您找到的内容来自表示 "无法送达" 或原始主题中的内容的单词列表。</span><span class="sxs-lookup"><span data-stu-id="1b1c9-116">Look at the subject and forward it if you find either something from a list of words that mean "undeliverable" or something from your original subject.</span></span> <span data-ttu-id="1b1c9-117">准备好在一段时间后调整这些列表。</span><span class="sxs-lookup"><span data-stu-id="1b1c9-117">Be prepared to tune these lists over time.</span></span> 
    

