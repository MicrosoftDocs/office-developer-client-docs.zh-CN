---
title: 关于基于通知的索引的 MAPI URL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 9cb35f0a-267e-2d85-1701-02d52578a0b8
description: 上次修改时间： 2011 年 11 月 8 日
ms.openlocfilehash: 57868996f95cfb135298378d2638bc57b2e69977
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22583671"
---
# <a name="about-mapi-urls-for-notification-based-indexing"></a><span data-ttu-id="9dae9-103">关于基于通知的索引的 MAPI URL</span><span class="sxs-lookup"><span data-stu-id="9dae9-103">About MAPI URLs for Notification-Based Indexing</span></span>

<span data-ttu-id="9dae9-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9dae9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9dae9-105">当存储提供程序通知对象是供索引编制索引器时，它将生成一个唯一标识到 MAPI 协议处理程序的对象的 MAPI URL。</span><span class="sxs-lookup"><span data-stu-id="9dae9-105">When a store provider notifies an indexer that an object is ready for indexing, it generates a MAPI URL that uniquely identifies the object to the MAPI Protocol Handler.</span></span> <span data-ttu-id="9dae9-106">MAPI Url 在 Unicode 中编码和具有以下格式：</span><span class="sxs-lookup"><span data-stu-id="9dae9-106">MAPI URLs are encoded in Unicode, and have the following format:</span></span> 
  
`Mapi://SID/StoreDisplayName ($HashNumber)/StoreType/FolderNameA/…/FolderNameN/[EntryIDEncoded[/at=AttachIDEncoded:FileName]]`

<span data-ttu-id="9dae9-107">下表介绍了典型的 URL 的各个部分。</span><span class="sxs-lookup"><span data-stu-id="9dae9-107">The following table describes the various parts of a typical URL.</span></span>

