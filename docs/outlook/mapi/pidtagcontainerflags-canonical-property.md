---
title: PidTagContainerFlags 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagContainerFlags
api_type:
- HeaderDef
ms.assetid: 66b8d333-227e-464d-8cf9-cd8a5ff15efb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c9c446097213e5b743a47ec32db17ec0afe63b78
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357545"
---
# <a name="pidtagcontainerflags-canonical-property"></a><span data-ttu-id="8acb3-103">PidTagContainerFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="8acb3-103">PidTagContainerFlags Canonical Property</span></span>

  
  
<span data-ttu-id="8acb3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8acb3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8acb3-105">包含描述通讯簿容器的功能的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="8acb3-105">Contains a bitmask of flags describing capabilities of an address book container.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8acb3-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="8acb3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="8acb3-107">PR_CONTAINER_FLAGS</span><span class="sxs-lookup"><span data-stu-id="8acb3-107">PR_CONTAINER_FLAGS</span></span>  <br/> |
|<span data-ttu-id="8acb3-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="8acb3-108">Identifier:</span></span>  <br/> |<span data-ttu-id="8acb3-109">0x3600</span><span class="sxs-lookup"><span data-stu-id="8acb3-109">0x3600</span></span>  <br/> |
|<span data-ttu-id="8acb3-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="8acb3-110">Data type:</span></span>  <br/> |<span data-ttu-id="8acb3-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="8acb3-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="8acb3-112">区域：</span><span class="sxs-lookup"><span data-stu-id="8acb3-112">Area:</span></span>  <br/> |<span data-ttu-id="8acb3-113">通讯簿</span><span class="sxs-lookup"><span data-stu-id="8acb3-113">Address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8acb3-114">注解</span><span class="sxs-lookup"><span data-stu-id="8acb3-114">Remarks</span></span>

<span data-ttu-id="8acb3-115">可以为位掩码设置以下一个或多个标志:</span><span class="sxs-lookup"><span data-stu-id="8acb3-115">One or more of the following flags can be set for the bitmask:</span></span>
  
<span data-ttu-id="8acb3-116">AB_FIND_ON_OPEN</span><span class="sxs-lookup"><span data-stu-id="8acb3-116">AB_FIND_ON_OPEN</span></span> 
  
> <span data-ttu-id="8acb3-117">显示一个对话框, 以便在显示容器的任何内容之前请求限制。</span><span class="sxs-lookup"><span data-stu-id="8acb3-117">Displays a dialog box to request a restriction before displaying any contents of the container.</span></span> 
    
<span data-ttu-id="8acb3-118">AB_MODIFIABLE</span><span class="sxs-lookup"><span data-stu-id="8acb3-118">AB_MODIFIABLE</span></span> 
  
> <span data-ttu-id="8acb3-119">可以在容器中添加和删除条目。</span><span class="sxs-lookup"><span data-stu-id="8acb3-119">Entries can be added to and removed from the container.</span></span> <span data-ttu-id="8acb3-120">此标志并不指示是否可以修改容器中的任何条目。</span><span class="sxs-lookup"><span data-stu-id="8acb3-120">This flag does not indicate whether any entries in the container can be modified.</span></span>
    
<span data-ttu-id="8acb3-121">AB_RECIPIENTS</span><span class="sxs-lookup"><span data-stu-id="8acb3-121">AB_RECIPIENTS</span></span> 
  
> <span data-ttu-id="8acb3-122">容器可以保留收件人。</span><span class="sxs-lookup"><span data-stu-id="8acb3-122">The container can hold recipients.</span></span> <span data-ttu-id="8acb3-123">此标志并不指示是否有任何收件人实际存在于容器中, 或者是否可以添加或删除它们。</span><span class="sxs-lookup"><span data-stu-id="8acb3-123">This flag does not indicate whether any recipients are actually present in the container, or whether they can be added or removed.</span></span> 
    
<span data-ttu-id="8acb3-124">AB_SUBCONTAINERS</span><span class="sxs-lookup"><span data-stu-id="8acb3-124">AB_SUBCONTAINERS</span></span> 
  
> <span data-ttu-id="8acb3-125">容器可以包含子容器。</span><span class="sxs-lookup"><span data-stu-id="8acb3-125">The container can hold child containers.</span></span> <span data-ttu-id="8acb3-126">此标志不指示是否有任何子容器实际存在于容器中, 以及是否可以添加或删除它们。</span><span class="sxs-lookup"><span data-stu-id="8acb3-126">This flag does not indicate whether any subcontainers are actually present in the container, nor whether they can be added or removed.</span></span> <span data-ttu-id="8acb3-127">若要支持[IMAPIContainer:: GetHierarchyTable](imapicontainer-gethierarchytable.md), 容器必须设置 AB_SUBCONTAINERS。</span><span class="sxs-lookup"><span data-stu-id="8acb3-127">AB_SUBCONTAINERS must be set for the container to support [IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md).</span></span> 
    
<span data-ttu-id="8acb3-128">AB_UNMODIFIABLE</span><span class="sxs-lookup"><span data-stu-id="8acb3-128">AB_UNMODIFIABLE</span></span> 
  
> <span data-ttu-id="8acb3-129">无法在容器中添加或删除条目。</span><span class="sxs-lookup"><span data-stu-id="8acb3-129">Entries cannot be added to or removed from the container.</span></span> <span data-ttu-id="8acb3-130">此标志并不指示是否可以修改容器中的任何条目。</span><span class="sxs-lookup"><span data-stu-id="8acb3-130">This flag does not indicate whether any entries in the container can be modified.</span></span> 
    
