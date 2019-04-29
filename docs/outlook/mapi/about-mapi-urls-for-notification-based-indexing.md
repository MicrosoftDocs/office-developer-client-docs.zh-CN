---
title: 关于基于通知的索引的 MAPI url
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 9cb35f0a-267e-2d85-1701-02d52578a0b8
description: '上次修改时间: 2011 年11月8日'
ms.openlocfilehash: 5a3e45809f36b71968560a4b239e268addf00474
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422479"
---
# <a name="about-mapi-urls-for-notification-based-indexing"></a><span data-ttu-id="ec908-103">关于基于通知的索引的 MAPI url</span><span class="sxs-lookup"><span data-stu-id="ec908-103">About MAPI URLs for Notification-Based Indexing</span></span>

<span data-ttu-id="ec908-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ec908-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ec908-105">当存储提供程序通知索引器对象已准备好编制索引时, 它将生成一个 mapi URL, 该 URL 将对象唯一标识为 mapi 协议处理程序。</span><span class="sxs-lookup"><span data-stu-id="ec908-105">When a store provider notifies an indexer that an object is ready for indexing, it generates a MAPI URL that uniquely identifies the object to the MAPI Protocol Handler.</span></span> <span data-ttu-id="ec908-106">MAPI url 采用 Unicode 编码, 格式如下:</span><span class="sxs-lookup"><span data-stu-id="ec908-106">MAPI URLs are encoded in Unicode, and have the following format:</span></span> 
  
`Mapi://SID/StoreDisplayName ($HashNumber)/StoreType/FolderNameA/…/FolderNameN/[EntryIDEncoded[/at=AttachIDEncoded:FileName]]`

<span data-ttu-id="ec908-107">下表介绍了典型 URL 的各个部分。</span><span class="sxs-lookup"><span data-stu-id="ec908-107">The following table describes the various parts of a typical URL.</span></span>

