---
title: 分析 POP3 帐户的邮件下载历史记录
manager: soliver
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 394e1430-04d6-4d61-be13-eb695309fa73
description: 本主题介绍 pop3 BLOB 的结构, 该 BLOB 表示 pop3 帐户的邮件下载历史记录, 用于标识已在该帐户上下载或删除的邮件。
ms.openlocfilehash: 44a799f6b6fbe2a2841522c18405149a470b0236
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32327757"
---
# <a name="parsing-the-message-download-history-for-a-pop3-account"></a><span data-ttu-id="6024f-103">分析 POP3 帐户的邮件下载历史记录</span><span class="sxs-lookup"><span data-stu-id="6024f-103">Parsing the message download history for a POP3 account</span></span>

<span data-ttu-id="6024f-104">本主题介绍 pop3 BLOB 的结构, 该 BLOB 表示 pop3 帐户的邮件下载历史记录, 用于标识已在该帐户上下载或删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="6024f-104">This topic describes the structure of the POP3 BLOB that represents the message download history of a POP3 account, to identify the messages that have been downloaded or deleted on that account.</span></span>

<span data-ttu-id="6024f-105"><a name="OL15Con_AuxRef_ParsingMsgsHistory_WhyParseHistory"> </a></span><span class="sxs-lookup"><span data-stu-id="6024f-105"></span></span>

## <a name="why-parse-the-message-download-history"></a><span data-ttu-id="6024f-106">为什么分析邮件下载历史记录？</span><span class="sxs-lookup"><span data-stu-id="6024f-106">Why parse the message download history?</span></span>

<span data-ttu-id="6024f-107">Outlook 的邮局协议 (POP) 提供程序允许用户在其本地设备上检索和下载新的电子邮件, 并随后在邮件服务器上保留或删除这些电子邮件。</span><span class="sxs-lookup"><span data-stu-id="6024f-107">The Post Office Protocol (POP) provider for Outlook allows users to retrieve and download new email messages on their local device, and subsequently to leave or delete these email messages on the mail server.</span></span> <span data-ttu-id="6024f-108">当邮件客户端检查要下载的新邮件时, 它必须能够识别和下载该收件箱的新邮件。</span><span class="sxs-lookup"><span data-stu-id="6024f-108">When the mail client checks for new messages to download, it has to be able to identify and download only the new messages for that Inbox.</span></span> <span data-ttu-id="6024f-109">邮件客户端通过首先使用 UIDL (唯一 ID 列表) 命令来获取已传递到该收件箱的每封邮件的映射, 以获取唯一标识符 (UID) 的映射。</span><span class="sxs-lookup"><span data-stu-id="6024f-109">The mail client does this by first using the UIDL (Unique ID Listing) command to obtain a map of each message that has ever been delivered to that Inbox to a unique identifier (UID).</span></span> <span data-ttu-id="6024f-110">客户端还会获取邮件下载历史记录, 以了解已为该客户端上的 "收件箱" 下载或删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="6024f-110">The client also gets the message download history for messages that have been downloaded or deleted for the Inbox on that client.</span></span> <span data-ttu-id="6024f-111">通过使用邮件 UID 映射和下载历史记录, 客户端可以将历史记录中缺少的那些邮件标识为新的, 因此应下载这些邮件。</span><span class="sxs-lookup"><span data-stu-id="6024f-111">Using the message UID map and download history, the client can then identify those messages that are absent from the history as new and, hence, should be downloaded.</span></span>
  
<span data-ttu-id="6024f-112">要获取收件箱的邮件下载历史记录, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="6024f-112">To get the messages download history for an Inbox:</span></span>
  
