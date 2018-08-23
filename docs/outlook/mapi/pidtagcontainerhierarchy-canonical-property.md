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
ms.openlocfilehash: 2c9598b583ba62adc42d6fb2b904dfe4981286ff
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22578106"
---
# <a name="pidtagcontainerhierarchy-canonical-property"></a><span data-ttu-id="a949a-103">PidTagContainerHierarchy 规范属性</span><span class="sxs-lookup"><span data-stu-id="a949a-103">PidTagContainerHierarchy Canonical Property</span></span>

  
  
<span data-ttu-id="a949a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a949a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a949a-105">包含嵌入层次结构表对象提供有关子容器。</span><span class="sxs-lookup"><span data-stu-id="a949a-105">Contains an embedded hierarchy table object that provides information about the child containers.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="a949a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="a949a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="a949a-107">PR_CONTAINER_HIERARCHY</span><span class="sxs-lookup"><span data-stu-id="a949a-107">PR_CONTAINER_HIERARCHY</span></span>  <br/> |
|<span data-ttu-id="a949a-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="a949a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="a949a-109">0x360E</span><span class="sxs-lookup"><span data-stu-id="a949a-109">0x360E</span></span>  <br/> |
|<span data-ttu-id="a949a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="a949a-110">Data type:</span></span>  <br/> |<span data-ttu-id="a949a-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="a949a-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="a949a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="a949a-112">Area:</span></span>  <br/> |<span data-ttu-id="a949a-113">Container</span><span class="sxs-lookup"><span data-stu-id="a949a-113">Container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="a949a-114">注解</span><span class="sxs-lookup"><span data-stu-id="a949a-114">Remarks</span></span>

<span data-ttu-id="a949a-115">可以在[IMAPIProp::CopyTo](imapiprop-copyto.md)操作中排除或[IMAPIProp::CopyProps](imapiprop-copyprops.md)操作中包括此属性。</span><span class="sxs-lookup"><span data-stu-id="a949a-115">This property can be excluded in [IMAPIProp::CopyTo](imapiprop-copyto.md) operations or included in [IMAPIProp::CopyProps](imapiprop-copyprops.md) operations.</span></span> <span data-ttu-id="a949a-116">作为**PT_OBJECT**类型的属性，它无法成功检索[IMAPIProp::GetProps](imapiprop-getprops.md)方法;应由请求 IID_IMAPITable 接口标识符的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法访问其内容。</span><span class="sxs-lookup"><span data-stu-id="a949a-116">As a property of type **PT_OBJECT**, it cannot be successfully retrieved by the [IMAPIProp::GetProps](imapiprop-getprops.md) method; its contents should be accessed by the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method, requesting the IID_IMAPITable interface identifier.</span></span> <span data-ttu-id="a949a-117">服务提供商必须将其报告[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法或如果其设置，但可以选择将其报告不如果它未设置。</span><span class="sxs-lookup"><span data-stu-id="a949a-117">Service providers must report it to the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method if it is set, but can optionally report it or not if it is not set.</span></span> 
  
<span data-ttu-id="a949a-118">若要检索目录，客户端应用程序应调用[IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md)方法。</span><span class="sxs-lookup"><span data-stu-id="a949a-118">To retrieve table contents, a client application should call the [IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md) method.</span></span> <span data-ttu-id="a949a-119">有关详细信息，请参阅[层次结构表](hierarchy-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="a949a-119">For more information, see [Hierarchy Tables](hierarchy-tables.md).</span></span> 
  
 <span data-ttu-id="a949a-120">**PR_CONTAINER_CONTENTS**([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))， **PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) 和此属性是在使用率类似。</span><span class="sxs-lookup"><span data-stu-id="a949a-120">**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md)), **PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)), and this property are similar in usage.</span></span> <span data-ttu-id="a949a-121">几个 MAPI 属性提供对表访问：</span><span class="sxs-lookup"><span data-stu-id="a949a-121">Several MAPI properties provide access to tables:</span></span> 
  
|<span data-ttu-id="a949a-122">**属性**</span><span class="sxs-lookup"><span data-stu-id="a949a-122">**Property**</span></span>|<span data-ttu-id="a949a-123">**Table**</span><span class="sxs-lookup"><span data-stu-id="a949a-123">**Table**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a949a-124">**PR_CONTAINER_CONTENTS**([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="a949a-124">**PR_CONTAINER_CONTENTS** ([PidTagContainerContents](pidtagcontainercontents-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="a949a-125">内容表</span><span class="sxs-lookup"><span data-stu-id="a949a-125">Contents table</span></span>  <br/> |
|<span data-ttu-id="a949a-126">**PR_CONTAINER_HIERARCHY**</span><span class="sxs-lookup"><span data-stu-id="a949a-126">**PR_CONTAINER_HIERARCHY**</span></span> <br/> |<span data-ttu-id="a949a-127">层次结构表</span><span class="sxs-lookup"><span data-stu-id="a949a-127">Hierarchy table</span></span>  <br/> |
|<span data-ttu-id="a949a-128">**PR_FOLDER_ASSOCIATED_CONTENTS**([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="a949a-128">**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="a949a-129">关联的内容表</span><span class="sxs-lookup"><span data-stu-id="a949a-129">Associated contents table</span></span>  <br/> |
|<span data-ttu-id="a949a-130">**PR_MESSAGE_ATTACHMENTS**([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="a949a-130">**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="a949a-131">附件表</span><span class="sxs-lookup"><span data-stu-id="a949a-131">Attachment table</span></span>  <br/> |
|<span data-ttu-id="a949a-132">**PR_MESSAGE_RECIPIENTS**([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="a949a-132">**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="a949a-133">收件人表</span><span class="sxs-lookup"><span data-stu-id="a949a-133">Recipient table</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="a949a-134">相关资源</span><span class="sxs-lookup"><span data-stu-id="a949a-134">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="a949a-135">协议规范</span><span class="sxs-lookup"><span data-stu-id="a949a-135">Protocol specifications</span></span>

<span data-ttu-id="a949a-136">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a949a-136">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a949a-137">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="a949a-137">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="a949a-138">[[MS OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a949a-138">[[MS-OXCFXICS]](http://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a949a-139">处理顺序和客户端和服务器之间的数据传输的流。</span><span class="sxs-lookup"><span data-stu-id="a949a-139">Handles the order and flow for data transfers between a client and server.</span></span>
    
<span data-ttu-id="a949a-140">[[MS OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="a949a-140">[[MS-OXCICAL]](http://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="a949a-141">IETF RFC2445、 RFC2446，和 RFC2447，和约会和会议对象之间进行转换。</span><span class="sxs-lookup"><span data-stu-id="a949a-141">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="a949a-142">头文件</span><span class="sxs-lookup"><span data-stu-id="a949a-142">Header files</span></span>

<span data-ttu-id="a949a-143">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="a949a-143">Mapidefs.h</span></span>
  
> <span data-ttu-id="a949a-144">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="a949a-144">Provides data type definitions.</span></span>
    
<span data-ttu-id="a949a-145">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="a949a-145">Mapitags.h</span></span>
  
> <span data-ttu-id="a949a-146">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="a949a-146">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="a949a-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a949a-147">See also</span></span>



[<span data-ttu-id="a949a-148">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="a949a-148">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="a949a-149">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="a949a-149">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="a949a-150">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="a949a-150">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="a949a-151">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="a949a-151">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