|<span data-ttu-id="ec908-108">Part</span><span class="sxs-lookup"><span data-stu-id="ec908-108">Part</span></span> | <span data-ttu-id="ec908-109">说明</span><span class="sxs-lookup"><span data-stu-id="ec908-109">Description</span></span>|
|:----|:-----------|  
|<span data-ttu-id="ec908-110">*SID*</span><span class="sxs-lookup"><span data-stu-id="ec908-110">*SID*</span></span> |<span data-ttu-id="ec908-111">当前用户的安全标识符。</span><span class="sxs-lookup"><span data-stu-id="ec908-111">The current user's security identifier.</span></span>| 
|<span data-ttu-id="ec908-112">*StoreDisplayName*</span><span class="sxs-lookup"><span data-stu-id="ec908-112">*StoreDisplayName*</span></span> |<span data-ttu-id="ec908-113">一个字符串, 它指定该存储区上的用户的显示名称。</span><span class="sxs-lookup"><span data-stu-id="ec908-113">A string that specifies the display name of the user on that store.</span></span>|
|<span data-ttu-id="ec908-114">*HashNumber*</span><span class="sxs-lookup"><span data-stu-id="ec908-114">*HashNumber*</span></span> |<span data-ttu-id="ec908-115">十六进制表示法中的一个**DWORD**值, 基于存储项 ID 或存储区映射签名计算。</span><span class="sxs-lookup"><span data-stu-id="ec908-115">A **DWORD** in hexadecimal representation that is calculated based on the store entry ID or the store mapping signature.</span></span> <span data-ttu-id="ec908-116">此值存储在注册表中, 稍后将用于标识 MAPI 协议处理程序中的存储区。</span><span class="sxs-lookup"><span data-stu-id="ec908-116">This value is stored in the registry and will be used later to identify the store in the MAPI Protocol Handler.</span></span><br/><br/><span data-ttu-id="ec908-117">此数字必须以最小化与其他存储区的冲突的方式计算。</span><span class="sxs-lookup"><span data-stu-id="ec908-117">This number must be calculated in a way that minimizes collisions with other stores.</span></span> <span data-ttu-id="ec908-118">有关 Microsoft Outlook 用于计算哈希值的算法, 请参阅[算法计算存储哈希数](algorithm-to-calculate-the-store-hash-number.md)。</span><span class="sxs-lookup"><span data-stu-id="ec908-118">For the algorithm that Microsoft Outlook uses to calculate the hash number, see [Algorithm to Calculate the Store Hash Number](algorithm-to-calculate-the-store-hash-number.md).</span></span>|
|<span data-ttu-id="ec908-119">*StoreType*</span><span class="sxs-lookup"><span data-stu-id="ec908-119">*StoreType*</span></span> |<span data-ttu-id="ec908-120">一个数字, 用于标识包含要编制索引的对象的存储区的类型。</span><span class="sxs-lookup"><span data-stu-id="ec908-120">A number that identifies the type of the store that contains the object to be indexed.</span></span> <span data-ttu-id="ec908-121">可能值包括：</span><span class="sxs-lookup"><span data-stu-id="ec908-121">The possible values are as follows:</span></span><br/><span data-ttu-id="ec908-122">-0-默认存储区。</span><span class="sxs-lookup"><span data-stu-id="ec908-122">- 0 - Default store.</span></span><br/><br/><span data-ttu-id="ec908-123">-1-代理存储, 用于委派本地缓存的项目。</span><span class="sxs-lookup"><span data-stu-id="ec908-123">- 1 - Delegate store, used for delegate items cached locally.</span></span><br/><br/><span data-ttu-id="ec908-124">-2-公用文件夹, 用于公用文件夹收藏夹。</span><span class="sxs-lookup"><span data-stu-id="ec908-124">- 2 - Public folders, used for public folder favorites.</span></span><br/><br/><span data-ttu-id="ec908-125">**注意**: 如果正在对存储进行爬网而不是推送, 则使用的值是字符*X*。</span><span class="sxs-lookup"><span data-stu-id="ec908-125">**NOTE**: If the store is being crawled instead of pushed, the value that is used is the character*X*.</span></span>| 
|<span data-ttu-id="ec908-126">*FolderNameA/.../FolderNameN*</span><span class="sxs-lookup"><span data-stu-id="ec908-126">*FolderNameA/…/FolderNameN*</span></span> |<span data-ttu-id="ec908-127">从 IPM_SUBTREE 的根目录到文件夹或邮件的路径。</span><span class="sxs-lookup"><span data-stu-id="ec908-127">The path from the root of the IPM_SUBTREE to the folder or message.</span></span> <span data-ttu-id="ec908-128">例如, 在 "**收件箱**" 下的 "**家庭**" 文件夹中的邮件包含此参数的**收件箱/家庭**。</span><span class="sxs-lookup"><span data-stu-id="ec908-128">For example, a message in the **Family** folder under **Inbox** has **Inbox/Family** for this parameter.</span></span> |
|<span data-ttu-id="ec908-129">*EntryIDEncoded*</span><span class="sxs-lookup"><span data-stu-id="ec908-129">*EntryIDEncoded*</span></span> |<span data-ttu-id="ec908-130">编码为 Unicode 字符串的项目的 MAPI 条目 ID。</span><span class="sxs-lookup"><span data-stu-id="ec908-130">MAPI entry ID for the item encoded as a Unicode string.</span></span> <span data-ttu-id="ec908-131">有关如何对特定特殊字符进行编码的信息, 请参阅以下部分 "特殊字符"。</span><span class="sxs-lookup"><span data-stu-id="ec908-131">See the following section "Special Characters" for information about how certain special characters are encoded.</span></span> <span data-ttu-id="ec908-132">有关用于对条目 id 进行编码的算法的详细信息, 请参阅[算法对条目 id 和附件 id 进行编码](algorithm-to-encode-entry-ids-and-attachment-ids.md)。</span><span class="sxs-lookup"><span data-stu-id="ec908-132">For more information about the algorithm to encode the entry ID, see [Algorithm to Encode Entry IDs and Attachment IDs](algorithm-to-encode-entry-ids-and-attachment-ids.md).</span></span><br/><br/><span data-ttu-id="ec908-133">**注意**: 作为文本查看时, 此编码的条目 ID 将显示为符合算法的随机朝鲜语字符或方框, 具体取决于可用的字体。</span><span class="sxs-lookup"><span data-stu-id="ec908-133">**NOTE**: When viewed as text, this encoded entry ID appears as random Hangul characters or boxes in compliance with the algorithm, depending on available fonts.</span></span>  |
|<span data-ttu-id="ec908-134">*AttachIDEncoded*</span><span class="sxs-lookup"><span data-stu-id="ec908-134">*AttachIDEncoded*</span></span> |<span data-ttu-id="ec908-135">编码为 Unicode 字符串的附件 ID。</span><span class="sxs-lookup"><span data-stu-id="ec908-135">Attachment ID encoded as a Unicode string.</span></span> <span data-ttu-id="ec908-136">有关如何对特定特殊字符进行编码的信息, 请参阅以下部分 "特殊字符"。</span><span class="sxs-lookup"><span data-stu-id="ec908-136">See the following section "Special Characters" for information about how certain special characters are encoded.</span></span> <span data-ttu-id="ec908-137">有关用于对条目 id 进行编码的算法的详细信息, 请参阅[算法对条目 id 和附件 id 进行编码](algorithm-to-encode-entry-ids-and-attachment-ids.md)。</span><span class="sxs-lookup"><span data-stu-id="ec908-137">For more information about the algorithm to encode the entry ID, see [Algorithm to Encode Entry IDs and Attachment IDs](algorithm-to-encode-entry-ids-and-attachment-ids.md).</span></span><br/><br/><span data-ttu-id="ec908-138">**注意**: 作为文本查看时, 此编码的条目 ID 将显示为符合算法的随机朝鲜语字符或方框, 具体取决于可用的字体。</span><span class="sxs-lookup"><span data-stu-id="ec908-138">**NOTE**: When viewed as text, this encoded entry ID appears as random Hangul characters or boxes in compliance with the algorithm, depending on available fonts.</span></span> |
|<span data-ttu-id="ec908-139">*FileName*</span><span class="sxs-lookup"><span data-stu-id="ec908-139">*FileName*</span></span> |<span data-ttu-id="ec908-140">附件文件在邮件中显示时的名称。</span><span class="sxs-lookup"><span data-stu-id="ec908-140">Name of the attachment file, as it appears in the message.</span></span>|
    