- <span data-ttu-id="6024f-113">按照[查找 pop3 帐户的邮件下载历史记录](locating-the-message-download-history-for-a-pop3-account.md)中的步骤查找[PidTagAttachDataBinary](https://msdn.microsoft.com/library/3b0a8b28-863e-4b96-a4c0-fdb8f40555b9%28Office.15%29.aspx)属性, 该属性包含一个二进制大型对象 (BLOB), 该对象代表 POP3 帐户的邮件历史记录。</span><span class="sxs-lookup"><span data-stu-id="6024f-113">Follow the steps in [Locating the message download history for a POP3 account](locating-the-message-download-history-for-a-pop3-account.md) to find the [PidTagAttachDataBinary](https://msdn.microsoft.com/library/3b0a8b28-863e-4b96-a4c0-fdb8f40555b9%28Office.15%29.aspx) property, which contains a binary large object (BLOB) that represents the message history for a POP3 account.</span></span> 
    
- <span data-ttu-id="6024f-114">阅读本主题, 其中介绍了 BLOB 的结构, 并显示了一个示例 BLOB, 用于标识已为 POP3 帐户的收件箱下载或删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="6024f-114">Read this topic, which describes the structure of the BLOB, and shows an example BLOB to identify messages that have been downloaded or deleted for the Inbox of the POP3 account.</span></span>

<span data-ttu-id="6024f-115"><a name="OL15Con_AuxRef_ParsingMsgsHistory_BLOBStructure"> </a></span><span class="sxs-lookup"><span data-stu-id="6024f-115"></span></span>

## <a name="pop-blob-structure"></a><span data-ttu-id="6024f-116">POP BLOB 结构</span><span class="sxs-lookup"><span data-stu-id="6024f-116">POP BLOB structure</span></span>

<span data-ttu-id="6024f-117">POP BLOB 结构 (如表1中所述) 以两个字段 " **Version** " 和 "**计数**" 开头, 后跟 "资源标记数", 其中每个字段的**计数**都是以 null 结尾的。</span><span class="sxs-lookup"><span data-stu-id="6024f-117">The POP BLOB structure, as described in Table 1, begins with two fields, **Version** and **Count**, followed by a **Count** number of resource tags, each of which is null-terminated.</span></span> 
  
<span data-ttu-id="6024f-118">**表1。表示 POP3 帐户的邮件下载历史记录的 BLOB 的结构**</span><span class="sxs-lookup"><span data-stu-id="6024f-118">**Table 1. Structure of the BLOB that represents the message download history of a POP3 account**</span></span>

|<span data-ttu-id="6024f-119">**BLOB 中的字段**</span><span class="sxs-lookup"><span data-stu-id="6024f-119">**Field in BLOB**</span></span>|<span data-ttu-id="6024f-120">**Size**</span><span class="sxs-lookup"><span data-stu-id="6024f-120">**Size**</span></span>|<span data-ttu-id="6024f-121">**说明**</span><span class="sxs-lookup"><span data-stu-id="6024f-121">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6024f-122">**版本**</span><span class="sxs-lookup"><span data-stu-id="6024f-122">**Version**</span></span> <br/> |<span data-ttu-id="6024f-123">2 个字节</span><span class="sxs-lookup"><span data-stu-id="6024f-123">2 bytes</span></span>  <br/> |<span data-ttu-id="6024f-124">必须为 3 (**PBLOB_VERSION_NUM**)。</span><span class="sxs-lookup"><span data-stu-id="6024f-124">Must be 3 (**PBLOB_VERSION_NUM**).</span></span>  <br/> |
|<span data-ttu-id="6024f-125">**Count**</span><span class="sxs-lookup"><span data-stu-id="6024f-125">**Count**</span></span> <br/> |<span data-ttu-id="6024f-126">2 个字节</span><span class="sxs-lookup"><span data-stu-id="6024f-126">2 bytes</span></span>  <br/> |<span data-ttu-id="6024f-127">此 BLOB 中的资源标记数。</span><span class="sxs-lookup"><span data-stu-id="6024f-127">The number of resource tags in this BLOB.</span></span>  <br/> |
|<span data-ttu-id="6024f-128">资源标记</span><span class="sxs-lookup"><span data-stu-id="6024f-128">Resource tag</span></span>  <br/> |<span data-ttu-id="6024f-129">变量</span><span class="sxs-lookup"><span data-stu-id="6024f-129">Variable</span></span>  <br/> |<span data-ttu-id="6024f-130">0个或更多以 null 结尾的 utf-8 字符串, 用于对资源标记进行编码。</span><span class="sxs-lookup"><span data-stu-id="6024f-130">0 or more null-terminated UTF-8 strings that encode the resource tags.</span></span> <span data-ttu-id="6024f-131">以 null 结尾的字符串的数目必须与**Count**相匹配。</span><span class="sxs-lookup"><span data-stu-id="6024f-131">The number of null-terminated strings must match **Count**.</span></span>  <br/> |
   
<span data-ttu-id="6024f-132">每个资源标记指定应用于邮件的操作、有关操作的一些日期时间元数据, 以及对邮件的 UID 进行编码。</span><span class="sxs-lookup"><span data-stu-id="6024f-132">Each resource tag specifies the operation that is applied to a message, some date-time metadata about the operation, and encodes the UID of the message.</span></span> <span data-ttu-id="6024f-133">资源标记字符串的格式按如下方式分解, 并在表2中进一步说明。</span><span class="sxs-lookup"><span data-stu-id="6024f-133">The format of a resource tag string is broken down as follows, and is further explained in Table 2.</span></span> 
  
`Ocyyyymmddhhmmssuuu...`
  
<span data-ttu-id="6024f-134">**表2。资源标记的结构**</span><span class="sxs-lookup"><span data-stu-id="6024f-134">**Table 2. Structure of a resource tag**</span></span>

|<span data-ttu-id="6024f-135">**资源标记中的字段**</span><span class="sxs-lookup"><span data-stu-id="6024f-135">**Field in a resource tag**</span></span>|<span data-ttu-id="6024f-136">**Size**</span><span class="sxs-lookup"><span data-stu-id="6024f-136">**Size**</span></span>|<span data-ttu-id="6024f-137">**Description**</span><span class="sxs-lookup"><span data-stu-id="6024f-137">**Description**</span></span>|
|:-----|:-----|:-----|
| `O` <br/> |<span data-ttu-id="6024f-138">1个字符</span><span class="sxs-lookup"><span data-stu-id="6024f-138">1 character</span></span>  <br/> |<span data-ttu-id="6024f-139">对电子邮件执行的操作。</span><span class="sxs-lookup"><span data-stu-id="6024f-139">The operation performed on the email message.</span></span> <span data-ttu-id="6024f-140">该值必须是 "+"、"-" 或 "&amp;", 分别表示成功的获取、删除或获取和删除操作。</span><span class="sxs-lookup"><span data-stu-id="6024f-140">The value must be "+", "-", or "&amp;", which indicates a successful get, delete, or get-and-delete operation, respectively.</span></span>  <br/> |
| `c` <br/> |<span data-ttu-id="6024f-141">1个字符</span><span class="sxs-lookup"><span data-stu-id="6024f-141">1 character</span></span>  <br/> |<span data-ttu-id="6024f-142">操作中涉及的邮件内容部分。</span><span class="sxs-lookup"><span data-stu-id="6024f-142">The part of the message content involved in the operation.</span></span> <span data-ttu-id="6024f-143">该值必须是 ""、"h" 或 "b", 分别表示无、头或正文的内容。</span><span class="sxs-lookup"><span data-stu-id="6024f-143">The value must be " ", "h", or "b", which indicates the content of none, header, or body, respectively.</span></span>  <br/> |
| `yyyy` <br/> |<span data-ttu-id="6024f-144">4个字符</span><span class="sxs-lookup"><span data-stu-id="6024f-144">4 characters</span></span>  <br/> |<span data-ttu-id="6024f-145">此运算的四位数年份。</span><span class="sxs-lookup"><span data-stu-id="6024f-145">The four-digit year of the operation.</span></span>  <br/> |
| `MM` <br/> |<span data-ttu-id="6024f-146">2个字符</span><span class="sxs-lookup"><span data-stu-id="6024f-146">2 characters</span></span>  <br/> |<span data-ttu-id="6024f-147">运算的两位数月份。</span><span class="sxs-lookup"><span data-stu-id="6024f-147">The two-digit month of the operation.</span></span>  <br/> |
| `dd` <br/> |<span data-ttu-id="6024f-148">2个字符</span><span class="sxs-lookup"><span data-stu-id="6024f-148">2 characters</span></span>  <br/> |<span data-ttu-id="6024f-149">操作的两位数日期。</span><span class="sxs-lookup"><span data-stu-id="6024f-149">The two-digit day of the operation.</span></span>  <br/> |
| `hh` <br/> |<span data-ttu-id="6024f-150">2个字符</span><span class="sxs-lookup"><span data-stu-id="6024f-150">2 characters</span></span>  <br/> |<span data-ttu-id="6024f-151">运算的两位数的小时数。</span><span class="sxs-lookup"><span data-stu-id="6024f-151">The two-digit hour of the operation.</span></span>  <br/> |
| `mm` <br/> |<span data-ttu-id="6024f-152">2个字符</span><span class="sxs-lookup"><span data-stu-id="6024f-152">2 characters</span></span>  <br/> |<span data-ttu-id="6024f-153">运算的两位数分钟数。</span><span class="sxs-lookup"><span data-stu-id="6024f-153">The two-digit minute of the operation.</span></span>  <br/> |
| `ss` <br/> |<span data-ttu-id="6024f-154">2个字符</span><span class="sxs-lookup"><span data-stu-id="6024f-154">2 characters</span></span>  <br/> |<span data-ttu-id="6024f-155">运算的两位数秒数。</span><span class="sxs-lookup"><span data-stu-id="6024f-155">The two-digit second of the operation.</span></span>  <br/> |
| `uuu…` <br/> |<span data-ttu-id="6024f-156">可变长度</span><span class="sxs-lookup"><span data-stu-id="6024f-156">Variable length</span></span>  <br/> |<span data-ttu-id="6024f-157">邮件的编码 UID。</span><span class="sxs-lookup"><span data-stu-id="6024f-157">The encoded UID of a message.</span></span>  <br/> |

<span data-ttu-id="6024f-158"><a name="OL15Con_AuxRef_ParsingMsgsHistory_Example"> </a></span><span class="sxs-lookup"><span data-stu-id="6024f-158"></span></span>

## <a name="example"></a><span data-ttu-id="6024f-159">示例</span><span class="sxs-lookup"><span data-stu-id="6024f-159">Example</span></span>

<span data-ttu-id="6024f-160">图1显示了一个 BLOB, 该示例表示 POP 帐户的邮件下载历史记录。</span><span class="sxs-lookup"><span data-stu-id="6024f-160">Figure 1 shows an example of a BLOB that represents the message download history of a POP account.</span></span> 
  
<span data-ttu-id="6024f-161">**图1。POP3 帐户的邮件下载历史记录的示例 BLOB 结构**</span><span class="sxs-lookup"><span data-stu-id="6024f-161">**Figure 1. Example BLOB structure for the message download history of a POP3 account**</span></span>

![用于 POP3 帐户的消息下载历史记录的 BLOB](media/OL15Con_AuxRef_ParsingMsgsHistory_Blob.gif)
  
<span data-ttu-id="6024f-163">根据表1和表2中所述的结构, 此 BLOB 表示23封电子邮件的下载历史记录。</span><span class="sxs-lookup"><span data-stu-id="6024f-163">Based on the structure described in Table 1 and Table 2, this BLOB represents the download history of 23 email messages.</span></span>
  
<span data-ttu-id="6024f-164">若要分析每个资源标记中的原始 UID, 请注意, uid 遵循以下编码: uid 中的字符主要是字母数字字符, 并且每个非字母数字字符前面都有 ASCII 字符 "$" (0x24)。</span><span class="sxs-lookup"><span data-stu-id="6024f-164">To parse the raw UID in each resource tag, be aware that the UID follows this encoding: characters in a UID are mostly alphanumeric characters, and each non-alphanumeric character is preceded by the ASCII character "$" (0x24).</span></span> <span data-ttu-id="6024f-165">因此, ASCII 字符 $ 2d 代表非字母数字字符 "-"。</span><span class="sxs-lookup"><span data-stu-id="6024f-165">So the ASCII characters $2d represent the non-alphanumeric character "-".</span></span> <span data-ttu-id="6024f-166">图2显示了首先将资源标记1中的原始 UID 转换为 ASCII 表示形式的示例, 然后转换以 "$" 开头的任何非字母数字字符, 以生成实际的 UID:</span><span class="sxs-lookup"><span data-stu-id="6024f-166">Figure 2 shows an example of first converting the raw UID in resource tag 1 to the ASCII representation, then converting any non-alphanumeric character preceded by "$" to produce the actual UID:</span></span>
  
`0BC535DB-EA63-11E1-A75C-00215AD7BB74`
  
<span data-ttu-id="6024f-167">**图2。将资源标记中的原始 UID 转换为实际的邮件 UID**</span><span class="sxs-lookup"><span data-stu-id="6024f-167">**Figure 2. Converting the raw UID in a resource tag to the actual message UID**</span></span>

![将 BLOB 中的原始 UID 转换为实际消息 UID](media/OL15Con_AuxRef_ParsingMsgsHistory_BlobRscTag.gif)
  
<span data-ttu-id="6024f-169">若要解释此 BLOB 中的资源标记 1, 请参阅 13:11:38 `0BC535DB-EA63-11E1-A75C-00215AD7BB74`在2012年9月6日成功检索 UID 为的邮件。</span><span class="sxs-lookup"><span data-stu-id="6024f-169">To interpret resource tag 1 in this BLOB: the message with the UID  `0BC535DB-EA63-11E1-A75C-00215AD7BB74` was successfully retrieved on September 6, 2012, at 13:11:38.</span></span> 
  
<span data-ttu-id="6024f-170">您可以同样分析该 BLOB 的其余22个资源标记。</span><span class="sxs-lookup"><span data-stu-id="6024f-170">You can similarly parse the remaining 22 resource tags for that BLOB.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6024f-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6024f-171">See also</span></span>
<span data-ttu-id="6024f-172"><a name="OL15Con_AuxRef_ParsingMsgsHistory_AdditionalRsc"> </a></span><span class="sxs-lookup"><span data-stu-id="6024f-172"></span></span>

- [<span data-ttu-id="6024f-173">管理 POP3 帐户的邮件下载</span><span class="sxs-lookup"><span data-stu-id="6024f-173">Managing message downloads for POP3 accounts</span></span>](managing-message-downloads-for-pop3-accounts.md)    
- [<span data-ttu-id="6024f-174">查找一个 POP3 帐户的消息下载历史记录</span><span class="sxs-lookup"><span data-stu-id="6024f-174">Locating the message download history for a POP3 account</span></span>](locating-the-message-download-history-for-a-pop3-account.md)    
- [<span data-ttu-id="6024f-175">分析 POP3 UIDL 历史记录</span><span class="sxs-lookup"><span data-stu-id="6024f-175">Parsing the POP3 UIDL History</span></span>](https://blogs.msdn.com/b/stephen_griffin/archive/2012/12/04/parsing-the-pop3-uidl-history.aspx)
    

