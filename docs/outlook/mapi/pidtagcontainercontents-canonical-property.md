---
title: PidTagContainerContents 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContainerContents
api_type:
- HeaderDef
ms.assetid: 66dbe65a-b9fd-41d5-946f-ec8888363043
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0d6a2f7b8b4f5345faa54e24c359f15ee181a7f3
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22575481"
---
# <a name="pidtagcontainercontents-canonical-property"></a><span data-ttu-id="1a0c9-103">PidTagContainerContents 规范属性</span><span class="sxs-lookup"><span data-stu-id="1a0c9-103">PidTagContainerContents Canonical Property</span></span>

  
  
<span data-ttu-id="1a0c9-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1a0c9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1a0c9-105">包含一个嵌入的内容表对象，提供有关容器的信息。</span><span class="sxs-lookup"><span data-stu-id="1a0c9-105">Contains an embedded contents table object that provides information about a container.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1a0c9-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1a0c9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1a0c9-107">PR_CONTAINER_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="1a0c9-107">PR_CONTAINER_CONTENTS</span></span>  <br/> |
|<span data-ttu-id="1a0c9-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="1a0c9-108">Identifier:</span></span>  <br/> |<span data-ttu-id="1a0c9-109">0x360F</span><span class="sxs-lookup"><span data-stu-id="1a0c9-109">0x360F</span></span>  <br/> |
|<span data-ttu-id="1a0c9-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1a0c9-110">Data type:</span></span>  <br/> |<span data-ttu-id="1a0c9-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="1a0c9-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="1a0c9-112">区域：</span><span class="sxs-lookup"><span data-stu-id="1a0c9-112">Area:</span></span>  <br/> |<span data-ttu-id="1a0c9-113">Container</span><span class="sxs-lookup"><span data-stu-id="1a0c9-113">Container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1a0c9-114">注解</span><span class="sxs-lookup"><span data-stu-id="1a0c9-114">Remarks</span></span>

<span data-ttu-id="1a0c9-115">可以在[IMAPIProp::CopyTo](imapiprop-copyto.md)操作中排除或[IMAPIProp::CopyProps](imapiprop-copyprops.md)操作中包括此属性。</span><span class="sxs-lookup"><span data-stu-id="1a0c9-115">This property can be excluded in [IMAPIProp::CopyTo](imapiprop-copyto.md) operations or included in [IMAPIProp::CopyProps](imapiprop-copyprops.md) operations.</span></span> <span data-ttu-id="1a0c9-116">作为 PT_OBJECT 类型的属性，它无法成功检索[IMAPIProp::GetProps](imapiprop-getprops.md)方法;应由请求 IID_IMAPITable 接口标识符的[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法访问其内容。</span><span class="sxs-lookup"><span data-stu-id="1a0c9-116">As a property of type PT_OBJECT, it cannot be successfully retrieved by the [IMAPIProp::GetProps](imapiprop-getprops.md) method; its contents should be accessed by the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method, requesting the IID_IMAPITable interface identifier.</span></span> <span data-ttu-id="1a0c9-117">服务提供商必须将其报告[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法或如果其设置，但可以选择将其报告不如果它未设置。</span><span class="sxs-lookup"><span data-stu-id="1a0c9-117">Service providers must report it to the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method if it is set, but can optionally report it or not if it is not set.</span></span> 
  
<span data-ttu-id="1a0c9-118">若要检索目录，客户端应用程序应调用[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)方法。</span><span class="sxs-lookup"><span data-stu-id="1a0c9-118">To retrieve table contents, a client application should call the [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) method.</span></span> <span data-ttu-id="1a0c9-119">有关详细信息，请参阅[内容表](contents-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="1a0c9-119">For more information, see [Contents Tables](contents-tables.md).</span></span> 
  
<span data-ttu-id="1a0c9-120">此属性， **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 和**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) 相近的用法。</span><span class="sxs-lookup"><span data-stu-id="1a0c9-120">This property, **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) , and **PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) are similar in usage.</span></span> <span data-ttu-id="1a0c9-121">几个 MAPI 属性提供对表访问：</span><span class="sxs-lookup"><span data-stu-id="1a0c9-121">Several MAPI properties provide access to tables:</span></span> 
  
|<span data-ttu-id="1a0c9-122">**属性**</span><span class="sxs-lookup"><span data-stu-id="1a0c9-122">**Property**</span></span>|<span data-ttu-id="1a0c9-123">**Table**</span><span class="sxs-lookup"><span data-stu-id="1a0c9-123">**Table**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1a0c9-124">PidTagContainerContents</span><span class="sxs-lookup"><span data-stu-id="1a0c9-124">PidTagContainerContents</span></span>  <br/> |<span data-ttu-id="1a0c9-125">内容表</span><span class="sxs-lookup"><span data-stu-id="1a0c9-125">Contents table</span></span>  <br/> |
|<span data-ttu-id="1a0c9-126">**PR_CONTAINER_HIERARCHY**([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1a0c9-126">**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="1a0c9-127">层次结构表</span><span class="sxs-lookup"><span data-stu-id="1a0c9-127">Hierarchy table</span></span>  <br/> |
|<span data-ttu-id="1a0c9-128">**PR_FOLDER_ASSOCIATED_CONTENTS**([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1a0c9-128">**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="1a0c9-129">关联的内容表</span><span class="sxs-lookup"><span data-stu-id="1a0c9-129">Associated contents table</span></span>  <br/> |
|<span data-ttu-id="1a0c9-130">**PR_MESSAGE_ATTACHMENTS**([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1a0c9-130">**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="1a0c9-131">附件表</span><span class="sxs-lookup"><span data-stu-id="1a0c9-131">Attachment table</span></span>  <br/> |
|<span data-ttu-id="1a0c9-132">**PR_MESSAGE_RECIPIENTS**([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="1a0c9-132">**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="1a0c9-133">收件人表</span><span class="sxs-lookup"><span data-stu-id="1a0c9-133">Recipient table</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="1a0c9-134">相关资源</span><span class="sxs-lookup"><span data-stu-id="1a0c9-134">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="1a0c9-135">协议规范</span><span class="sxs-lookup"><span data-stu-id="1a0c9-135">Protocol specifications</span></span>

<span data-ttu-id="1a0c9-136">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1a0c9-136">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1a0c9-137">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="1a0c9-137">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="1a0c9-138">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="1a0c9-138">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="1a0c9-139">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="1a0c9-139">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="1a0c9-140">头文件</span><span class="sxs-lookup"><span data-stu-id="1a0c9-140">Header files</span></span>

<span data-ttu-id="1a0c9-141">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1a0c9-141">Mapidefs.h</span></span>
  
> <span data-ttu-id="1a0c9-142">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1a0c9-142">Provides data type definitions.</span></span>
    
<span data-ttu-id="1a0c9-143">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="1a0c9-143">Mapitags.h</span></span>
  
> <span data-ttu-id="1a0c9-144">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1a0c9-144">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1a0c9-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1a0c9-145">See also</span></span>



[<span data-ttu-id="1a0c9-146">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1a0c9-146">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1a0c9-147">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1a0c9-147">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1a0c9-148">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1a0c9-148">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1a0c9-149">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1a0c9-149">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

