---
title: PidTagFolderAssociatedContents 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagFolderAssociatedContents
api_type:
- HeaderDef
ms.assetid: d1f3f589-dc2d-4538-a13f-278dad29bcc7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c85c5d7c3e80508c4d328f69ac4ad15f0f2c355a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316301"
---
# <a name="pidtagfolderassociatedcontents-canonical-property"></a><span data-ttu-id="4a65b-103">PidTagFolderAssociatedContents 规范属性</span><span class="sxs-lookup"><span data-stu-id="4a65b-103">PidTagFolderAssociatedContents Canonical Property</span></span>

  
  
<span data-ttu-id="4a65b-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4a65b-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4a65b-105">包含一个嵌入的内容表对象, 该对象提供有关关联的内容表的信息。</span><span class="sxs-lookup"><span data-stu-id="4a65b-105">Contains an embedded contents table object that provides information about the associated contents table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4a65b-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4a65b-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4a65b-107">PR_FOLDER_ASSOCIATED_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="4a65b-107">PR_FOLDER_ASSOCIATED_CONTENTS</span></span>  <br/> |
|<span data-ttu-id="4a65b-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="4a65b-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4a65b-109">0x3610</span><span class="sxs-lookup"><span data-stu-id="4a65b-109">0x3610</span></span>  <br/> |
|<span data-ttu-id="4a65b-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4a65b-110">Data type:</span></span>  <br/> |<span data-ttu-id="4a65b-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="4a65b-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="4a65b-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4a65b-112">Area:</span></span>  <br/> |<span data-ttu-id="4a65b-113">MAPI 容器</span><span class="sxs-lookup"><span data-stu-id="4a65b-113">MAPI container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4a65b-114">注解</span><span class="sxs-lookup"><span data-stu-id="4a65b-114">Remarks</span></span>

<span data-ttu-id="4a65b-115">"关联的内容" 表表示 "标准内容" 表中未显示的子文件夹。</span><span class="sxs-lookup"><span data-stu-id="4a65b-115">The associated contents table represents a subfolder that does not appear in the standard contents table.</span></span> <span data-ttu-id="4a65b-116">它包含文件夹的关联的或隐藏的邮件。</span><span class="sxs-lookup"><span data-stu-id="4a65b-116">It contains the folder's associated, or hidden, messages.</span></span> 
  
<span data-ttu-id="4a65b-117">此属性可以排除在[IMAPIProp:: CopyTo](imapiprop-copyto.md)操作中, 也可以包含在[IMAPIProp:: CopyProps](imapiprop-copyprops.md)操作中。</span><span class="sxs-lookup"><span data-stu-id="4a65b-117">This property can be excluded in [IMAPIProp::CopyTo](imapiprop-copyto.md) operations or included in [IMAPIProp::CopyProps](imapiprop-copyprops.md) operations.</span></span> <span data-ttu-id="4a65b-118">作为**PT_OBJECT**类型的属性, [IMAPIProp:: GetProps](imapiprop-getprops.md)方法无法成功检索它;其内容应由[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法访问, 请求**IID_IMAPITable**接口标识符。</span><span class="sxs-lookup"><span data-stu-id="4a65b-118">As a property of type **PT_OBJECT**, it cannot be successfully retrieved by the [IMAPIProp::GetProps](imapiprop-getprops.md) method; its contents should be accessed by the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method, requesting the **IID_IMAPITable** interface identifier.</span></span> <span data-ttu-id="4a65b-119">如果设置了服务提供程序, 则必须将其报告给[IMAPIProp:: GetPropList](imapiprop-getproplist.md)方法, 但如果未设置, 则可能需要报告它。</span><span class="sxs-lookup"><span data-stu-id="4a65b-119">Service providers must report it to the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method if it is set, but may optionally report it or not if it is not set.</span></span> 
  
<span data-ttu-id="4a65b-120">若要检索表内容, 客户端应用程序应调用[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)方法。</span><span class="sxs-lookup"><span data-stu-id="4a65b-120">To retrieve table contents, client applications should call the [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) method.</span></span> <span data-ttu-id="4a65b-121">有关文件夹内容表的详细信息, 请参阅[内容表](contents-tables.md)和[显示文件夹内容表](displaying-a-folder-contents-table.md)。</span><span class="sxs-lookup"><span data-stu-id="4a65b-121">For more information on folder contents tables, see [Contents Tables](contents-tables.md) and [Displaying a Folder Contents Table](displaying-a-folder-contents-table.md).</span></span> 
  
<span data-ttu-id="4a65b-122">**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))、 **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 和此属性在使用中相似。</span><span class="sxs-lookup"><span data-stu-id="4a65b-122">The **PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)), **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)), and this property are similar in usage.</span></span> <span data-ttu-id="4a65b-123">有几个 MAPI 属性提供对表的访问权限:</span><span class="sxs-lookup"><span data-stu-id="4a65b-123">Several MAPI properties provide access to tables:</span></span> 
  
