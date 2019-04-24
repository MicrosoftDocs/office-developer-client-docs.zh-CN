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
# <a name="pidtagcontainercontents-canonical-property"></a><span data-ttu-id="5ac57-103">PidTagContainerContents 规范属性</span><span class="sxs-lookup"><span data-stu-id="5ac57-103">PidTagContainerContents Canonical Property</span></span>

  
  
<span data-ttu-id="5ac57-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="5ac57-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="5ac57-105">包含一个提供有关容器信息的嵌入的内容表对象。</span><span class="sxs-lookup"><span data-stu-id="5ac57-105">Contains an embedded contents table object that provides information about a container.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="5ac57-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5ac57-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5ac57-107">PR_CONTAINER_CONTENTS</span><span class="sxs-lookup"><span data-stu-id="5ac57-107">PR_CONTAINER_CONTENTS</span></span>  <br/> |
|<span data-ttu-id="5ac57-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="5ac57-108">Identifier:</span></span>  <br/> |<span data-ttu-id="5ac57-109">0x360F</span><span class="sxs-lookup"><span data-stu-id="5ac57-109">0x360F</span></span>  <br/> |
|<span data-ttu-id="5ac57-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5ac57-110">Data type:</span></span>  <br/> |<span data-ttu-id="5ac57-111">PT_OBJECT</span><span class="sxs-lookup"><span data-stu-id="5ac57-111">PT_OBJECT</span></span>  <br/> |
|<span data-ttu-id="5ac57-112">区域：</span><span class="sxs-lookup"><span data-stu-id="5ac57-112">Area:</span></span>  <br/> |<span data-ttu-id="5ac57-113">Container</span><span class="sxs-lookup"><span data-stu-id="5ac57-113">Container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5ac57-114">注解</span><span class="sxs-lookup"><span data-stu-id="5ac57-114">Remarks</span></span>

<span data-ttu-id="5ac57-115">此属性可以排除在[IMAPIProp:: CopyTo](imapiprop-copyto.md)操作中, 也可以包含在[IMAPIProp:: CopyProps](imapiprop-copyprops.md)操作中。</span><span class="sxs-lookup"><span data-stu-id="5ac57-115">This property can be excluded in [IMAPIProp::CopyTo](imapiprop-copyto.md) operations or included in [IMAPIProp::CopyProps](imapiprop-copyprops.md) operations.</span></span> <span data-ttu-id="5ac57-116">作为 PT_OBJECT 类型的属性, [IMAPIProp:: GetProps](imapiprop-getprops.md)方法无法成功检索它;其内容应由[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法访问, 请求 IID_IMAPITable 接口标识符。</span><span class="sxs-lookup"><span data-stu-id="5ac57-116">As a property of type PT_OBJECT, it cannot be successfully retrieved by the [IMAPIProp::GetProps](imapiprop-getprops.md) method; its contents should be accessed by the [IMAPIProp::OpenProperty](imapiprop-openproperty.md) method, requesting the IID_IMAPITable interface identifier.</span></span> <span data-ttu-id="5ac57-117">如果设置了服务提供程序, 则必须将其报告给[IMAPIProp:: GetPropList](imapiprop-getproplist.md)方法, 但如果未设置, 则可以选择报告它。</span><span class="sxs-lookup"><span data-stu-id="5ac57-117">Service providers must report it to the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method if it is set, but can optionally report it or not if it is not set.</span></span> 
  
<span data-ttu-id="5ac57-118">若要检索表内容, 客户端应用程序应调用[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)方法。</span><span class="sxs-lookup"><span data-stu-id="5ac57-118">To retrieve table contents, a client application should call the [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) method.</span></span> <span data-ttu-id="5ac57-119">有关详细信息，请参阅[内容表](contents-tables.md)。</span><span class="sxs-lookup"><span data-stu-id="5ac57-119">For more information, see [Contents Tables](contents-tables.md).</span></span> 
  
<span data-ttu-id="5ac57-120">此属性、 **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 和**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) 在使用中相似。</span><span class="sxs-lookup"><span data-stu-id="5ac57-120">This property, **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) , and **PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) are similar in usage.</span></span> <span data-ttu-id="5ac57-121">有几个 MAPI 属性提供对表的访问权限:</span><span class="sxs-lookup"><span data-stu-id="5ac57-121">Several MAPI properties provide access to tables:</span></span> 
  
|<span data-ttu-id="5ac57-122">**Property**</span><span class="sxs-lookup"><span data-stu-id="5ac57-122">**Property**</span></span>|<span data-ttu-id="5ac57-123">**Table**</span><span class="sxs-lookup"><span data-stu-id="5ac57-123">**Table**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5ac57-124">PidTagContainerContents</span><span class="sxs-lookup"><span data-stu-id="5ac57-124">PidTagContainerContents</span></span>  <br/> |<span data-ttu-id="5ac57-125">内容表</span><span class="sxs-lookup"><span data-stu-id="5ac57-125">Contents table</span></span>  <br/> |
|<span data-ttu-id="5ac57-126">**PR_CONTAINER_HIERARCHY**([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="5ac57-126">**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="5ac57-127">层次结构表</span><span class="sxs-lookup"><span data-stu-id="5ac57-127">Hierarchy table</span></span>  <br/> |
|<span data-ttu-id="5ac57-128">**PR_FOLDER_ASSOCIATED_CONTENTS**([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="5ac57-128">**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="5ac57-129">关联的内容表</span><span class="sxs-lookup"><span data-stu-id="5ac57-129">Associated contents table</span></span>  <br/> |
|<span data-ttu-id="5ac57-130">**PR_MESSAGE_ATTACHMENTS**([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="5ac57-130">**PR_MESSAGE_ATTACHMENTS** ([PidTagMessageAttachments](pidtagmessageattachments-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="5ac57-131">附件表</span><span class="sxs-lookup"><span data-stu-id="5ac57-131">Attachment table</span></span>  <br/> |
|<span data-ttu-id="5ac57-132">**PR_MESSAGE_RECIPIENTS**([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="5ac57-132">**PR_MESSAGE_RECIPIENTS** ([PidTagMessageRecipients](pidtagmessagerecipients-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="5ac57-133">收件人表</span><span class="sxs-lookup"><span data-stu-id="5ac57-133">Recipient table</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="5ac57-134">相关资源</span><span class="sxs-lookup"><span data-stu-id="5ac57-134">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5ac57-135">协议规范</span><span class="sxs-lookup"><span data-stu-id="5ac57-135">Protocol specifications</span></span>

<span data-ttu-id="5ac57-136">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5ac57-136">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5ac57-137">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="5ac57-137">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="5ac57-138">[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5ac57-138">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5ac57-139">指定用户、联系人、组和资源列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="5ac57-139">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5ac57-140">头文件</span><span class="sxs-lookup"><span data-stu-id="5ac57-140">Header files</span></span>

<span data-ttu-id="5ac57-141">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="5ac57-141">Mapidefs.h</span></span>
  
> <span data-ttu-id="5ac57-142">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5ac57-142">Provides data type definitions.</span></span>
    
<span data-ttu-id="5ac57-143">Mapitags</span><span class="sxs-lookup"><span data-stu-id="5ac57-143">Mapitags.h</span></span>
  
> <span data-ttu-id="5ac57-144">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="5ac57-144">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5ac57-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5ac57-145">See also</span></span>



[<span data-ttu-id="5ac57-146">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5ac57-146">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5ac57-147">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5ac57-147">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5ac57-148">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5ac57-148">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5ac57-149">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5ac57-149">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

