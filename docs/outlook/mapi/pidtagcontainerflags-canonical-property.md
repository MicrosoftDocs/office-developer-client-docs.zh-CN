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
ms.openlocfilehash: c13acd1c3b759602a5fbe07c21ca8b784e0fe4d1
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777461"
---
# <a name="pidtagcontainerflags-canonical-property"></a><span data-ttu-id="7e5fe-103">PidTagContainerFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="7e5fe-103">PidTagContainerFlags Canonical Property</span></span>

  
  
<span data-ttu-id="7e5fe-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7e5fe-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7e5fe-105">包含描述的通讯簿容器功能标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-105">Contains a bitmask of flags describing capabilities of an address book container.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="7e5fe-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7e5fe-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7e5fe-107">PR_CONTAINER_FLAGS</span><span class="sxs-lookup"><span data-stu-id="7e5fe-107">PR_CONTAINER_FLAGS</span></span>  <br/> |
|<span data-ttu-id="7e5fe-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="7e5fe-108">Identifier:</span></span>  <br/> |<span data-ttu-id="7e5fe-109">0x3600</span><span class="sxs-lookup"><span data-stu-id="7e5fe-109">0x3600</span></span>  <br/> |
|<span data-ttu-id="7e5fe-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7e5fe-110">Data type:</span></span>  <br/> |<span data-ttu-id="7e5fe-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="7e5fe-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="7e5fe-112">区域：</span><span class="sxs-lookup"><span data-stu-id="7e5fe-112">Area:</span></span>  <br/> |<span data-ttu-id="7e5fe-113">通讯簿</span><span class="sxs-lookup"><span data-stu-id="7e5fe-113">Address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7e5fe-114">说明</span><span class="sxs-lookup"><span data-stu-id="7e5fe-114">Remarks</span></span>

<span data-ttu-id="7e5fe-115">可以为位掩码设置一个或多个以下标志：</span><span class="sxs-lookup"><span data-stu-id="7e5fe-115">One or more of the following flags can be set for the bitmask:</span></span>
  
<span data-ttu-id="7e5fe-116">AB_FIND_ON_OPEN</span><span class="sxs-lookup"><span data-stu-id="7e5fe-116">AB_FIND_ON_OPEN</span></span> 
  
> <span data-ttu-id="7e5fe-117">显示一个对话框，以请求之前显示容器的任何内容的限制。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-117">Displays a dialog box to request a restriction before displaying any contents of the container.</span></span> 
    
<span data-ttu-id="7e5fe-118">AB_MODIFIABLE</span><span class="sxs-lookup"><span data-stu-id="7e5fe-118">AB_MODIFIABLE</span></span> 
  
> <span data-ttu-id="7e5fe-119">可以添加到并从容器中删除条目。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-119">Entries can be added to and removed from the container.</span></span> <span data-ttu-id="7e5fe-120">此标志不指示是否可以修改任何容器中的条目。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-120">This flag does not indicate whether any entries in the container can be modified.</span></span>
    
<span data-ttu-id="7e5fe-121">AB_RECIPIENTS</span><span class="sxs-lookup"><span data-stu-id="7e5fe-121">AB_RECIPIENTS</span></span> 
  
> <span data-ttu-id="7e5fe-122">容器可以包含收件人。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-122">The container can hold recipients.</span></span> <span data-ttu-id="7e5fe-123">此标志并不表示任何收件人是否确实存在的容器中，或者可以是否添加或删除它们。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-123">This flag does not indicate whether any recipients are actually present in the container, or whether they can be added or removed.</span></span> 
    
<span data-ttu-id="7e5fe-124">AB_SUBCONTAINERS</span><span class="sxs-lookup"><span data-stu-id="7e5fe-124">AB_SUBCONTAINERS</span></span> 
  
> <span data-ttu-id="7e5fe-125">容器可以包含子容器。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-125">The container can hold child containers.</span></span> <span data-ttu-id="7e5fe-126">此标志并不表示任何子容器是否确实存在的容器中，也可以是否添加或删除它们。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-126">This flag does not indicate whether any subcontainers are actually present in the container, nor whether they can be added or removed.</span></span> <span data-ttu-id="7e5fe-127">AB_SUBCONTAINERS 必须为要支持[IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md)的容器。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-127">AB_SUBCONTAINERS must be set for the container to support [IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md).</span></span> 
    
<span data-ttu-id="7e5fe-128">AB_UNMODIFIABLE</span><span class="sxs-lookup"><span data-stu-id="7e5fe-128">AB_UNMODIFIABLE</span></span> 
  