|<span data-ttu-id="4a65b-124">**Property**</span><span class="sxs-lookup"><span data-stu-id="4a65b-124">**Property**</span></span>|<span data-ttu-id="4a65b-125">**Table**</span><span class="sxs-lookup"><span data-stu-id="4a65b-125">**Table**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4a65b-126">**PR_CONTAINER_CONTENTS**([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="4a65b-126">**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="4a65b-127">内容表</span><span class="sxs-lookup"><span data-stu-id="4a65b-127">Contents table</span></span>  <br/> |
|<span data-ttu-id="4a65b-128">**PR_CONTAINER_HIERARCHY**([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="4a65b-128">**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="4a65b-129">层次结构表</span><span class="sxs-lookup"><span data-stu-id="4a65b-129">Hierarchy table</span></span>  <br/> |
|<span data-ttu-id="4a65b-130">**PR_FOLDER_ASSOCIATED_CONTENTS**</span><span class="sxs-lookup"><span data-stu-id="4a65b-130">**PR_FOLDER_ASSOCIATED_CONTENTS**</span></span> <br/> |<span data-ttu-id="4a65b-131">关联的内容表</span><span class="sxs-lookup"><span data-stu-id="4a65b-131">Associated contents table</span></span>  <br/> |
|<span data-ttu-id="4a65b-132">**PR_MESSAGE_ATTACHMENTS**([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="4a65b-132">**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="4a65b-133">附件表</span><span class="sxs-lookup"><span data-stu-id="4a65b-133">Attachment table</span></span>  <br/> |
|<span data-ttu-id="4a65b-134">**PR_MESSAGE_RECIPIENTS**([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="4a65b-134">**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="4a65b-135">收件人表</span><span class="sxs-lookup"><span data-stu-id="4a65b-135">Recipient table</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="4a65b-136">相关资源</span><span class="sxs-lookup"><span data-stu-id="4a65b-136">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4a65b-137">协议规范</span><span class="sxs-lookup"><span data-stu-id="4a65b-137">Protocol specifications</span></span>

<span data-ttu-id="4a65b-138">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4a65b-138">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4a65b-139">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="4a65b-139">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="4a65b-140">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4a65b-140">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4a65b-141">处理客户端与服务器之间的数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="4a65b-141">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="4a65b-142">[[毫秒-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4a65b-142">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4a65b-143">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议项目之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="4a65b-143">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting items.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="4a65b-144">头文件</span><span class="sxs-lookup"><span data-stu-id="4a65b-144">Header files</span></span>

<span data-ttu-id="4a65b-145">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="4a65b-145">Mapidefs.h</span></span>
  
> <span data-ttu-id="4a65b-146">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4a65b-146">Provides data type definitions.</span></span>
    
<span data-ttu-id="4a65b-147">Mapitags</span><span class="sxs-lookup"><span data-stu-id="4a65b-147">Mapitags.h</span></span>
  
> <span data-ttu-id="4a65b-148">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4a65b-148">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4a65b-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a65b-149">See also</span></span>



[<span data-ttu-id="4a65b-150">PidTagAssociatedContentCount 规范属性</span><span class="sxs-lookup"><span data-stu-id="4a65b-150">PidTagAssociatedContentCount Canonical Property</span></span>](pidtagassociatedcontentcount-canonical-property.md)


[<span data-ttu-id="4a65b-151">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4a65b-151">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4a65b-152">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4a65b-152">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4a65b-153">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4a65b-153">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4a65b-154">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4a65b-154">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