## <a name="examples-of-mapi-urls"></a><span data-ttu-id="ec908-141">MAPI url 的示例</span><span class="sxs-lookup"><span data-stu-id="ec908-141">Examples of MAPI URLs</span></span>

<span data-ttu-id="ec908-142">以下是 MAPI url 的一些示例。</span><span class="sxs-lookup"><span data-stu-id="ec908-142">The following are some examples of MAPI URLs.</span></span>
  
- <span data-ttu-id="ec908-143">文件夹的 MAPI URL:</span><span class="sxs-lookup"><span data-stu-id="ec908-143">MAPI URL for a folder:</span></span> 
    
  `mapi://S-1-5-21-2127521184-1604012920-1887927527-71418/Mailbox - Some User ($be19928f)/2/Office`
    
- <span data-ttu-id="ec908-144">邮件的 MAPI URL:</span><span class="sxs-lookup"><span data-stu-id="ec908-144">MAPI URL for a message:</span></span> 
    
  `mapi://S-1-5-21-2127521184-1604012920-1887927527-71418/Mailbox - Some User ($484efb89)/0/Calendar/곯가가가걍걝걌곌겷걢곒갑겛개가검걟곔걙곾걤곂갠가`
    
- <span data-ttu-id="ec908-145">附件的 MAPI URL:</span><span class="sxs-lookup"><span data-stu-id="ec908-145">MAPI URL for an attachment:</span></span> 
    
  `mapi://S-1-5-21-2127521184-1604012920-1887927527-71418/Mailbox - Some User ($484efb89)/0/Inbox/곯가가가걍걝걌곌겷걢곒갑겛개가검걟곔걙곾간곷갦가/at=겅걋각가:somefile.txt`
    
