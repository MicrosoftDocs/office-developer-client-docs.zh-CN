---
title: PidTagContainerHierarchy 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContainerHierarchy
api_type:
- HeaderDef
ms.assetid: 6917510d-ca1e-4049-9eab-09313753ecf0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f009d7ce5cd1856ccff1e00953188c8edde7a6bc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332856"
---
# <a name="pidtagcontainerhierarchy-canonical-property"></a><span data-ttu-id="405a5-103">PidTagContainerHierarchy 规范属性</span><span class="sxs-lookup"><span data-stu-id="405a5-103">PidTagContainerHierarchy Canonical Property</span></span>

  
  
<span data-ttu-id="405a5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="405a5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="405a5-105">包含一个提供有关子容器的信息的嵌入的层次结构表对象。</span><span class="sxs-lookup"><span data-stu-id="405a5-105">Contains an embedded hierarchy table object that provides information about the child containers.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="405a5-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="405a5-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="405a5-107">PR_CONTAINER_HIERARCHY</span><span class="sxs-lookup"><span data-stu-id="405a5-107">PR_CONTAINER_HIERARCHY</span></span>  <br/> |
|<span data-ttu-id="405a5-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="405a5-108">Identifier:</span></span>  <br/> |<span data-ttu-id="405a5-109">0x360E</span><span class="sxs-lookup"><span data-stu-id="405a5-109">0x360E</span></span>  <br/> |
|<span data-ttu-id="405a5-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="405a5-110">Data type:</span></span>  <br/> |<span data-ttu-id="405a5-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="405a5-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="405a5-112">区域：</span><span class="sxs-lookup"><span data-stu-id="405a5-112">Area:</span></span>  <br/> |<span data-ttu-id="405a5-113">Container</span><span class="sxs-lookup"><span data-stu-id="405a5-113">Container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="405a5-114">注解</span><span class="sxs-lookup"><span data-stu-id="405a5-114">Remarks</span></span>

<span data-ttu-id="405a5-115">此属性可以排除在[IMAPIProp:: CopyTo](imapiprop-copyto.md)操作中, 也可以包含在[IMAPIProp:: CopyProps](imapiprop-copyprops.md)操作中。</span><span class="sxs-lookup"><span data-stu-id="405a5-115">This property can be excluded in [IMAPIProp::CopyTo](imapiprop-copyto.md) operations or included in [IMAPIProp::CopyProps](imapiprop-copyprops.md) operations.</span></span> <span data-ttu-id="405a5-116">作为**PT_OBJECT**类型的属性, [IMAPIProp:: GetProps](imapiprop-getprops.md)方法无法成功检索它;其内容应由[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法访问, 请求 IID_IMAPITable 接口标识符。</span><span class="sxs-lookup"><span data-stu-id="405a5-116">As a property of type **PT_OBJECT**, it cannot be successfully retrieved by the [IMAPIProp::GetProps](imapiprop-getprops.md) method; its contents should be accessed by the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method, requesting the IID_IMAPITable interface identifier.</span></span> <span data-ttu-id="405a5-117">如果设置了服务提供程序, 则必须将其报告给[IMAPIProp:: GetPropList](imapiprop-getproplist.md)方法, 但如果未设置, 则可以选择报告它。</span><span class="sxs-lookup"><span data-stu-id="405a5-117">Service providers must report it to the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method if it is set, but can optionally report it or not if it is not set.</span></span> 
  
<span data-ttu-id="405a5-118">若要检索表内容, 客户端应用程序应调用[IMAPIContainer:: GetHierarchyTable](imapicontainer-gethierarchytable.md)方法。</span><span class="sxs-lookup"><span data-stu-id="405a5-118">To retrieve table contents, a client application should call the [IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md) method.</span></span> <span data-ttu-id="405a5-119">有关详细信息, 请参阅[层次结构表](hierarchy-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="405a5-119">For more information, see [Hierarchy Tables](hierarchy-tables.md).</span></span> 
  
 <span data-ttu-id="405a5-120">**PR_CONTAINER_CONTENTS**([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))、 **PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) 和此属性在使用中相似。</span><span class="sxs-lookup"><span data-stu-id="405a5-120">**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)), **PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)), and this property are similar in usage.</span></span> <span data-ttu-id="405a5-121">有几个 MAPI 属性提供对表的访问权限:</span><span class="sxs-lookup"><span data-stu-id="405a5-121">Several MAPI properties provide access to tables:</span></span> 
  
|<span data-ttu-id="405a5-122">**Property**</span><span class="sxs-lookup"><span data-stu-id="405a5-122">**Property**</span></span>|<span data-ttu-id="405a5-123">**Table**</span><span class="sxs-lookup"><span data-stu-id="405a5-123">**Table**</span></span>|
|:-----|:-----|
|<span data-ttu-id="405a5-124">**PR_CONTAINER_CONTENTS**([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="405a5-124">**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="405a5-125">内容表</span><span class="sxs-lookup"><span data-stu-id="405a5-125">Contents table</span></span>  <br/> |
|<span data-ttu-id="405a5-126">**PR_CONTAINER_HIERARCHY**</span><span class="sxs-lookup"><span data-stu-id="405a5-126">**PR_CONTAINER_HIERARCHY**</span></span> <br/> |<span data-ttu-id="405a5-127">层次结构表</span><span class="sxs-lookup"><span data-stu-id="405a5-127">Hierarchy table</span></span>  <br/> |
|<span data-ttu-id="405a5-128">**PR_FOLDER_ASSOCIATED_CONTENTS**([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="405a5-128">**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="405a5-129">关联的内容表</span><span class="sxs-lookup"><span data-stu-id="405a5-129">Associated contents table</span></span>  <br/> |
|<span data-ttu-id="405a5-130">**PR_MESSAGE_ATTACHMENTS**([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="405a5-130">**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="405a5-131">附件表</span><span class="sxs-lookup"><span data-stu-id="405a5-131">Attachment table</span></span>  <br/> |
|<span data-ttu-id="405a5-132">**PR_MESSAGE_RECIPIENTS**([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="405a5-132">**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="405a5-133">收件人表</span><span class="sxs-lookup"><span data-stu-id="405a5-133">Recipient table</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="405a5-134">相关资源</span><span class="sxs-lookup"><span data-stu-id="405a5-134">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="405a5-135">协议规范</span><span class="sxs-lookup"><span data-stu-id="405a5-135">Protocol specifications</span></span>

<span data-ttu-id="405a5-136">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="405a5-136">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="405a5-137">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="405a5-137">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="405a5-138">[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="405a5-138">[[MS-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="405a5-139">处理客户端与服务器之间的数据传输的顺序和流。</span><span class="sxs-lookup"><span data-stu-id="405a5-139">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="405a5-140">[[毫秒-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="405a5-140">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="405a5-141">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="405a5-141">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="405a5-142">头文件</span><span class="sxs-lookup"><span data-stu-id="405a5-142">Header files</span></span>

<span data-ttu-id="405a5-143">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="405a5-143">Mapidefs.h</span></span>
  
> <span data-ttu-id="405a5-144">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="405a5-144">Provides data type definitions.</span></span>
    
<span data-ttu-id="405a5-145">Mapitags</span><span class="sxs-lookup"><span data-stu-id="405a5-145">Mapitags.h</span></span>
  
> <span data-ttu-id="405a5-146">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="405a5-146">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="405a5-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="405a5-147">See also</span></span>



[<span data-ttu-id="405a5-148">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="405a5-148">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="405a5-149">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="405a5-149">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="405a5-150">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="405a5-150">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="405a5-151">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="405a5-151">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