|<span data-ttu-id="9dae9-108">部分</span><span class="sxs-lookup"><span data-stu-id="9dae9-108">Part</span></span> | <span data-ttu-id="9dae9-109">说明</span><span class="sxs-lookup"><span data-stu-id="9dae9-109">Description</span></span>|
|:----|:-----------|  
|<span data-ttu-id="9dae9-110">*SID*</span><span class="sxs-lookup"><span data-stu-id="9dae9-110">*SID*</span></span> |<span data-ttu-id="9dae9-111">当前用户的安全标识符。</span><span class="sxs-lookup"><span data-stu-id="9dae9-111">The current user's security identifier.</span></span>| 
|<span data-ttu-id="9dae9-112">*StoreDisplayName*</span><span class="sxs-lookup"><span data-stu-id="9dae9-112">*StoreDisplayName*</span></span> |<span data-ttu-id="9dae9-113">一个字符串，该存储指定用户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="9dae9-113">A string that specifies the display name of the user on that store.</span></span>|
|<span data-ttu-id="9dae9-114">*HashNumber*</span><span class="sxs-lookup"><span data-stu-id="9dae9-114">*HashNumber*</span></span> |<span data-ttu-id="9dae9-115">在计算的十六进制表示一个**DWORD**基于存储条目 ID 或存储映射签名。</span><span class="sxs-lookup"><span data-stu-id="9dae9-115">A **DWORD** in hexadecimal representation that is calculated based on the store entry ID or the store mapping signature.</span></span> <span data-ttu-id="9dae9-116">此值存储在注册表，并且将用于更高版本的 MAPI 协议处理程序中存储的标识。</span><span class="sxs-lookup"><span data-stu-id="9dae9-116">This value is stored in the registry and will be used later to identify the store in the MAPI Protocol Handler.</span></span><br/><br/><span data-ttu-id="9dae9-117">此号码必须与其他存储将最小化冲突的方式计算。</span><span class="sxs-lookup"><span data-stu-id="9dae9-117">This number must be calculated in a way that minimizes collisions with other stores.</span></span> <span data-ttu-id="9dae9-118">Microsoft Outlook 用来计算的哈希算法，请参阅[要计算的存储哈希算法](algorithm-to-calculate-the-store-hash-number.md)。</span><span class="sxs-lookup"><span data-stu-id="9dae9-118">For the algorithm that Microsoft Outlook uses to calculate the hash number, see [Algorithm to Calculate the Store Hash Number](algorithm-to-calculate-the-store-hash-number.md).</span></span>|
|<span data-ttu-id="9dae9-119">*StoreType*</span><span class="sxs-lookup"><span data-stu-id="9dae9-119">*StoreType*</span></span> |<span data-ttu-id="9dae9-120">一个数字，标识包含要编制索引的对象的存储区的类型。</span><span class="sxs-lookup"><span data-stu-id="9dae9-120">A number that identifies the type of the store that contains the object to be indexed.</span></span> <span data-ttu-id="9dae9-121">可能值如下所示：</span><span class="sxs-lookup"><span data-stu-id="9dae9-121">The possible values are as follows:</span></span><br/><span data-ttu-id="9dae9-122">-0-默认存储。</span><span class="sxs-lookup"><span data-stu-id="9dae9-122">- 0 - Default store.</span></span><br/><br/><span data-ttu-id="9dae9-123">-1-代理存储区，用于在本地缓存的委托项。</span><span class="sxs-lookup"><span data-stu-id="9dae9-123">- 1 - Delegate store, used for delegate items cached locally.</span></span><br/><br/><span data-ttu-id="9dae9-124">-2-公用文件夹，用于公用文件夹收藏夹。</span><span class="sxs-lookup"><span data-stu-id="9dae9-124">- 2 - Public folders, used for public folder favorites.</span></span><br/><br/><span data-ttu-id="9dae9-125">**注意**： 如果存储区进行爬网而不是推送，使用的值是*X*的字符。</span><span class="sxs-lookup"><span data-stu-id="9dae9-125">**NOTE**: If the store is being crawled instead of pushed, the value that is used is the character*X*.</span></span>| 
|<span data-ttu-id="9dae9-126">*FolderNameA/.../FolderNameN*</span><span class="sxs-lookup"><span data-stu-id="9dae9-126">*FolderNameA/…/FolderNameN*</span></span> |<span data-ttu-id="9dae9-127">从 IPM_SUBTREE 根到邮件的文件夹的路径。</span><span class="sxs-lookup"><span data-stu-id="9dae9-127">The path from the root of the IPM_SUBTREE to the folder or message.</span></span> <span data-ttu-id="9dae9-128">例如，在**收件箱**下的**系列**文件夹中的邮件的**收件箱/系列**有此参数。</span><span class="sxs-lookup"><span data-stu-id="9dae9-128">For example, a message in the **Family** folder under **Inbox** has **Inbox/Family** for this parameter.</span></span> |
|<span data-ttu-id="9dae9-129">*EntryIDEncoded*</span><span class="sxs-lookup"><span data-stu-id="9dae9-129">*EntryIDEncoded*</span></span> |<span data-ttu-id="9dae9-130">MAPI 编码为的 Unicode 字符串项的条目 ID。</span><span class="sxs-lookup"><span data-stu-id="9dae9-130">MAPI entry ID for the item encoded as a Unicode string.</span></span> <span data-ttu-id="9dae9-131">请参阅下的一节"特殊字符"有关如何对某些特殊字符进行编码。</span><span class="sxs-lookup"><span data-stu-id="9dae9-131">See the following section "Special Characters" for information about how certain special characters are encoded.</span></span> <span data-ttu-id="9dae9-132">有关算法进行编码的条目 ID 的详细信息，请参阅[到编码条目 Id 和附件 Id 的算法](algorithm-to-encode-entry-ids-and-attachment-ids.md)。</span><span class="sxs-lookup"><span data-stu-id="9dae9-132">For more information about the algorithm to encode the entry ID, see [Algorithm to Encode Entry IDs and Attachment IDs](algorithm-to-encode-entry-ids-and-attachment-ids.md).</span></span><br/><br/><span data-ttu-id="9dae9-133">**注意**： 时查看以文本形式，这编码的条目 ID 显示为随机朝鲜文字符或依照的算法，具体取决于可用字体的框。</span><span class="sxs-lookup"><span data-stu-id="9dae9-133">**NOTE**: When viewed as text, this encoded entry ID appears as random Hangul characters or boxes in compliance with the algorithm, depending on available fonts.</span></span>  |
|<span data-ttu-id="9dae9-134">*AttachIDEncoded*</span><span class="sxs-lookup"><span data-stu-id="9dae9-134">*AttachIDEncoded*</span></span> |<span data-ttu-id="9dae9-135">附件 ID 编码为的 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="9dae9-135">Attachment ID encoded as a Unicode string.</span></span> <span data-ttu-id="9dae9-136">请参阅下的一节"特殊字符"有关如何对某些特殊字符进行编码。</span><span class="sxs-lookup"><span data-stu-id="9dae9-136">See the following section "Special Characters" for information about how certain special characters are encoded.</span></span> <span data-ttu-id="9dae9-137">有关算法进行编码的条目 ID 的详细信息，请参阅[到编码条目 Id 和附件 Id 的算法](algorithm-to-encode-entry-ids-and-attachment-ids.md)。</span><span class="sxs-lookup"><span data-stu-id="9dae9-137">For more information about the algorithm to encode the entry ID, see [Algorithm to Encode Entry IDs and Attachment IDs](algorithm-to-encode-entry-ids-and-attachment-ids.md).</span></span><br/><br/><span data-ttu-id="9dae9-138">**注意**： 时查看以文本形式，这编码的条目 ID 显示为随机朝鲜文字符或依照的算法，具体取决于可用字体的框。</span><span class="sxs-lookup"><span data-stu-id="9dae9-138">**NOTE**: When viewed as text, this encoded entry ID appears as random Hangul characters or boxes in compliance with the algorithm, depending on available fonts.</span></span> |
|<span data-ttu-id="9dae9-139">*FileName*</span><span class="sxs-lookup"><span data-stu-id="9dae9-139">*FileName*</span></span> |<span data-ttu-id="9dae9-140">附件名称的文件，在邮件中所示。</span><span class="sxs-lookup"><span data-stu-id="9dae9-140">Name of the attachment file, as it appears in the message.</span></span>|
    
