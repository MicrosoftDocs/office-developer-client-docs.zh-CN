---
title: 使用 TNEF 对收件人表进行编码
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: cd2f595f-4dd0-4704-b670-6857d6c843ca
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1ed047424e4a6d64c08b511a15769c081a0d8c4e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417957"
---
# <a name="encoding-recipient-tables-by-using-tnef"></a><span data-ttu-id="8262a-103">使用 TNEF 对收件人表进行编码</span><span class="sxs-lookup"><span data-stu-id="8262a-103">Encoding Recipient Tables by Using TNEF</span></span>

  
  
<span data-ttu-id="8262a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8262a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8262a-105">由于大多数邮件系统直接支持收件人列表, 因此很少需要将收件人表的编码转换为 TNEF 流。</span><span class="sxs-lookup"><span data-stu-id="8262a-105">The encoding of a recipient table into the TNEF stream is rarely necessary since most messaging systems support recipient lists directly.</span></span> <span data-ttu-id="8262a-106">通常情况下, 收件人属性在邮件头中传输。</span><span class="sxs-lookup"><span data-stu-id="8262a-106">In general, the recipient properties are transmitted in the message header.</span></span> <span data-ttu-id="8262a-107">当必须包含收件人表时, TNEF 可以将收件人表编码为其常规处理的一部分。</span><span class="sxs-lookup"><span data-stu-id="8262a-107">When inclusion of the recipient table is necessary, TNEF can encode the recipient table as a part of its usual processing.</span></span> <span data-ttu-id="8262a-108">这是在 TNEF 处理的初始阶段完成的。</span><span class="sxs-lookup"><span data-stu-id="8262a-108">This is done during the initial phase of TNEF processing.</span></span> <span data-ttu-id="8262a-109">传输提供程序可以通过调用包含列表中指定的**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) 属性的[ITnef:: AddProps](itnef-addprops.md)方法来包含邮件的收件人表。</span><span class="sxs-lookup"><span data-stu-id="8262a-109">The transport provider can include the message's recipient table by calling the [ITnef::AddProps](itnef-addprops.md) method with the **PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md)) property specified in the inclusion list.</span></span> <span data-ttu-id="8262a-110">TNEF 从邮件中获取收件人表, 查询列集, 并将表中的每一行处理到 TNEF 流中。</span><span class="sxs-lookup"><span data-stu-id="8262a-110">TNEF gets the recipient table from the message, queries the column set, and processes every row of the table into the TNEF stream.</span></span>
  
<span data-ttu-id="8262a-111">如果传输提供程序需要在对收件人表进行编码之前对其进行修改, 则可使用备用方法。</span><span class="sxs-lookup"><span data-stu-id="8262a-111">An alternate method is available if the transport provider needs to modify the recipient table before it is encoded.</span></span> <span data-ttu-id="8262a-112">传输提供程序可以构造必要的表, 然后调用[ITnef:: EncodeRecips](itnef-encoderecips.md)方法。</span><span class="sxs-lookup"><span data-stu-id="8262a-112">The transport provider can construct the necessary table and then call the [ITnef::EncodeRecips](itnef-encoderecips.md) method.</span></span> <span data-ttu-id="8262a-113">如果在_lpRecipTable_参数中传递 NULL, 则从邮件中直接获取收件人表, 如**ITnef:: AddProps**所述。</span><span class="sxs-lookup"><span data-stu-id="8262a-113">If NULL is passed in the  _lpRecipTable_ parameter, then the recipient table is taken directly from the message as described for **ITnef::AddProps**.</span></span>
  

