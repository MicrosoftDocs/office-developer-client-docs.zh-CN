---
title: 关于用于索引Notification-Based MAPI URL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 9cb35f0a-267e-2d85-1701-02d52578a0b8
description: 上次修改时间：2011 年 11 月 8 日
ms.openlocfilehash: 5a3e45809f36b71968560a4b239e268addf00474
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422479"
---
# <a name="about-mapi-urls-for-notification-based-indexing"></a><span data-ttu-id="eba8b-103">关于用于索引Notification-Based MAPI URL</span><span class="sxs-lookup"><span data-stu-id="eba8b-103">About MAPI URLs for Notification-Based Indexing</span></span>

<span data-ttu-id="eba8b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="eba8b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="eba8b-105">当存储提供程序通知索引器某个对象已准备好编制索引时，它将生成一个 MAPI URL，用于唯一标识 MAPI 协议处理程序的对象。</span><span class="sxs-lookup"><span data-stu-id="eba8b-105">When a store provider notifies an indexer that an object is ready for indexing, it generates a MAPI URL that uniquely identifies the object to the MAPI Protocol Handler.</span></span> <span data-ttu-id="eba8b-106">MAPI URL 采用 Unicode 编码，并具有以下格式：</span><span class="sxs-lookup"><span data-stu-id="eba8b-106">MAPI URLs are encoded in Unicode, and have the following format:</span></span> 
  
`Mapi://SID/StoreDisplayName ($HashNumber)/StoreType/FolderNameA/…/FolderNameN/[EntryIDEncoded[/at=AttachIDEncoded:FileName]]`

<span data-ttu-id="eba8b-107">下表介绍了典型 URL 的各个部分。</span><span class="sxs-lookup"><span data-stu-id="eba8b-107">The following table describes the various parts of a typical URL.</span></span>

