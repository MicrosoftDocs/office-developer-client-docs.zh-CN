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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405854"
---
# <a name="centralizing-the-receipt-of-ndrs"></a><span data-ttu-id="a521a-103">集中处理收到的 NDR</span><span class="sxs-lookup"><span data-stu-id="a521a-103">Centralizing the receipt of NDRs</span></span>

<span data-ttu-id="a521a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a521a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a521a-105">**若要让未送达报告 (当) 多个客户端实例同时运行时，未送达报告将到达中心位置**</span><span class="sxs-lookup"><span data-stu-id="a521a-105">**To have nondelivery reports (NDRs) arrive at a central location when multiple instances of your client are running simultaneously**</span></span>
  
1. <span data-ttu-id="a521a-106">将 **PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md) **) 、PR_REPORT_NAME** ([PidTagReportName](pidtagreportname-canonical-property.md)) 和 **PR_REPORT_SEARCH_KEY** ([PidTagReportSearchKey](pidtagreportsearchkey-canonical-property.md)) 设置为要接收报告的帐户的适当值。</span><span class="sxs-lookup"><span data-stu-id="a521a-106">Set **PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md)), **PR_REPORT_NAME** ([PidTagReportName](pidtagreportname-canonical-property.md)), and **PR_REPORT_SEARCH_KEY** ([PidTagReportSearchKey](pidtagreportsearchkey-canonical-property.md)) to the appropriate values for the account that is to receive the reports.</span></span> <span data-ttu-id="a521a-107">如有必要，通过调用 [IAddrBook：：CreateOneOff 创建](iaddrbook-createoneoff.md) 条目标识符。</span><span class="sxs-lookup"><span data-stu-id="a521a-107">Create the entry identifier by calling [IAddrBook::CreateOneOff](iaddrbook-createoneoff.md) if necessary.</span></span> 
    
2. <span data-ttu-id="a521a-108">请注意，有些邮件系统将忽略您请求的报告帐户，并将其发送给发起方。</span><span class="sxs-lookup"><span data-stu-id="a521a-108">Understand that there are messaging systems that will ignore the account you've requested for reports and send them to the originator.</span></span> <span data-ttu-id="a521a-109">请通过以下两种策略减少对需要移动报告管理员的影响：</span><span class="sxs-lookup"><span data-stu-id="a521a-109">Reduce the impact that this will have on administrators that will need to move reports around by:</span></span>
    
- <span data-ttu-id="a521a-110">为原始邮件提供一个不同的邮件类别，如 IPM。Note.MSNNews。</span><span class="sxs-lookup"><span data-stu-id="a521a-110">Giving your original message a distinct message class, such as IPM.Note.MSNNews.</span></span> <span data-ttu-id="a521a-111">查找具有类 Report.IPM.Note.MSNNews.NDR 的传入邮件，然后将它们转发到预期报告到达的帐户。</span><span class="sxs-lookup"><span data-stu-id="a521a-111">Look for incoming messages with class Report.IPM.Note.MSNNews.NDR and forward them to the account you intended reports to come to.</span></span> <span data-ttu-id="a521a-112">同时，将电子邮件发送到忽略未送达报告帐户的邮件系统，以表明它应遵守 PR_REPORT_ENTRYID **属性。**</span><span class="sxs-lookup"><span data-stu-id="a521a-112">At the same time, send email to the messaging system that ignored your nondelivery report account to communicate that it should honor the **PR_REPORT_ENTRYID** property.</span></span> 
    
- <span data-ttu-id="a521a-113">大多数不遵守 MAPI 邮件 **PR_REPORT_ENTRYID** 也不遵守 MAPI 邮件类约定。</span><span class="sxs-lookup"><span data-stu-id="a521a-113">Most messaging systems which do not honor **PR_REPORT_ENTRYID** will not honor the MAPI message class conventions either.</span></span> <span data-ttu-id="a521a-114">因此，您将收到类似于注释的一些内容。</span><span class="sxs-lookup"><span data-stu-id="a521a-114">Therefore, you'll receive something that looks like a note.</span></span> <span data-ttu-id="a521a-115">这有点难以处理，因为输入是可变的。</span><span class="sxs-lookup"><span data-stu-id="a521a-115">This is a little harder to deal with because the input is so variable.</span></span> <span data-ttu-id="a521a-116">如果您从表示"无法送达"的单词列表中找到内容或原始主题中的某些内容，请查看主题并转发主题。</span><span class="sxs-lookup"><span data-stu-id="a521a-116">Look at the subject and forward it if you find either something from a list of words that mean "undeliverable" or something from your original subject.</span></span> <span data-ttu-id="a521a-117">请准备好随着时间的推移调整这些列表。</span><span class="sxs-lookup"><span data-stu-id="a521a-117">Be prepared to tune these lists over time.</span></span> 
    