## <a name="examples-of-mapi-urls"></a><span data-ttu-id="9dae9-141">MAPI Url 的示例</span><span class="sxs-lookup"><span data-stu-id="9dae9-141">Examples of MAPI URLs</span></span>

<span data-ttu-id="9dae9-142">以下是一些示例的 MAPI Url。</span><span class="sxs-lookup"><span data-stu-id="9dae9-142">The following are some examples of MAPI URLs.</span></span>
  
- <span data-ttu-id="9dae9-143">MAPI 的文件夹的 URL:</span><span class="sxs-lookup"><span data-stu-id="9dae9-143">MAPI URL for a folder:</span></span> 
    
  `mapi://S-1-5-21-2127521184-1604012920-1887927527-71418/Mailbox - Some User ($be19928f)/2/Office`
    
- <span data-ttu-id="9dae9-144">邮件的 MAPI URL:</span><span class="sxs-lookup"><span data-stu-id="9dae9-144">MAPI URL for a message:</span></span> 
    
  `mapi://S-1-5-21-2127521184-1604012920-1887927527-71418/Mailbox - Some User ($484efb89)/0/Calendar/곯가가가걍걝걌곌겷걢곒갑겛개가검걟곔걙곾걤곂갠가`
    
- <span data-ttu-id="9dae9-145">MAPI 的附件的 URL:</span><span class="sxs-lookup"><span data-stu-id="9dae9-145">MAPI URL for an attachment:</span></span> 
    
  `mapi://S-1-5-21-2127521184-1604012920-1887927527-71418/Mailbox - Some User ($484efb89)/0/Inbox/곯가가가걍걝걌곌겷걢곒갑겛개가검걟곔걙곾간곷갦가/at=겅걋각가:somefile.txt`
    
