---
title: 集中 Ndr 的回执
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: fbe1f4f6-28f8-40b8-b551-192c0ba48c18
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 0af587bd07de9445f143be316798059eaef402e0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774651"
---
# <a name="centralizing-the-receipt-of-ndrs"></a><span data-ttu-id="79556-103">集中 Ndr 的回执</span><span class="sxs-lookup"><span data-stu-id="79556-103">Centralizing the receipt of NDRs</span></span>

<span data-ttu-id="79556-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="79556-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="79556-105">**具有未送达报告 (Ndr) 到达一个中心位置时同时运行多个客户端的实例**</span><span class="sxs-lookup"><span data-stu-id="79556-105">**To have nondelivery reports (NDRs) arrive at a central location when multiple instances of your client are running simultaneously**</span></span>
  
1. <span data-ttu-id="79556-106">将**PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md))、 **PR_REPORT_NAME** ([PidTagReportName](pidtagreportname-canonical-property.md)) 和**PR_REPORT_SEARCH_KEY** ([PidTagReportSearchKey](pidtagreportsearchkey-canonical-property.md)) 设置为适当的值是接收的帐户报告。</span><span class="sxs-lookup"><span data-stu-id="79556-106">Set **PR_REPORT_ENTRYID** ([PidTagReportEntryId](pidtagreportentryid-canonical-property.md)), **PR_REPORT_NAME** ([PidTagReportName](pidtagreportname-canonical-property.md)), and **PR_REPORT_SEARCH_KEY** ([PidTagReportSearchKey](pidtagreportsearchkey-canonical-property.md)) to the appropriate values for the account that is to receive the reports.</span></span> <span data-ttu-id="79556-107">通过调用[IAddrBook::CreateOneOff](iaddrbook-createoneoff.md) ，根据需要创建的项标识符。</span><span class="sxs-lookup"><span data-stu-id="79556-107">Create the entry identifier by calling [IAddrBook::CreateOneOff](iaddrbook-createoneoff.md) if necessary.</span></span> 
    
2. <span data-ttu-id="79556-108">了解将忽略帐户已请求报告并将它们发送到原始发件人的邮件系统。</span><span class="sxs-lookup"><span data-stu-id="79556-108">Understand that there are messaging systems that will ignore the account you've requested for reports and send them to the originator.</span></span> <span data-ttu-id="79556-109">减少这会在需要通过移动报告的管理员的影响：</span><span class="sxs-lookup"><span data-stu-id="79556-109">Reduce the impact that this will have on administrators that will need to move reports around by:</span></span>
    
- <span data-ttu-id="79556-110">提供您的原始邮件不同邮件类 IPM 如。Note.MSNNews。</span><span class="sxs-lookup"><span data-stu-id="79556-110">Giving your original message a distinct message class, such as IPM.Note.MSNNews.</span></span> <span data-ttu-id="79556-111">查找与类 Report.IPM.Note.MSNNews.NDR 的传入消息，并将它们转发给您能报告前置的帐户。</span><span class="sxs-lookup"><span data-stu-id="79556-111">Look for incoming messages with class Report.IPM.Note.MSNNews.NDR and forward them to the account you intended reports to come to.</span></span> <span data-ttu-id="79556-112">同时，到忽略您原件报表帐户进行通信，它应服从**PR_REPORT_ENTRYID**属性的邮件系统发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="79556-112">At the same time, send email to the messaging system that ignored your nondelivery report account to communicate that it should honor the **PR_REPORT_ENTRYID** property.</span></span> 
    
- <span data-ttu-id="79556-113">大多数邮件系统的不遵守**PR_REPORT_ENTRYID**不将也遵守的 MAPI 邮件类约定。</span><span class="sxs-lookup"><span data-stu-id="79556-113">Most messaging systems which do not honor **PR_REPORT_ENTRYID** will not honor the MAPI message class conventions either.</span></span> <span data-ttu-id="79556-114">因此，您会收到类似一条注释的。</span><span class="sxs-lookup"><span data-stu-id="79556-114">Therefore, you'll receive something that looks like a note.</span></span> <span data-ttu-id="79556-115">这是有点更加复杂，因为输入因此变量处理。</span><span class="sxs-lookup"><span data-stu-id="79556-115">This is a little harder to deal with because the input is so variable.</span></span> <span data-ttu-id="79556-116">查看主题，并将其转接，如果您发现任一从列表中的单词"未送达"该 mean 或内容从您的原始主题。</span><span class="sxs-lookup"><span data-stu-id="79556-116">Look at the subject and forward it if you find either something from a list of words that mean "undeliverable" or something from your original subject.</span></span> <span data-ttu-id="79556-117">准备随着时间的推移调整这些列表。</span><span class="sxs-lookup"><span data-stu-id="79556-117">Be prepared to tune these lists over time.</span></span> 
    