## <a name="special-characters"></a><span data-ttu-id="ec908-146">特殊字符</span><span class="sxs-lookup"><span data-stu-id="ec908-146">Special characters</span></span>

<span data-ttu-id="ec908-147">如果某些字符出现在邮件或附件中, 则对其进行编码。</span><span class="sxs-lookup"><span data-stu-id="ec908-147">Certain characters are encoded if they appear in the message or attachment.</span></span> <span data-ttu-id="ec908-148">下面显示了在 MAPI URL 中编码的字符:</span><span class="sxs-lookup"><span data-stu-id="ec908-148">The following shows which characters are encoded in a MAPI URL:</span></span>
  
- <span data-ttu-id="ec908-149">% >% 25</span><span class="sxs-lookup"><span data-stu-id="ec908-149">% > %25</span></span>
    
- <span data-ttu-id="ec908-150">/>% 2f</span><span class="sxs-lookup"><span data-stu-id="ec908-150">/ > %2F</span></span> 
    
- <span data-ttu-id="ec908-151">\ >% 5c</span><span class="sxs-lookup"><span data-stu-id="ec908-151">\ > %5C</span></span> 
    
- <span data-ttu-id="ec908-152">\*>% 2a</span><span class="sxs-lookup"><span data-stu-id="ec908-152">\* > %2A</span></span> 
    
- <span data-ttu-id="ec908-153">?</span><span class="sxs-lookup"><span data-stu-id="ec908-153"></span></span> <span data-ttu-id="ec908-154">>% 3F</span><span class="sxs-lookup"><span data-stu-id="ec908-154">> %3F</span></span> 
    
## <a name="blob-associated-with-each-mapi-url"></a><span data-ttu-id="ec908-155">与每个 MAPI URL 相关联的 Blob</span><span class="sxs-lookup"><span data-stu-id="ec908-155">Blob associated with each MAPI URL</span></span>

<span data-ttu-id="ec908-156">为要编制索引的对象推送 MAPI URL 时, 存储提供程序还会创建一个二进制大型对象 (BLOB), 其中包含 MAPI 协议处理程序的特定信息。</span><span class="sxs-lookup"><span data-stu-id="ec908-156">When pushing a MAPI URL for an object to be indexed, a store provider also creates a binary large object (BLOB) that contains certain information for the MAPI Protocol Handler.</span></span> <span data-ttu-id="ec908-157">存储提供程序将此 BLOB 与每个 mapi url 相关联, 并在将 MAPI url 推送到索引器时发送该 url。</span><span class="sxs-lookup"><span data-stu-id="ec908-157">The store provider associates this BLOB with each MAPI URL and sends it when pushing the MAPI URL to the indexer.</span></span> <span data-ttu-id="ec908-158">BLOB 的格式如下所示:</span><span class="sxs-lookup"><span data-stu-id="ec908-158">The format of the BLOB is as follows:</span></span> 
  
```cpp
DWORD  dwVersion
DWORD  dwFlags
ULONG  cbProfileName
WCHAR  wszProfileName
ULONG  cbProviderItemID
WCHAR  wszProviderItemID
```

<span data-ttu-id="ec908-159">存储提供程序必须按显示的顺序将这些值写入 BLOB。</span><span class="sxs-lookup"><span data-stu-id="ec908-159">The store provider must write these values to the BLOB in the order shown.</span></span> <span data-ttu-id="ec908-160">下表介绍了 BLOB 的每个字段。</span><span class="sxs-lookup"><span data-stu-id="ec908-160">The following table describes each field of the BLOB.</span></span>

