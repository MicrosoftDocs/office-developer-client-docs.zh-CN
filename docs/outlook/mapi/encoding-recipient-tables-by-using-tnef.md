---
title: 使用 TNEF 对收件人表编码
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cd2f595f-4dd0-4704-b670-6857d6c843ca
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: aa2120b5d64eece76f8882489de4388b04afa053
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591343"
---
# <a name="encoding-recipient-tables-by-using-tnef"></a><span data-ttu-id="70915-103">使用 TNEF 对收件人表编码</span><span class="sxs-lookup"><span data-stu-id="70915-103">Encoding Recipient Tables by Using TNEF</span></span>

  
  
<span data-ttu-id="70915-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="70915-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="70915-105">收件人表编码到 TNEF 流很少需要，因为大多数邮件系统直接支持收件人列表。</span><span class="sxs-lookup"><span data-stu-id="70915-105">The encoding of a recipient table into the TNEF stream is rarely necessary since most messaging systems support recipient lists directly.</span></span> <span data-ttu-id="70915-106">一般情况下，收件人属性传输邮件头中。</span><span class="sxs-lookup"><span data-stu-id="70915-106">In general, the recipient properties are transmitted in the message header.</span></span> <span data-ttu-id="70915-107">收件人表包含必要时，TNEF 可以对收件人表作为其往常处理的一部分进行编码。</span><span class="sxs-lookup"><span data-stu-id="70915-107">When inclusion of the recipient table is necessary, TNEF can encode the recipient table as a part of its usual processing.</span></span> <span data-ttu-id="70915-108">此功能的初始 TNEF 处理阶段。</span><span class="sxs-lookup"><span data-stu-id="70915-108">This is done during the initial phase of TNEF processing.</span></span> <span data-ttu-id="70915-109">传输提供程序可以通过调用不带包含列表中指定的**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性[ITnef::AddProps](itnef-addprops.md)方法包括邮件的收件人表。</span><span class="sxs-lookup"><span data-stu-id="70915-109">The transport provider can include the message's recipient table by calling the [ITnef::AddProps](itnef-addprops.md) method with the **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) property specified in the inclusion list.</span></span> <span data-ttu-id="70915-110">TNEF 从邮件中获取收件人的表、 查询列集，以及到 TNEF 流处理每个表的行。</span><span class="sxs-lookup"><span data-stu-id="70915-110">TNEF gets the recipient table from the message, queries the column set, and processes every row of the table into the TNEF stream.</span></span>
  
<span data-ttu-id="70915-111">一种方法是可用传输提供程序需要编码之前修改收件人的表。</span><span class="sxs-lookup"><span data-stu-id="70915-111">An alternate method is available if the transport provider needs to modify the recipient table before it is encoded.</span></span> <span data-ttu-id="70915-112">传输提供程序可以构造必要的表，然后调用[ITnef::EncodeRecips](itnef-encoderecips.md)方法。</span><span class="sxs-lookup"><span data-stu-id="70915-112">The transport provider can construct the necessary table and then call the [ITnef::EncodeRecips](itnef-encoderecips.md) method.</span></span> <span data-ttu-id="70915-113">如果_lpRecipTable_参数中传递了 NULL，则收件人表不执行直接从邮件为**ITnef::AddProps**所述。</span><span class="sxs-lookup"><span data-stu-id="70915-113">If NULL is passed in the  _lpRecipTable_ parameter, then the recipient table is taken directly from the message as described for **ITnef::AddProps**.</span></span>
  