> <span data-ttu-id="7e5fe-129">无法添加到或从容器中删除条目。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-129">Entries cannot be added to or removed from the container.</span></span> <span data-ttu-id="7e5fe-130">此标志不指示是否可以修改任何容器中的条目。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-130">This flag does not indicate whether any entries in the container can be modified.</span></span> 
    
<span data-ttu-id="7e5fe-131">使用与在线服务或慢速连接到服务器的容器中的强烈建议 AB_FIND_ON_OPEN 标志。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-131">The AB_FIND_ON_OPEN flag is highly recommended for containers used with online services or with slow connections to servers.</span></span> <span data-ttu-id="7e5fe-132">容器打开已设置的 AB_FIND_ON_OPEN 时, 的**查找**对话框将显示向用户显示消息的用户限制。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-132">When a container is opened that has AB_FIND_ON_OPEN set, a **Find** dialog box is presented to the user to restrict the displayed messaging users.</span></span> <span data-ttu-id="7e5fe-133">即使部分规范限制的邮件的用户可以显著加快内容的显示。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-133">Even a partial specification limiting the messaging users can dramatically speed up a display of the contents.</span></span> 
  
<span data-ttu-id="7e5fe-134">必须设置 AB_MODIFIABLE 或 AB_UNMODIFIABLE 标志。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-134">Either the AB_MODIFIABLE or AB_UNMODIFIABLE flag must be set.</span></span> <span data-ttu-id="7e5fe-135">可以设置这两个标志以指示容器不知道是否可以进行修改，例如，如果修改取决于用户的访问权限。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-135">Both flags can be set to indicate that the container does not know whether it can be modified or not, for example if modification depends on the user's access rights.</span></span> <span data-ttu-id="7e5fe-136">在这种情况下，客户端应用程序必须尝试呼叫，并检查返回代码来确定容器的功能。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-136">In this case, a client application must attempt a call and examine the return code to determine the container's capabilities.</span></span> <span data-ttu-id="7e5fe-137">通过检查 AB_MODIFIABLE 通常启动客户端。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-137">A client typically starts by examining AB_MODIFIABLE.</span></span> <span data-ttu-id="7e5fe-138">如果设置，则客户端调用尝试修改容器并检查的返回值。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-138">If it is set, the client makes a call that attempts to modify the container and checks the return value.</span></span> 
  
<span data-ttu-id="7e5fe-139">AB_MODIFIABLE 标志并不表示哪些类型的条目可以添加到容器。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-139">The AB_MODIFIABLE flag does not indicate what types of entries can be added to the container.</span></span> <span data-ttu-id="7e5fe-140">若要确定这一点，客户端应使用相应的[OpenProperty](imapiprop-openproperty.md)方法打开容器的**PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-140">To determine this, the client should use the appropriate [OpenProperty](imapiprop-openproperty.md) method to open the container's **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) property.</span></span> <span data-ttu-id="7e5fe-141">打开**PR_CREATE_TEMPLATES**原因容器的一次性要返回的表列出可以容器中创建的项的类型。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-141">Opening **PR_CREATE_TEMPLATES** causes the container's one-off table to be returned, listing the kinds of entries that can be created in the container.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="7e5fe-142">相关资源</span><span class="sxs-lookup"><span data-stu-id="7e5fe-142">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7e5fe-143">协议规范</span><span class="sxs-lookup"><span data-stu-id="7e5fe-143">Protocol specifications</span></span>

<span data-ttu-id="7e5fe-144">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7e5fe-144">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7e5fe-145">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-145">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7e5fe-146">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7e5fe-146">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7e5fe-147">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-147">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
<span data-ttu-id="7e5fe-148">[[MS NSPI]](http://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7e5fe-148">[[MS-NSPI]](http://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7e5fe-149">处理与名称服务提供程序界面 (NSPI) 服务器的客户端的通信。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-149">Handles a client's communications with a Name Service Provider Interface (NSPI) server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7e5fe-150">头文件</span><span class="sxs-lookup"><span data-stu-id="7e5fe-150">Header files</span></span>

<span data-ttu-id="7e5fe-151">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7e5fe-151">Mapidefs.h</span></span>
  
> <span data-ttu-id="7e5fe-152">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-152">Provides data type definitions.</span></span>
    
<span data-ttu-id="7e5fe-153">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="7e5fe-153">Mapitags.h</span></span>
  
> <span data-ttu-id="7e5fe-154">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="7e5fe-154">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7e5fe-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7e5fe-155">See also</span></span>



[<span data-ttu-id="7e5fe-156">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7e5fe-156">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7e5fe-157">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7e5fe-157">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7e5fe-158">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7e5fe-158">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7e5fe-159">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7e5fe-159">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