## <a name="special-characters"></a><span data-ttu-id="9dae9-146">特殊字符</span><span class="sxs-lookup"><span data-stu-id="9dae9-146">Special characters</span></span>

<span data-ttu-id="9dae9-147">如果它们出现在邮件或附件，某些字符进行编码。</span><span class="sxs-lookup"><span data-stu-id="9dae9-147">Certain characters are encoded if they appear in the message or attachment.</span></span> <span data-ttu-id="9dae9-148">下面显示 MAPI URL 中的哪些字符编码：</span><span class="sxs-lookup"><span data-stu-id="9dae9-148">The following shows which characters are encoded in a MAPI URL:</span></span>
  
- <span data-ttu-id="9dae9-149">%> 25%</span><span class="sxs-lookup"><span data-stu-id="9dae9-149">% > %25</span></span>
    
- <span data-ttu-id="9dae9-150">/ > %2f</span><span class="sxs-lookup"><span data-stu-id="9dae9-150">/ > %2F</span></span> 
    
- <span data-ttu-id="9dae9-151">\ > %5 C</span><span class="sxs-lookup"><span data-stu-id="9dae9-151">\ > %5C</span></span> 
    
- <span data-ttu-id="9dae9-152">\*> %2a</span><span class="sxs-lookup"><span data-stu-id="9dae9-152">\* > %2A</span></span> 
    
- <span data-ttu-id="9dae9-153">?</span><span class="sxs-lookup"><span data-stu-id="9dae9-153"></span></span> <span data-ttu-id="9dae9-154">> %3f</span><span class="sxs-lookup"><span data-stu-id="9dae9-154">> %3F</span></span> 
    
## <a name="blob-associated-with-each-mapi-url"></a><span data-ttu-id="9dae9-155">每个 MAPI URL 相关联的 blob</span><span class="sxs-lookup"><span data-stu-id="9dae9-155">Blob associated with each MAPI URL</span></span>

<span data-ttu-id="9dae9-156">时将推送对象 MAPI URL 编制索引，存储提供程序还创建包含 MAPI 协议处理程序的特定信息二进制大型对象 (BLOB)。</span><span class="sxs-lookup"><span data-stu-id="9dae9-156">When pushing a MAPI URL for an object to be indexed, a store provider also creates a binary large object (BLOB) that contains certain information for the MAPI Protocol Handler.</span></span> <span data-ttu-id="9dae9-157">存储提供程序将此 BLOB 与每个 MAPI URL 相关联，并将其发送时将 MAPI URL 推送到索引器。</span><span class="sxs-lookup"><span data-stu-id="9dae9-157">The store provider associates this BLOB with each MAPI URL and sends it when pushing the MAPI URL to the indexer.</span></span> <span data-ttu-id="9dae9-158">BLOB 的格式如下所示：</span><span class="sxs-lookup"><span data-stu-id="9dae9-158">The format of the BLOB is as follows:</span></span> 
  
```cpp
DWORD  dwVersion
DWORD  dwFlags
ULONG  cbProfileName
WCHAR  wszProfileName
ULONG  cbProviderItemID
WCHAR  wszProviderItemID
```

<span data-ttu-id="9dae9-159">存储提供程序必须将这些值写入显示的顺序 BLOB。</span><span class="sxs-lookup"><span data-stu-id="9dae9-159">The store provider must write these values to the BLOB in the order shown.</span></span> <span data-ttu-id="9dae9-160">下表描述了各个字段的 BLOB。</span><span class="sxs-lookup"><span data-stu-id="9dae9-160">The following table describes each field of the BLOB.</span></span>