|<span data-ttu-id="eba8b-108">Part</span><span class="sxs-lookup"><span data-stu-id="eba8b-108">Part</span></span> | <span data-ttu-id="eba8b-109">说明</span><span class="sxs-lookup"><span data-stu-id="eba8b-109">Description</span></span>|
|:----|:-----------|  
|<span data-ttu-id="eba8b-110">*SID*</span><span class="sxs-lookup"><span data-stu-id="eba8b-110">*SID*</span></span> |<span data-ttu-id="eba8b-111">当前用户的安全标识符。</span><span class="sxs-lookup"><span data-stu-id="eba8b-111">The current user's security identifier.</span></span>| 
|<span data-ttu-id="eba8b-112">*StoreDisplayName*</span><span class="sxs-lookup"><span data-stu-id="eba8b-112">*StoreDisplayName*</span></span> |<span data-ttu-id="eba8b-113">一个字符串，显示名称该存储区上的用户名称。</span><span class="sxs-lookup"><span data-stu-id="eba8b-113">A string that specifies the display name of the user on that store.</span></span>|
|<span data-ttu-id="eba8b-114">*HashNumber*</span><span class="sxs-lookup"><span data-stu-id="eba8b-114">*HashNumber*</span></span> |<span data-ttu-id="eba8b-115">以十六进制表示形式表示的 **DWORD，** 它基于存储条目 ID 或存储映射签名计算。</span><span class="sxs-lookup"><span data-stu-id="eba8b-115">A **DWORD** in hexadecimal representation that is calculated based on the store entry ID or the store mapping signature.</span></span> <span data-ttu-id="eba8b-116">此值存储在注册表中，稍后将用于标识 MAPI 协议处理程序中的存储。</span><span class="sxs-lookup"><span data-stu-id="eba8b-116">This value is stored in the registry and will be used later to identify the store in the MAPI Protocol Handler.</span></span><br/><br/><span data-ttu-id="eba8b-117">此数字必须以最大程度减少与其他存储冲突的方式计算。</span><span class="sxs-lookup"><span data-stu-id="eba8b-117">This number must be calculated in a way that minimizes collisions with other stores.</span></span> <span data-ttu-id="eba8b-118">有关 Microsoft Outlook计算哈希数的算法，请参阅 Algorithm to [Calculate the Store Hash Number](algorithm-to-calculate-the-store-hash-number.md)。</span><span class="sxs-lookup"><span data-stu-id="eba8b-118">For the algorithm that Microsoft Outlook uses to calculate the hash number, see [Algorithm to Calculate the Store Hash Number](algorithm-to-calculate-the-store-hash-number.md).</span></span>|
|<span data-ttu-id="eba8b-119">*StoreType*</span><span class="sxs-lookup"><span data-stu-id="eba8b-119">*StoreType*</span></span> |<span data-ttu-id="eba8b-120">一个数字，标识包含要编制索引的对象的存储区的类型。</span><span class="sxs-lookup"><span data-stu-id="eba8b-120">A number that identifies the type of the store that contains the object to be indexed.</span></span> <span data-ttu-id="eba8b-121">可能值包括：</span><span class="sxs-lookup"><span data-stu-id="eba8b-121">The possible values are as follows:</span></span><br/><span data-ttu-id="eba8b-122">- 0 - 默认存储。</span><span class="sxs-lookup"><span data-stu-id="eba8b-122">- 0 - Default store.</span></span><br/><br/><span data-ttu-id="eba8b-123">- 1 - 委托存储，用于本地缓存的委托项。</span><span class="sxs-lookup"><span data-stu-id="eba8b-123">- 1 - Delegate store, used for delegate items cached locally.</span></span><br/><br/><span data-ttu-id="eba8b-124">- 2 - 公用文件夹，用于公用文件夹收藏夹。</span><span class="sxs-lookup"><span data-stu-id="eba8b-124">- 2 - Public folders, used for public folder favorites.</span></span><br/><br/><span data-ttu-id="eba8b-125">**注意**：如果正在对存储进行爬网而不是推送，则使用的值是字符 *X*。</span><span class="sxs-lookup"><span data-stu-id="eba8b-125">**NOTE**: If the store is being crawled instead of pushed, the value that is used is the character *X*.</span></span>| 
|<span data-ttu-id="eba8b-126">*FolderNameA/.../FolderNameN*</span><span class="sxs-lookup"><span data-stu-id="eba8b-126">*FolderNameA/…/FolderNameN*</span></span> |<span data-ttu-id="eba8b-127">从文件夹或邮件IPM_SUBTREE根目录的路径。</span><span class="sxs-lookup"><span data-stu-id="eba8b-127">The path from the root of the IPM_SUBTREE to the folder or message.</span></span> <span data-ttu-id="eba8b-128">例如，"收件箱"下的 **"** 系列"文件夹中 **的邮件** 具有 **此参数的"收件箱/** 系列"。</span><span class="sxs-lookup"><span data-stu-id="eba8b-128">For example, a message in the **Family** folder under **Inbox** has **Inbox/Family** for this parameter.</span></span> |
|<span data-ttu-id="eba8b-129">*EntryIDEncoded*</span><span class="sxs-lookup"><span data-stu-id="eba8b-129">*EntryIDEncoded*</span></span> |<span data-ttu-id="eba8b-130">编码为 Unicode 字符串的项的 MAPI 条目 ID。</span><span class="sxs-lookup"><span data-stu-id="eba8b-130">MAPI entry ID for the item encoded as a Unicode string.</span></span> <span data-ttu-id="eba8b-131">请参阅以下"特殊字符"部分，了解如何对特定特殊字符进行编码。</span><span class="sxs-lookup"><span data-stu-id="eba8b-131">See the following section "Special Characters" for information about how certain special characters are encoded.</span></span> <span data-ttu-id="eba8b-132">有关对条目 ID 进行编码的算法详细信息，请参阅对条目 ID 和附件 ID 进行编码 [的算法](algorithm-to-encode-entry-ids-and-attachment-ids.md)。</span><span class="sxs-lookup"><span data-stu-id="eba8b-132">For more information about the algorithm to encode the entry ID, see [Algorithm to Encode Entry IDs and Attachment IDs](algorithm-to-encode-entry-ids-and-attachment-ids.md).</span></span><br/><br/><span data-ttu-id="eba8b-133">**注意**：当以文本方式查看时，此编码条目 ID 显示为随机的 Hangul 字符或方框，以与算法一致性，具体取决于可用字体。</span><span class="sxs-lookup"><span data-stu-id="eba8b-133">**NOTE**: When viewed as text, this encoded entry ID appears as random Hangul characters or boxes in compliance with the algorithm, depending on available fonts.</span></span>  |
|<span data-ttu-id="eba8b-134">*AttachIDEncoded*</span><span class="sxs-lookup"><span data-stu-id="eba8b-134">*AttachIDEncoded*</span></span> |<span data-ttu-id="eba8b-135">编码为 Unicode 字符串的附件 ID。</span><span class="sxs-lookup"><span data-stu-id="eba8b-135">Attachment ID encoded as a Unicode string.</span></span> <span data-ttu-id="eba8b-136">请参阅以下"特殊字符"部分，了解如何对特定特殊字符进行编码。</span><span class="sxs-lookup"><span data-stu-id="eba8b-136">See the following section "Special Characters" for information about how certain special characters are encoded.</span></span> <span data-ttu-id="eba8b-137">有关对条目 ID 进行编码的算法详细信息，请参阅对条目 ID 和附件 ID 进行编码 [的算法](algorithm-to-encode-entry-ids-and-attachment-ids.md)。</span><span class="sxs-lookup"><span data-stu-id="eba8b-137">For more information about the algorithm to encode the entry ID, see [Algorithm to Encode Entry IDs and Attachment IDs](algorithm-to-encode-entry-ids-and-attachment-ids.md).</span></span><br/><br/><span data-ttu-id="eba8b-138">**注意**：当以文本方式查看时，此编码条目 ID 显示为随机的 Hangul 字符或方框，以与算法一致性，具体取决于可用字体。</span><span class="sxs-lookup"><span data-stu-id="eba8b-138">**NOTE**: When viewed as text, this encoded entry ID appears as random Hangul characters or boxes in compliance with the algorithm, depending on available fonts.</span></span> |
|<span data-ttu-id="eba8b-139">*FileName*</span><span class="sxs-lookup"><span data-stu-id="eba8b-139">*FileName*</span></span> |<span data-ttu-id="eba8b-140">附件文件的名称，如邮件中显示。</span><span class="sxs-lookup"><span data-stu-id="eba8b-140">Name of the attachment file, as it appears in the message.</span></span>|
    
