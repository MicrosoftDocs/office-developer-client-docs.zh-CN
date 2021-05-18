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
ms.openlocfilehash: 5f0717c2a6def6f99f1e53217764e8820125b79d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283126"
---
# <a name="pidtagcontainercontents-canonical-property"></a><span data-ttu-id="b5ecf-103">PidTagContainerContents 规范属性</span><span class="sxs-lookup"><span data-stu-id="b5ecf-103">PidTagContainerContents Canonical Property</span></span>

  
  
<span data-ttu-id="b5ecf-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b5ecf-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b5ecf-105">包含提供有关容器信息的嵌入内容表对象。</span><span class="sxs-lookup"><span data-stu-id="b5ecf-105">Contains an embedded contents table object that provides information about a container.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b5ecf-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b5ecf-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b5ecf-107">PR_CONTAINER_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="b5ecf-107">PR_CONTAINER_CONTENTS</span></span>  <br/> |
|<span data-ttu-id="b5ecf-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="b5ecf-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b5ecf-109">0x360F</span><span class="sxs-lookup"><span data-stu-id="b5ecf-109">0x360F</span></span>  <br/> |
|<span data-ttu-id="b5ecf-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b5ecf-110">Data type:</span></span>  <br/> |<span data-ttu-id="b5ecf-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="b5ecf-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="b5ecf-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b5ecf-112">Area:</span></span>  <br/> |<span data-ttu-id="b5ecf-113">容器</span><span class="sxs-lookup"><span data-stu-id="b5ecf-113">Container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b5ecf-114">备注</span><span class="sxs-lookup"><span data-stu-id="b5ecf-114">Remarks</span></span>

<span data-ttu-id="b5ecf-115">此属性可以在 [IMAPIProp：：CopyTo](imapiprop-copyto.md) 操作中排除，也可以包含在 [IMAPIProp：：CopyProps 操作](imapiprop-copyprops.md) 中。</span><span class="sxs-lookup"><span data-stu-id="b5ecf-115">This property can be excluded in [IMAPIProp::CopyTo](imapiprop-copyto.md) operations or included in [IMAPIProp::CopyProps](imapiprop-copyprops.md) operations.</span></span> <span data-ttu-id="b5ecf-116">作为类型为 [PT_OBJECT，IMAPIProp：：GetProps](imapiprop-getprops.md) 方法无法成功检索它;它的内容应该由 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法访问，并请求IID_IMAPITable标识符。</span><span class="sxs-lookup"><span data-stu-id="b5ecf-116">As a property of type PT_OBJECT, it cannot be successfully retrieved by the [IMAPIProp::GetProps](imapiprop-getprops.md) method; its contents should be accessed by the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method, requesting the IID_IMAPITable interface identifier.</span></span> <span data-ttu-id="b5ecf-117">如果已设置，服务提供商必须报告给 [IMAPIProp：：GetPropList](imapiprop-getproplist.md) 方法，但可以选择是否报告（如果未设置）。</span><span class="sxs-lookup"><span data-stu-id="b5ecf-117">Service providers must report it to the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method if it is set, but can optionally report it or not if it is not set.</span></span> 
  
<span data-ttu-id="b5ecf-118">若要检索表内容，客户端应用程序应调用 [IMAPIContainer：：GetContentsTable](imapicontainer-getcontentstable.md) 方法。</span><span class="sxs-lookup"><span data-stu-id="b5ecf-118">To retrieve table contents, a client application should call the [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) method.</span></span> <span data-ttu-id="b5ecf-119">有关详细信息，请参阅[内容表](contents-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="b5ecf-119">For more information, see [Contents Tables](contents-tables.md).</span></span> 
  
<span data-ttu-id="b5ecf-120">此属性PR_CONTAINER_HIERARCHY ( [PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 和 **PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) 用法相似。</span><span class="sxs-lookup"><span data-stu-id="b5ecf-120">This property, **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) , and **PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) are similar in usage.</span></span> <span data-ttu-id="b5ecf-121">多个 MAPI 属性提供对表的访问权限：</span><span class="sxs-lookup"><span data-stu-id="b5ecf-121">Several MAPI properties provide access to tables:</span></span> 
  
|<span data-ttu-id="b5ecf-122">**Property**</span><span class="sxs-lookup"><span data-stu-id="b5ecf-122">**Property**</span></span>|<span data-ttu-id="b5ecf-123">**Table**</span><span class="sxs-lookup"><span data-stu-id="b5ecf-123">**Table**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b5ecf-124">PidTagContainerContents</span><span class="sxs-lookup"><span data-stu-id="b5ecf-124">PidTagContainerContents</span></span>  <br/> |<span data-ttu-id="b5ecf-125">Contents 表</span><span class="sxs-lookup"><span data-stu-id="b5ecf-125">Contents table</span></span>  <br/> |
|<span data-ttu-id="b5ecf-126">**PR_CONTAINER_HIERARCHY (** [PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="b5ecf-126">**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b5ecf-127">层次结构表</span><span class="sxs-lookup"><span data-stu-id="b5ecf-127">Hierarchy table</span></span>  <br/> |
|<span data-ttu-id="b5ecf-128">**PR_FOLDER_ASSOCIATED_CONTENTS (** [PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) </span><span class="sxs-lookup"><span data-stu-id="b5ecf-128">**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b5ecf-129">关联内容表</span><span class="sxs-lookup"><span data-stu-id="b5ecf-129">Associated contents table</span></span>  <br/> |
|<span data-ttu-id="b5ecf-130">**PR_MESSAGE_ATTACHMENTS (** [PidTagMessageAttachments)](pidtagmessageattachments-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="b5ecf-130">**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b5ecf-131">Attachment 表</span><span class="sxs-lookup"><span data-stu-id="b5ecf-131">Attachment table</span></span>  <br/> |
|<span data-ttu-id="b5ecf-132">**PR_MESSAGE_RECIPIENTS (** [PidTagMessageRecipients)](pidtagmessagerecipients-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="b5ecf-132">**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="b5ecf-133">收件人表</span><span class="sxs-lookup"><span data-stu-id="b5ecf-133">Recipient table</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="b5ecf-134">相关资源</span><span class="sxs-lookup"><span data-stu-id="b5ecf-134">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b5ecf-135">协议规范</span><span class="sxs-lookup"><span data-stu-id="b5ecf-135">Protocol specifications</span></span>

<span data-ttu-id="b5ecf-136">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b5ecf-136">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b5ecf-137">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="b5ecf-137">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b5ecf-138">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b5ecf-138">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b5ecf-139">指定用户、联系人、组和资源的列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="b5ecf-139">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b5ecf-140">头文件</span><span class="sxs-lookup"><span data-stu-id="b5ecf-140">Header files</span></span>

<span data-ttu-id="b5ecf-141">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b5ecf-141">Mapidefs.h</span></span>
  
> <span data-ttu-id="b5ecf-142">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b5ecf-142">Provides data type definitions.</span></span>
    
<span data-ttu-id="b5ecf-143">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="b5ecf-143">Mapitags.h</span></span>
  
> <span data-ttu-id="b5ecf-144">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b5ecf-144">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b5ecf-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b5ecf-145">See also</span></span>



[<span data-ttu-id="b5ecf-146">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b5ecf-146">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b5ecf-147">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b5ecf-147">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b5ecf-148">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b5ecf-148">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b5ecf-149">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b5ecf-149">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

