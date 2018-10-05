---
title: 分析 POP3 帐户的邮件下载历史记录
manager: soliver
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 394e1430-04d6-4d61-be13-eb695309fa73
description: 本主题介绍 POP3 BLOB 值，该值代表 POP3 帐户，以确定已下载或删除该帐户的消息的消息下载历史记录的结构。
ms.openlocfilehash: 44a799f6b6fbe2a2841522c18405149a470b0236
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25389006"
---
# <a name="parsing-the-message-download-history-for-a-pop3-account"></a><span data-ttu-id="af9af-103">分析 POP3 帐户的邮件下载历史记录</span><span class="sxs-lookup"><span data-stu-id="af9af-103">Parsing the message download history for a POP3 account</span></span>

<span data-ttu-id="af9af-104">本主题介绍 POP3 BLOB 值，该值代表 POP3 帐户，以确定已下载或删除该帐户的消息的消息下载历史记录的结构。</span><span class="sxs-lookup"><span data-stu-id="af9af-104">This topic describes the structure of the POP3 BLOB that represents the message download history of a POP3 account, to identify the messages that have been downloaded or deleted on that account.</span></span>

<span data-ttu-id="af9af-105"><a name="OL15Con_AuxRef_ParsingMsgsHistory_WhyParseHistory"> </a></span><span class="sxs-lookup"><span data-stu-id="af9af-105"></span></span>

## <a name="why-parse-the-message-download-history"></a><span data-ttu-id="af9af-106">为什么解析的消息下载历史记录？</span><span class="sxs-lookup"><span data-stu-id="af9af-106">Why parse the message download history?</span></span>

<span data-ttu-id="af9af-107">Outlook 邮局协议 (POP) 提供程序允许用户检索并在其本地设备上的新电子邮件下载并随后保留或删除这些邮件服务器上的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="af9af-107">The Post Office Protocol (POP) provider for Outlook allows users to retrieve and download new email messages on their local device, and subsequently to leave or delete these email messages on the mail server.</span></span> <span data-ttu-id="af9af-108">当邮件客户端检查新邮件，若要下载时，它具有能够识别和仅下载新邮件的收件箱。</span><span class="sxs-lookup"><span data-stu-id="af9af-108">When the mail client checks for new messages to download, it has to be able to identify and download only the new messages for that Inbox.</span></span> <span data-ttu-id="af9af-109">邮件客户端第一个使用 UIDL （唯一 ID 列出） 命令获取以往任何时候都已传递给为唯一标识符 (UID) 的收件箱每封邮件的地图来达到此目的。</span><span class="sxs-lookup"><span data-stu-id="af9af-109">The mail client does this by first using the UIDL (Unique ID Listing) command to obtain a map of each message that has ever been delivered to that Inbox to a unique identifier (UID).</span></span> <span data-ttu-id="af9af-110">客户端还获取的已下载或删除该客户端上的收件箱邮件的消息下载历史记录。</span><span class="sxs-lookup"><span data-stu-id="af9af-110">The client also gets the message download history for messages that have been downloaded or deleted for the Inbox on that client.</span></span> <span data-ttu-id="af9af-111">使用邮件 UID 地图和下载历史记录，客户端可以然后确定存在这些邮件从历史记录，通过新建，因此，应下载。</span><span class="sxs-lookup"><span data-stu-id="af9af-111">Using the message UID map and download history, the client can then identify those messages that are absent from the history as new and, hence, should be downloaded.</span></span>
  
<span data-ttu-id="af9af-112">若要获取的收件箱邮件下载历史记录：</span><span class="sxs-lookup"><span data-stu-id="af9af-112">To get the messages download history for an Inbox:</span></span>
  