## <a name="examples-of-mapi-urls"></a><span data-ttu-id="eba8b-141">MAPI URL 示例</span><span class="sxs-lookup"><span data-stu-id="eba8b-141">Examples of MAPI URLs</span></span>

<span data-ttu-id="eba8b-142">下面是 MAPI URL 的一些示例。</span><span class="sxs-lookup"><span data-stu-id="eba8b-142">The following are some examples of MAPI URLs.</span></span>
  
- <span data-ttu-id="eba8b-143">文件夹的 MAPI URL：</span><span class="sxs-lookup"><span data-stu-id="eba8b-143">MAPI URL for a folder:</span></span> 
    
  `mapi://S-1-5-21-2127521184-1604012920-1887927527-71418/Mailbox - Some User ($be19928f)/2/Office`
    
- <span data-ttu-id="eba8b-144">邮件的 MAPI URL：</span><span class="sxs-lookup"><span data-stu-id="eba8b-144">MAPI URL for a message:</span></span> 
    
  `mapi://S-1-5-21-2127521184-1604012920-1887927527-71418/Mailbox - Some User ($484efb89)/0/Calendar/곯가가가걍걝걌곌겷걢곒갑겛개가검걟곔걙곾걤곂갠가`
    
- <span data-ttu-id="eba8b-145">附件的 MAPI URL：</span><span class="sxs-lookup"><span data-stu-id="eba8b-145">MAPI URL for an attachment:</span></span> 
    
  `mapi://S-1-5-21-2127521184-1604012920-1887927527-71418/Mailbox - Some User ($484efb89)/0/Inbox/곯가가가걍걝걌곌겷걢곒갑겛개가검걟곔걙곾간곷갦가/at=겅걋각가:somefile.txt`
    