<span data-ttu-id="8acb3-131">对于用于联机服务或与服务器的连接速度较慢的容器, 强烈建议使用 AB_FIND_ON_OPEN 标志。</span><span class="sxs-lookup"><span data-stu-id="8acb3-131">The AB_FIND_ON_OPEN flag is highly recommended for containers used with online services or with slow connections to servers.</span></span> <span data-ttu-id="8acb3-132">在打开具有 AB_FIND_ON_OPEN 集的容器时, 会向用户显示 "**查找**" 对话框, 以限制显示的邮件用户。</span><span class="sxs-lookup"><span data-stu-id="8acb3-132">When a container is opened that has AB_FIND_ON_OPEN set, a **Find** dialog box is presented to the user to restrict the displayed messaging users.</span></span> <span data-ttu-id="8acb3-133">即使限制邮件用户的部分规范, 也可以显著加快内容的显示速度。</span><span class="sxs-lookup"><span data-stu-id="8acb3-133">Even a partial specification limiting the messaging users can dramatically speed up a display of the contents.</span></span> 
  
<span data-ttu-id="8acb3-134">必须设置 AB_MODIFIABLE 或 AB_UNMODIFIABLE 标志。</span><span class="sxs-lookup"><span data-stu-id="8acb3-134">Either the AB_MODIFIABLE or AB_UNMODIFIABLE flag must be set.</span></span> <span data-ttu-id="8acb3-135">可以设置这两个标志, 以指示容器不知道它是否可以修改, 例如, 如果修改取决于用户的访问权限。</span><span class="sxs-lookup"><span data-stu-id="8acb3-135">Both flags can be set to indicate that the container does not know whether it can be modified or not, for example if modification depends on the user's access rights.</span></span> <span data-ttu-id="8acb3-136">在这种情况下, 客户端应用程序必须尝试调用并检查返回代码, 以确定容器的功能。</span><span class="sxs-lookup"><span data-stu-id="8acb3-136">In this case, a client application must attempt a call and examine the return code to determine the container's capabilities.</span></span> <span data-ttu-id="8acb3-137">客户端通常首先检查 AB_MODIFIABLE。</span><span class="sxs-lookup"><span data-stu-id="8acb3-137">A client typically starts by examining AB_MODIFIABLE.</span></span> <span data-ttu-id="8acb3-138">如果设置了此设置, 则客户端会发出尝试修改容器并检查返回值的调用。</span><span class="sxs-lookup"><span data-stu-id="8acb3-138">If it is set, the client makes a call that attempts to modify the container and checks the return value.</span></span> 
  
<span data-ttu-id="8acb3-139">AB_MODIFIABLE 标志并不指示可以向容器中添加哪些类型的条目。</span><span class="sxs-lookup"><span data-stu-id="8acb3-139">The AB_MODIFIABLE flag does not indicate what types of entries can be added to the container.</span></span> <span data-ttu-id="8acb3-140">若要确定这一点, 客户端应使用相应的[OpenProperty](imapiprop-openproperty.md)方法打开容器的**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="8acb3-140">To determine this, the client should use the appropriate [OpenProperty](imapiprop-openproperty.md) method to open the container's **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) property.</span></span> <span data-ttu-id="8acb3-141">打开**PR_CREATE_TEMPLATES**会导致容器的一次性表, 列出可在容器中创建的条目的类型。</span><span class="sxs-lookup"><span data-stu-id="8acb3-141">Opening **PR_CREATE_TEMPLATES** causes the container's one-off table to be returned, listing the kinds of entries that can be created in the container.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="8acb3-142">相关资源</span><span class="sxs-lookup"><span data-stu-id="8acb3-142">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="8acb3-143">协议规范</span><span class="sxs-lookup"><span data-stu-id="8acb3-143">Protocol specifications</span></span>

<span data-ttu-id="8acb3-144">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8acb3-144">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8acb3-145">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="8acb3-145">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="8acb3-146">[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8acb3-146">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8acb3-147">指定用户、联系人、组和资源列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="8acb3-147">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
<span data-ttu-id="8acb3-148">[[毫秒-NSPI]](https://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="8acb3-148">[[MS-NSPI]](https://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="8acb3-149">处理客户端与名称服务提供程序接口 (NSPI) 服务器的通信。</span><span class="sxs-lookup"><span data-stu-id="8acb3-149">Handles a client's communications with a Name Service Provider Interface (NSPI) server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="8acb3-150">头文件</span><span class="sxs-lookup"><span data-stu-id="8acb3-150">Header files</span></span>

<span data-ttu-id="8acb3-151">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="8acb3-151">Mapidefs.h</span></span>
  
> <span data-ttu-id="8acb3-152">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="8acb3-152">Provides data type definitions.</span></span>
    
<span data-ttu-id="8acb3-153">Mapitags</span><span class="sxs-lookup"><span data-stu-id="8acb3-153">Mapitags.h</span></span>
  
> <span data-ttu-id="8acb3-154">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="8acb3-154">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8acb3-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8acb3-155">See also</span></span>



[<span data-ttu-id="8acb3-156">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="8acb3-156">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="8acb3-157">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="8acb3-157">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="8acb3-158">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="8acb3-158">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="8acb3-159">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="8acb3-159">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