- <span data-ttu-id="af9af-113">按照中[查找邮件下载历史记录 POP3 帐户](locating-the-message-download-history-for-a-pop3-account.md)以查找[PidTagAttachDataBinary](https://msdn.microsoft.com/library/3b0a8b28-863e-4b96-a4c0-fdb8f40555b9%28Office.15%29.aspx)属性，其中包含代表 POP3 帐户的消息历史记录二进制大型对象 (BLOB) 的步骤。</span><span class="sxs-lookup"><span data-stu-id="af9af-113">Follow the steps in [Locating the message download history for a POP3 account](locating-the-message-download-history-for-a-pop3-account.md) to find the [PidTagAttachDataBinary](https://msdn.microsoft.com/library/3b0a8b28-863e-4b96-a4c0-fdb8f40555b9%28Office.15%29.aspx) property, which contains a binary large object (BLOB) that represents the message history for a POP3 account.</span></span> 
    
- <span data-ttu-id="af9af-114">阅读本主题，其中介绍 BLOB 的结构，并显示了示例标识的已下载或删除的 POP3 帐户的收件箱邮件的 BLOB。</span><span class="sxs-lookup"><span data-stu-id="af9af-114">Read this topic, which describes the structure of the BLOB, and shows an example BLOB to identify messages that have been downloaded or deleted for the Inbox of the POP3 account.</span></span>

<span data-ttu-id="af9af-115"><a name="OL15Con_AuxRef_ParsingMsgsHistory_BLOBStructure"> </a></span><span class="sxs-lookup"><span data-stu-id="af9af-115"></span></span>

## <a name="pop-blob-structure"></a><span data-ttu-id="af9af-116">POP BLOB 结构</span><span class="sxs-lookup"><span data-stu-id="af9af-116">POP BLOB structure</span></span>

<span data-ttu-id="af9af-117">POP BLOB 结构，如表 1 中所述开头**版本**和**计数**后, 跟**计数**大量资源标记，其中每个以 null 结尾的两个字段。</span><span class="sxs-lookup"><span data-stu-id="af9af-117">The POP BLOB structure, as described in Table 1, begins with two fields, **Version** and **Count**, followed by a **Count** number of resource tags, each of which is null-terminated.</span></span> 
  
<span data-ttu-id="af9af-118">**表 1。结构 BLOB 表示消息下载历史记录的 POP3 帐户**</span><span class="sxs-lookup"><span data-stu-id="af9af-118">**Table 1. Structure of the BLOB that represents the message download history of a POP3 account**</span></span>

|<span data-ttu-id="af9af-119">**BLOB 中的字段**</span><span class="sxs-lookup"><span data-stu-id="af9af-119">**Field in BLOB**</span></span>|<span data-ttu-id="af9af-120">**Size**</span><span class="sxs-lookup"><span data-stu-id="af9af-120">**Size**</span></span>|<span data-ttu-id="af9af-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="af9af-121">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="af9af-122">**版本**</span><span class="sxs-lookup"><span data-stu-id="af9af-122">**Version**</span></span> <br/> |<span data-ttu-id="af9af-123">2 个字节</span><span class="sxs-lookup"><span data-stu-id="af9af-123">2 bytes</span></span>  <br/> |<span data-ttu-id="af9af-124">必须为 3 (**PBLOB_VERSION_NUM**)。</span><span class="sxs-lookup"><span data-stu-id="af9af-124">Must be 3 (**PBLOB_VERSION_NUM**).</span></span>  <br/> |
|<span data-ttu-id="af9af-125">**Count**</span><span class="sxs-lookup"><span data-stu-id="af9af-125">**Count**</span></span> <br/> |<span data-ttu-id="af9af-126">2 个字节</span><span class="sxs-lookup"><span data-stu-id="af9af-126">2 bytes</span></span>  <br/> |<span data-ttu-id="af9af-127">在此 BLOB 标记的资源的数目。</span><span class="sxs-lookup"><span data-stu-id="af9af-127">The number of resource tags in this BLOB.</span></span>  <br/> |
|<span data-ttu-id="af9af-128">资源标记</span><span class="sxs-lookup"><span data-stu-id="af9af-128">Resource tag</span></span>  <br/> |<span data-ttu-id="af9af-129">变量</span><span class="sxs-lookup"><span data-stu-id="af9af-129">Variable</span></span>  <br/> |<span data-ttu-id="af9af-130">编码的资源标记的 0 或更多 null 结尾 utf-8 字符串。</span><span class="sxs-lookup"><span data-stu-id="af9af-130">0 or more null-terminated UTF-8 strings that encode the resource tags.</span></span> <span data-ttu-id="af9af-131">空结尾字符串数必须匹配**计数**。</span><span class="sxs-lookup"><span data-stu-id="af9af-131">The number of null-terminated strings must match **Count**.</span></span>  <br/> |
   
<span data-ttu-id="af9af-132">每个资源标记指定应用到邮件中，有关操作，某些日期时间元数据并将编码的邮件 UID 的操作。</span><span class="sxs-lookup"><span data-stu-id="af9af-132">Each resource tag specifies the operation that is applied to a message, some date-time metadata about the operation, and encodes the UID of the message.</span></span> <span data-ttu-id="af9af-133">资源标记字符串的格式，如下所示，细分和进一步说明表 2 中。</span><span class="sxs-lookup"><span data-stu-id="af9af-133">The format of a resource tag string is broken down as follows, and is further explained in Table 2.</span></span> 
  
`Ocyyyymmddhhmmssuuu...`
  
<span data-ttu-id="af9af-134">**表 2。资源标记的结构**</span><span class="sxs-lookup"><span data-stu-id="af9af-134">**Table 2. Structure of a resource tag**</span></span>

|<span data-ttu-id="af9af-135">**资源标记中的字段**</span><span class="sxs-lookup"><span data-stu-id="af9af-135">**Field in a resource tag**</span></span>|<span data-ttu-id="af9af-136">**Size**</span><span class="sxs-lookup"><span data-stu-id="af9af-136">**Size**</span></span>|<span data-ttu-id="af9af-137">**说明**</span><span class="sxs-lookup"><span data-stu-id="af9af-137">**Description**</span></span>|
|:-----|:-----|:-----|
| `O` <br/> |<span data-ttu-id="af9af-138">1 个字符</span><span class="sxs-lookup"><span data-stu-id="af9af-138">1 character</span></span>  <br/> |<span data-ttu-id="af9af-139">在电子邮件上执行操作。</span><span class="sxs-lookup"><span data-stu-id="af9af-139">The operation performed on the email message.</span></span> <span data-ttu-id="af9af-140">值必须是"+"、"-"，或"&amp;"，分别表示成功 get、 删除或 get 删除操作。</span><span class="sxs-lookup"><span data-stu-id="af9af-140">The value must be "+", "-", or "&amp;", which indicates a successful get, delete, or get-and-delete operation, respectively.</span></span>  <br/> |
| `c` <br/> |<span data-ttu-id="af9af-141">1 个字符</span><span class="sxs-lookup"><span data-stu-id="af9af-141">1 character</span></span>  <br/> |<span data-ttu-id="af9af-142">消息内容操作中所涉及的一部分。</span><span class="sxs-lookup"><span data-stu-id="af9af-142">The part of the message content involved in the operation.</span></span> <span data-ttu-id="af9af-143">值必须是""，"h"或"b"，指示的任何内容，标头或正文，分别。</span><span class="sxs-lookup"><span data-stu-id="af9af-143">The value must be " ", "h", or "b", which indicates the content of none, header, or body, respectively.</span></span>  <br/> |
| `yyyy` <br/> |<span data-ttu-id="af9af-144">4 个字符</span><span class="sxs-lookup"><span data-stu-id="af9af-144">4 characters</span></span>  <br/> |<span data-ttu-id="af9af-145">操作四位数年份。</span><span class="sxs-lookup"><span data-stu-id="af9af-145">The four-digit year of the operation.</span></span>  <br/> |
| `MM` <br/> |<span data-ttu-id="af9af-146">2 个字符</span><span class="sxs-lookup"><span data-stu-id="af9af-146">2 characters</span></span>  <br/> |<span data-ttu-id="af9af-147">操作的两位数表示的月份。</span><span class="sxs-lookup"><span data-stu-id="af9af-147">The two-digit month of the operation.</span></span>  <br/> |
| `dd` <br/> |<span data-ttu-id="af9af-148">2 个字符</span><span class="sxs-lookup"><span data-stu-id="af9af-148">2 characters</span></span>  <br/> |<span data-ttu-id="af9af-149">操作的两位数的天数。</span><span class="sxs-lookup"><span data-stu-id="af9af-149">The two-digit day of the operation.</span></span>  <br/> |
| `hh` <br/> |<span data-ttu-id="af9af-150">2 个字符</span><span class="sxs-lookup"><span data-stu-id="af9af-150">2 characters</span></span>  <br/> |<span data-ttu-id="af9af-151">操作的两位数小时数。</span><span class="sxs-lookup"><span data-stu-id="af9af-151">The two-digit hour of the operation.</span></span>  <br/> |
| `mm` <br/> |<span data-ttu-id="af9af-152">2 个字符</span><span class="sxs-lookup"><span data-stu-id="af9af-152">2 characters</span></span>  <br/> |<span data-ttu-id="af9af-153">操作的两位数分钟。</span><span class="sxs-lookup"><span data-stu-id="af9af-153">The two-digit minute of the operation.</span></span>  <br/> |
| `ss` <br/> |<span data-ttu-id="af9af-154">2 个字符</span><span class="sxs-lookup"><span data-stu-id="af9af-154">2 characters</span></span>  <br/> |<span data-ttu-id="af9af-155">操作的两位数秒钟。</span><span class="sxs-lookup"><span data-stu-id="af9af-155">The two-digit second of the operation.</span></span>  <br/> |
| `uuu…` <br/> |<span data-ttu-id="af9af-156">可变长度</span><span class="sxs-lookup"><span data-stu-id="af9af-156">Variable length</span></span>  <br/> |<span data-ttu-id="af9af-157">邮件编码的 UID。</span><span class="sxs-lookup"><span data-stu-id="af9af-157">The encoded UID of a message.</span></span>  <br/> |

<span data-ttu-id="af9af-158"><a name="OL15Con_AuxRef_ParsingMsgsHistory_Example"> </a></span><span class="sxs-lookup"><span data-stu-id="af9af-158"></span></span>

## <a name="example"></a><span data-ttu-id="af9af-159">示例</span><span class="sxs-lookup"><span data-stu-id="af9af-159">Example</span></span>

<span data-ttu-id="af9af-160">图 1 显示值，该值代表 POP 帐户的消息下载历史记录的 BLOB 的示例。</span><span class="sxs-lookup"><span data-stu-id="af9af-160">Figure 1 shows an example of a BLOB that represents the message download history of a POP account.</span></span> 
  
<span data-ttu-id="af9af-161">**图 1。将 BLOB 结构示例邮件下载历史记录的 POP3 帐户**</span><span class="sxs-lookup"><span data-stu-id="af9af-161">**Figure 1. Example BLOB structure for the message download history of a POP3 account**</span></span>

![用于 POP3 帐户的消息下载历史记录的 BLOB](media/OL15Con_AuxRef_ParsingMsgsHistory_Blob.gif)
  
<span data-ttu-id="af9af-163">基于表 1 和表 2 中所述的结构，此 BLOB 表示 23 电子邮件下载历史的记录。</span><span class="sxs-lookup"><span data-stu-id="af9af-163">Based on the structure described in Table 1 and Table 2, this BLOB represents the download history of 23 email messages.</span></span>
  
<span data-ttu-id="af9af-164">若要分析的原始 UID 每个资源标记中，注意 UID 遵循此编码： UID 中的字符都是主要字母数字字符，并且每个非字母数字字符前面加 ASCII 字符"$"(0x24)。</span><span class="sxs-lookup"><span data-stu-id="af9af-164">To parse the raw UID in each resource tag, be aware that the UID follows this encoding: characters in a UID are mostly alphanumeric characters, and each non-alphanumeric character is preceded by the ASCII character "$" (0x24).</span></span> <span data-ttu-id="af9af-165">以便 ASCII 字符 $2d 表示非字母数字字符"-"。</span><span class="sxs-lookup"><span data-stu-id="af9af-165">So the ASCII characters $2d represent the non-alphanumeric character "-".</span></span> <span data-ttu-id="af9af-166">图 2 显示了示例首先将资源标记 1 中的原始 UID 转换为 ASCII 表示形式，然后将"$"若要生成的实际 UID 前面有任何非字母数字字符转换：</span><span class="sxs-lookup"><span data-stu-id="af9af-166">Figure 2 shows an example of first converting the raw UID in resource tag 1 to the ASCII representation, then converting any non-alphanumeric character preceded by "$" to produce the actual UID:</span></span>
  
`0BC535DB-EA63-11E1-A75C-00215AD7BB74`
  
<span data-ttu-id="af9af-167">**图 2。将资源标记中的原始 UID 转换为实际邮件 UID**</span><span class="sxs-lookup"><span data-stu-id="af9af-167">**Figure 2. Converting the raw UID in a resource tag to the actual message UID**</span></span>

![将 BLOB 中的原始 UID 转换为实际消息 UID](media/OL15Con_AuxRef_ParsingMsgsHistory_BlobRscTag.gif)
  
<span data-ttu-id="af9af-169">解释此 BLOB 中的资源标记 1： 具有 UID 消息`0BC535DB-EA63-11E1-A75C-00215AD7BB74`已成功检索在 2012 年 9 月 6 日，在 13:11:38。</span><span class="sxs-lookup"><span data-stu-id="af9af-169">To interpret resource tag 1 in this BLOB: the message with the UID  `0BC535DB-EA63-11E1-A75C-00215AD7BB74` was successfully retrieved on September 6, 2012, at 13:11:38.</span></span> 
  
<span data-ttu-id="af9af-170">同样，您可以为该 BLOB 分析的其余 22 资源标记。</span><span class="sxs-lookup"><span data-stu-id="af9af-170">You can similarly parse the remaining 22 resource tags for that BLOB.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="af9af-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="af9af-171">See also</span></span>
<span data-ttu-id="af9af-172"><a name="OL15Con_AuxRef_ParsingMsgsHistory_AdditionalRsc"> </a></span><span class="sxs-lookup"><span data-stu-id="af9af-172"></span></span>

- [<span data-ttu-id="af9af-173">管理 POP3 帐户的邮件下载</span><span class="sxs-lookup"><span data-stu-id="af9af-173">Managing message downloads for POP3 accounts</span></span>](managing-message-downloads-for-pop3-accounts.md)    
- [<span data-ttu-id="af9af-174">查找一个 POP3 帐户的消息下载历史记录</span><span class="sxs-lookup"><span data-stu-id="af9af-174">Locating the message download history for a POP3 account</span></span>](locating-the-message-download-history-for-a-pop3-account.md)    
- [<span data-ttu-id="af9af-175">分析 POP3 UIDL 历史记录</span><span class="sxs-lookup"><span data-stu-id="af9af-175">Parsing the POP3 UIDL History</span></span>](https://blogs.msdn.com/b/stephen_griffin/archive/2012/12/04/parsing-the-pop3-uidl-history.aspx)
    