## <a name="special-characters"></a><span data-ttu-id="eba8b-146">特殊字符</span><span class="sxs-lookup"><span data-stu-id="eba8b-146">Special characters</span></span>

<span data-ttu-id="eba8b-147">如果某些字符出现在邮件或附件中，则进行编码。</span><span class="sxs-lookup"><span data-stu-id="eba8b-147">Certain characters are encoded if they appear in the message or attachment.</span></span> <span data-ttu-id="eba8b-148">下面显示了在 MAPI URL 中对哪些字符进行编码：</span><span class="sxs-lookup"><span data-stu-id="eba8b-148">The following shows which characters are encoded in a MAPI URL:</span></span>
  
- <span data-ttu-id="eba8b-149">% > %25</span><span class="sxs-lookup"><span data-stu-id="eba8b-149">% > %25</span></span>
    
- <span data-ttu-id="eba8b-150">/ > %2F</span><span class="sxs-lookup"><span data-stu-id="eba8b-150">/ > %2F</span></span> 
    
- <span data-ttu-id="eba8b-151">\ > %5C</span><span class="sxs-lookup"><span data-stu-id="eba8b-151">\ > %5C</span></span> 
    
- <span data-ttu-id="eba8b-152">\* > %2A</span><span class="sxs-lookup"><span data-stu-id="eba8b-152">\* > %2A</span></span> 
    
- <span data-ttu-id="eba8b-153">?</span><span class="sxs-lookup"><span data-stu-id="eba8b-153">?</span></span> <span data-ttu-id="eba8b-154">> %3F</span><span class="sxs-lookup"><span data-stu-id="eba8b-154">> %3F</span></span> 
    
## <a name="blob-associated-with-each-mapi-url"></a><span data-ttu-id="eba8b-155">与每个 MAPI URL 关联的 Blob</span><span class="sxs-lookup"><span data-stu-id="eba8b-155">Blob associated with each MAPI URL</span></span>

<span data-ttu-id="eba8b-156">为要编制索引的对象推送 MAPI URL 时，存储提供程序还会创建二进制大型对象 (BLOB) ，其中包含 MAPI 协议处理程序的某些信息。</span><span class="sxs-lookup"><span data-stu-id="eba8b-156">When pushing a MAPI URL for an object to be indexed, a store provider also creates a binary large object (BLOB) that contains certain information for the MAPI Protocol Handler.</span></span> <span data-ttu-id="eba8b-157">存储提供程序将此 BLOB 与每个 MAPI URL 关联，并将它在将 MAPI URL 推送到索引器时发送。</span><span class="sxs-lookup"><span data-stu-id="eba8b-157">The store provider associates this BLOB with each MAPI URL and sends it when pushing the MAPI URL to the indexer.</span></span> <span data-ttu-id="eba8b-158">BLOB 的格式如下：</span><span class="sxs-lookup"><span data-stu-id="eba8b-158">The format of the BLOB is as follows:</span></span> 
  
```cpp
DWORD  dwVersion
DWORD  dwFlags
ULONG  cbProfileName
WCHAR  wszProfileName
ULONG  cbProviderItemID
WCHAR  wszProviderItemID
```

<span data-ttu-id="eba8b-159">存储提供程序必须按所示顺序将这些值写入 BLOB。</span><span class="sxs-lookup"><span data-stu-id="eba8b-159">The store provider must write these values to the BLOB in the order shown.</span></span> <span data-ttu-id="eba8b-160">下表介绍了 BLOB 的每个字段。</span><span class="sxs-lookup"><span data-stu-id="eba8b-160">The following table describes each field of the BLOB.</span></span>