|<span data-ttu-id="ec908-161">Part</span><span class="sxs-lookup"><span data-stu-id="ec908-161">Part</span></span> | <span data-ttu-id="ec908-162">说明</span><span class="sxs-lookup"><span data-stu-id="ec908-162">Description</span></span>|
|:----|:-----------|  
|<span data-ttu-id="ec908-163">*dwVersion*</span><span class="sxs-lookup"><span data-stu-id="ec908-163">*dwVersion*</span></span> |<span data-ttu-id="ec908-164">这是要发送的数据的版本。</span><span class="sxs-lookup"><span data-stu-id="ec908-164">This is the version of the data being sent.</span></span> <span data-ttu-id="ec908-165">当前此值为1。</span><span class="sxs-lookup"><span data-stu-id="ec908-165">Currently this value is 1.</span></span>|
|<span data-ttu-id="ec908-166">*dwFlags*</span><span class="sxs-lookup"><span data-stu-id="ec908-166">*dwFlags*</span></span> |<span data-ttu-id="ec908-167">保留供以后使用。</span><span class="sxs-lookup"><span data-stu-id="ec908-167">Reserved for future use.</span></span> <span data-ttu-id="ec908-168">当前此值应为0。</span><span class="sxs-lookup"><span data-stu-id="ec908-168">Currently this value should be 0.</span></span>|
|<span data-ttu-id="ec908-169">*cbProfileName*</span><span class="sxs-lookup"><span data-stu-id="ec908-169">*cbProfileName*</span></span> |<span data-ttu-id="ec908-170">配置文件名称的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="ec908-170">The size of the profile name, in bytes.</span></span> <span data-ttu-id="ec908-171">此信息对 MAPI 协议处理程序很有用, 以知道在对项目编制索引时要使用哪个配置文件。</span><span class="sxs-lookup"><span data-stu-id="ec908-171">This information is useful for the MAPI Protocol Handler to know which profile to use when indexing the item.</span></span>|
|<span data-ttu-id="ec908-172">*wszProfileName*</span><span class="sxs-lookup"><span data-stu-id="ec908-172">*wszProfileName*</span></span> |<span data-ttu-id="ec908-173">以 Null 结尾的 Unicode 字符串, 其中包含配置文件名称。</span><span class="sxs-lookup"><span data-stu-id="ec908-173">Null-terminated Unicode string that contains the profile name.</span></span>|
|<span data-ttu-id="ec908-174">*cbProviderItemID*</span><span class="sxs-lookup"><span data-stu-id="ec908-174">*cbProviderItemID*</span></span> |<span data-ttu-id="ec908-175">提供程序项目 ID 的大小 (以字节为单位)。</span><span class="sxs-lookup"><span data-stu-id="ec908-175">Size of the provider item ID, in bytes.</span></span> <span data-ttu-id="ec908-176">存储提供程序应仅发送文件夹的提供程序项目 ID, 以防止打开其他文件夹获取此信息。</span><span class="sxs-lookup"><span data-stu-id="ec908-176">The store provider should send only the provider item ID for folders, to prevent opening additional folders to get this information.</span></span>|
|<span data-ttu-id="ec908-177">*wszProviderItemID*</span><span class="sxs-lookup"><span data-stu-id="ec908-177">*wszProviderItemID*</span></span> |<span data-ttu-id="ec908-178">以 Null 结尾的 Unicode 字符串, 其中包含唯一标识存储中的项目的提供程序项目 ID。</span><span class="sxs-lookup"><span data-stu-id="ec908-178">Null-terminated Unicode string with the provider item ID that uniquely identifies the item in the store.</span></span>|
    
## <a name="see-also"></a><span data-ttu-id="ec908-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ec908-179">See also</span></span>

- [<span data-ttu-id="ec908-180">关于基于通知的存储索引</span><span class="sxs-lookup"><span data-stu-id="ec908-180">About Notification-Based Store Indexing</span></span>](about-notification-based-store-indexing.md)
- [<span data-ttu-id="ec908-181">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="ec908-181">MAPI Constants</span></span>](mapi-constants.md)