|<span data-ttu-id="9dae9-161">部分</span><span class="sxs-lookup"><span data-stu-id="9dae9-161">Part</span></span> | <span data-ttu-id="9dae9-162">说明</span><span class="sxs-lookup"><span data-stu-id="9dae9-162">Description</span></span>|
|:----|:-----------|  
|<span data-ttu-id="9dae9-163">*dwVersion*</span><span class="sxs-lookup"><span data-stu-id="9dae9-163">*dwVersion*</span></span> |<span data-ttu-id="9dae9-164">这是发送的数据的版本。</span><span class="sxs-lookup"><span data-stu-id="9dae9-164">This is the version of the data being sent.</span></span> <span data-ttu-id="9dae9-165">当前此值为 1。</span><span class="sxs-lookup"><span data-stu-id="9dae9-165">Currently this value is 1.</span></span>|
|<span data-ttu-id="9dae9-166">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="9dae9-166">*dwFlags*</span></span> |<span data-ttu-id="9dae9-167">保留以备今后使用。</span><span class="sxs-lookup"><span data-stu-id="9dae9-167">Reserved for future use.</span></span> <span data-ttu-id="9dae9-168">当前此值应为 0。</span><span class="sxs-lookup"><span data-stu-id="9dae9-168">Currently this value should be 0.</span></span>|
|<span data-ttu-id="9dae9-169">*cbProfileName*</span><span class="sxs-lookup"><span data-stu-id="9dae9-169">*cbProfileName*</span></span> |<span data-ttu-id="9dae9-170">配置文件名称，以字节为单位的大小。</span><span class="sxs-lookup"><span data-stu-id="9dae9-170">The size of the profile name, in bytes.</span></span> <span data-ttu-id="9dae9-171">此信息可用于 MAPI 协议处理程序，以了解索引项时要使用哪个配置文件。</span><span class="sxs-lookup"><span data-stu-id="9dae9-171">This information is useful for the MAPI Protocol Handler to know which profile to use when indexing the item.</span></span>|
|<span data-ttu-id="9dae9-172">*wszProfileName*</span><span class="sxs-lookup"><span data-stu-id="9dae9-172">*wszProfileName*</span></span> |<span data-ttu-id="9dae9-173">空结尾 Unicode 字符串，包含的配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="9dae9-173">Null-terminated Unicode string that contains the profile name.</span></span>|
|<span data-ttu-id="9dae9-174">*cbProviderItemID*</span><span class="sxs-lookup"><span data-stu-id="9dae9-174">*cbProviderItemID*</span></span> |<span data-ttu-id="9dae9-175">提供程序项目 ID，以字节为单位的大小。</span><span class="sxs-lookup"><span data-stu-id="9dae9-175">Size of the provider item ID, in bytes.</span></span> <span data-ttu-id="9dae9-176">存储提供程序应发送仅提供程序项目 ID 为文件夹，以防止打开其他文件夹以获取此信息。</span><span class="sxs-lookup"><span data-stu-id="9dae9-176">The store provider should send only the provider item ID for folders, to prevent opening additional folders to get this information.</span></span>|
|<span data-ttu-id="9dae9-177">*wszProviderItemID*</span><span class="sxs-lookup"><span data-stu-id="9dae9-177">*wszProviderItemID*</span></span> |<span data-ttu-id="9dae9-178">提供程序项目 id 唯一标识存储区中的项目的空结尾 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="9dae9-178">Null-terminated Unicode string with the provider item ID that uniquely identifies the item in the store.</span></span>|
    
## <a name="see-also"></a><span data-ttu-id="9dae9-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9dae9-179">See also</span></span>

- [<span data-ttu-id="9dae9-180">关于基于通知的存储区索引</span><span class="sxs-lookup"><span data-stu-id="9dae9-180">About Notification-Based Store Indexing</span></span>](about-notification-based-store-indexing.md)
- [<span data-ttu-id="9dae9-181">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="9dae9-181">MAPI Constants</span></span>](mapi-constants.md)