|<span data-ttu-id="eba8b-161">Part</span><span class="sxs-lookup"><span data-stu-id="eba8b-161">Part</span></span> | <span data-ttu-id="eba8b-162">说明</span><span class="sxs-lookup"><span data-stu-id="eba8b-162">Description</span></span>|
|:----|:-----------|  
|<span data-ttu-id="eba8b-163">*dwVersion*</span><span class="sxs-lookup"><span data-stu-id="eba8b-163">*dwVersion*</span></span> |<span data-ttu-id="eba8b-164">这是要发送的数据的版本。</span><span class="sxs-lookup"><span data-stu-id="eba8b-164">This is the version of the data being sent.</span></span> <span data-ttu-id="eba8b-165">当前此值为 1。</span><span class="sxs-lookup"><span data-stu-id="eba8b-165">Currently this value is 1.</span></span>|
|<span data-ttu-id="eba8b-166">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="eba8b-166">*dwFlags*</span></span> |<span data-ttu-id="eba8b-167">保留供以后使用。</span><span class="sxs-lookup"><span data-stu-id="eba8b-167">Reserved for future use.</span></span> <span data-ttu-id="eba8b-168">当前此值应为 0。</span><span class="sxs-lookup"><span data-stu-id="eba8b-168">Currently this value should be 0.</span></span>|
|<span data-ttu-id="eba8b-169">*cbProfileName*</span><span class="sxs-lookup"><span data-stu-id="eba8b-169">*cbProfileName*</span></span> |<span data-ttu-id="eba8b-170">配置文件名称的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="eba8b-170">The size of the profile name, in bytes.</span></span> <span data-ttu-id="eba8b-171">此信息对于 MAPI 协议处理程序了解在索引项目时将使用哪个配置文件非常有用。</span><span class="sxs-lookup"><span data-stu-id="eba8b-171">This information is useful for the MAPI Protocol Handler to know which profile to use when indexing the item.</span></span>|
|<span data-ttu-id="eba8b-172">*wszProfileName*</span><span class="sxs-lookup"><span data-stu-id="eba8b-172">*wszProfileName*</span></span> |<span data-ttu-id="eba8b-173">包含配置文件名称的以 Null 结尾的 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="eba8b-173">Null-terminated Unicode string that contains the profile name.</span></span>|
|<span data-ttu-id="eba8b-174">*cbProviderItemID*</span><span class="sxs-lookup"><span data-stu-id="eba8b-174">*cbProviderItemID*</span></span> |<span data-ttu-id="eba8b-175">提供程序项 ID 的大小（以字节为单位）。</span><span class="sxs-lookup"><span data-stu-id="eba8b-175">Size of the provider item ID, in bytes.</span></span> <span data-ttu-id="eba8b-176">存储提供程序应仅发送文件夹的提供程序项目 ID，以防止打开其他文件夹获取此信息。</span><span class="sxs-lookup"><span data-stu-id="eba8b-176">The store provider should send only the provider item ID for folders, to prevent opening additional folders to get this information.</span></span>|
|<span data-ttu-id="eba8b-177">*wszProviderItemID*</span><span class="sxs-lookup"><span data-stu-id="eba8b-177">*wszProviderItemID*</span></span> |<span data-ttu-id="eba8b-178">以 Null 结尾的 Unicode 字符串，其提供程序项 ID 唯一标识存储区中的项。</span><span class="sxs-lookup"><span data-stu-id="eba8b-178">Null-terminated Unicode string with the provider item ID that uniquely identifies the item in the store.</span></span>|
    
## <a name="see-also"></a><span data-ttu-id="eba8b-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="eba8b-179">See also</span></span>

- [<span data-ttu-id="eba8b-180">关于Notification-Based存储索引</span><span class="sxs-lookup"><span data-stu-id="eba8b-180">About Notification-Based Store Indexing</span></span>](about-notification-based-store-indexing.md)
- [<span data-ttu-id="eba8b-181">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="eba8b-181">MAPI Constants</span></span>](mapi-constants.md)

