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
# <a name="pidtagcontainerflags-canonical-property"></a><span data-ttu-id="0b4e6-103">PidTagContainerFlags 规范属性</span><span class="sxs-lookup"><span data-stu-id="0b4e6-103">PidTagContainerFlags Canonical Property</span></span>

  
  
<span data-ttu-id="0b4e6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0b4e6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0b4e6-105">包含描述通讯簿容器功能的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-105">Contains a bitmask of flags describing capabilities of an address book container.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0b4e6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0b4e6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0b4e6-107">PR_CONTAINER_FLAGS</span><span class="sxs-lookup"><span data-stu-id="0b4e6-107">PR_CONTAINER_FLAGS</span></span>  <br/> |
|<span data-ttu-id="0b4e6-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="0b4e6-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0b4e6-109">0x3600</span><span class="sxs-lookup"><span data-stu-id="0b4e6-109">0x3600</span></span>  <br/> |
|<span data-ttu-id="0b4e6-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0b4e6-110">Data type:</span></span>  <br/> |<span data-ttu-id="0b4e6-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="0b4e6-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="0b4e6-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0b4e6-112">Area:</span></span>  <br/> |<span data-ttu-id="0b4e6-113">通讯簿</span><span class="sxs-lookup"><span data-stu-id="0b4e6-113">Address book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0b4e6-114">备注</span><span class="sxs-lookup"><span data-stu-id="0b4e6-114">Remarks</span></span>

<span data-ttu-id="0b4e6-115">可以为位掩码设置以下一个或多个标志：</span><span class="sxs-lookup"><span data-stu-id="0b4e6-115">One or more of the following flags can be set for the bitmask:</span></span>
  
<span data-ttu-id="0b4e6-116">AB_FIND_ON_OPEN</span><span class="sxs-lookup"><span data-stu-id="0b4e6-116">AB_FIND_ON_OPEN</span></span> 
  
> <span data-ttu-id="0b4e6-117">显示一个对话框，在显示容器的任何内容之前请求限制。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-117">Displays a dialog box to request a restriction before displaying any contents of the container.</span></span> 
    
<span data-ttu-id="0b4e6-118">AB_MODIFIABLE</span><span class="sxs-lookup"><span data-stu-id="0b4e6-118">AB_MODIFIABLE</span></span> 
  
> <span data-ttu-id="0b4e6-119">条目可以添加到容器中，也可以从容器中删除。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-119">Entries can be added to and removed from the container.</span></span> <span data-ttu-id="0b4e6-120">此标志不指示是否可以修改容器中的任何条目。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-120">This flag does not indicate whether any entries in the container can be modified.</span></span>
    
<span data-ttu-id="0b4e6-121">AB_RECIPIENTS</span><span class="sxs-lookup"><span data-stu-id="0b4e6-121">AB_RECIPIENTS</span></span> 
  
> <span data-ttu-id="0b4e6-122">容器可以保留收件人。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-122">The container can hold recipients.</span></span> <span data-ttu-id="0b4e6-123">此标志不指示容器中是否实际存在任何收件人，或者是否可以添加或删除这些收件人。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-123">This flag does not indicate whether any recipients are actually present in the container, or whether they can be added or removed.</span></span> 
    
<span data-ttu-id="0b4e6-124">AB_SUBCONTAINERS</span><span class="sxs-lookup"><span data-stu-id="0b4e6-124">AB_SUBCONTAINERS</span></span> 
  
> <span data-ttu-id="0b4e6-125">容器可以容纳子容器。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-125">The container can hold child containers.</span></span> <span data-ttu-id="0b4e6-126">此标志不指示容器中是否实际存在任何子容器，也不指示是否可以添加或删除它们。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-126">This flag does not indicate whether any subcontainers are actually present in the container, nor whether they can be added or removed.</span></span> <span data-ttu-id="0b4e6-127">AB_SUBCONTAINERS必须设置为容器以支持 [IMAPIContainer：：GetHierarchyTable](imapicontainer-gethierarchytable.md)。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-127">AB_SUBCONTAINERS must be set for the container to support [IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md).</span></span> 
    
<span data-ttu-id="0b4e6-128">AB_UNMODIFIABLE</span><span class="sxs-lookup"><span data-stu-id="0b4e6-128">AB_UNMODIFIABLE</span></span> 
  
> <span data-ttu-id="0b4e6-129">条目不能添加到容器中或无法从容器中删除。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-129">Entries cannot be added to or removed from the container.</span></span> <span data-ttu-id="0b4e6-130">此标志不指示是否可以修改容器中的任何条目。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-130">This flag does not indicate whether any entries in the container can be modified.</span></span> 
    
<span data-ttu-id="0b4e6-131">强烈建议AB_FIND_ON_OPEN联机服务或与服务器连接缓慢的容器使用此标志。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-131">The AB_FIND_ON_OPEN flag is highly recommended for containers used with online services or with slow connections to servers.</span></span> <span data-ttu-id="0b4e6-132">打开已设置AB_FIND_ON_OPEN容器时，会向用户显示"查找"对话框以限制显示的消息用户。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-132">When a container is opened that has AB_FIND_ON_OPEN set, a **Find** dialog box is presented to the user to restrict the displayed messaging users.</span></span> <span data-ttu-id="0b4e6-133">即使部分规范限制邮件用户，也可以极大地加快内容的显示速度。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-133">Even a partial specification limiting the messaging users can dramatically speed up a display of the contents.</span></span> 
  
<span data-ttu-id="0b4e6-134">必须AB_MODIFIABLE或AB_UNMODIFIABLE标记。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-134">Either the AB_MODIFIABLE or AB_UNMODIFIABLE flag must be set.</span></span> <span data-ttu-id="0b4e6-135">可以设置这两个标志以指示容器不知道是否可以修改它，例如，如果修改取决于用户的访问权。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-135">Both flags can be set to indicate that the container does not know whether it can be modified or not, for example if modification depends on the user's access rights.</span></span> <span data-ttu-id="0b4e6-136">在这种情况下，客户端应用程序必须尝试调用并检查返回代码以确定容器的功能。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-136">In this case, a client application must attempt a call and examine the return code to determine the container's capabilities.</span></span> <span data-ttu-id="0b4e6-137">客户端通常首先检查AB_MODIFIABLE。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-137">A client typically starts by examining AB_MODIFIABLE.</span></span> <span data-ttu-id="0b4e6-138">如果已设置，客户端将进行调用，尝试修改容器并检查返回值。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-138">If it is set, the client makes a call that attempts to modify the container and checks the return value.</span></span> 
  
<span data-ttu-id="0b4e6-139">the AB_MODIFIABLE flag does not indicate what types of entries can be added to the container.</span><span class="sxs-lookup"><span data-stu-id="0b4e6-139">The AB_MODIFIABLE flag does not indicate what types of entries can be added to the container.</span></span> <span data-ttu-id="0b4e6-140">若要确定这一点，客户端应该使用适当的[OpenProperty](imapiprop-openproperty.md)方法打开容器的PR_CREATE_TEMPLATES ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-140">To determine this, the client should use the appropriate [OpenProperty](imapiprop-openproperty.md) method to open the container's **PR_CREATE_TEMPLATES** ([PidTagCreateTemplates](pidtagcreatetemplates-canonical-property.md)) property.</span></span> <span data-ttu-id="0b4e6-141">打开 **PR_CREATE_TEMPLATES** 会导致返回容器的一次表，其中列出了可在容器中创建的条目类型。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-141">Opening **PR_CREATE_TEMPLATES** causes the container's one-off table to be returned, listing the kinds of entries that can be created in the container.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="0b4e6-142">相关资源</span><span class="sxs-lookup"><span data-stu-id="0b4e6-142">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0b4e6-143">协议规范</span><span class="sxs-lookup"><span data-stu-id="0b4e6-143">Protocol specifications</span></span>

<span data-ttu-id="0b4e6-144">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0b4e6-144">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0b4e6-145">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-145">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="0b4e6-146">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0b4e6-146">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0b4e6-147">指定用户、联系人、组和资源的列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-147">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
<span data-ttu-id="0b4e6-148">[[MS-NSPI]](https://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0b4e6-148">[[MS-NSPI]](https://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0b4e6-149">处理客户端与 NSPI 服务器的名称服务提供程序 (的通信) 。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-149">Handles a client's communications with a Name Service Provider Interface (NSPI) server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0b4e6-150">头文件</span><span class="sxs-lookup"><span data-stu-id="0b4e6-150">Header files</span></span>

<span data-ttu-id="0b4e6-151">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0b4e6-151">Mapidefs.h</span></span>
  
> <span data-ttu-id="0b4e6-152">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-152">Provides data type definitions.</span></span>
    
<span data-ttu-id="0b4e6-153">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="0b4e6-153">Mapitags.h</span></span>
  
> <span data-ttu-id="0b4e6-154">包含作为关联属性列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0b4e6-154">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0b4e6-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0b4e6-155">See also</span></span>



[<span data-ttu-id="0b4e6-156">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0b4e6-156">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0b4e6-157">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0b4e6-157">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0b4e6-158">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0b4e6-158">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0b4e6-159">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0b4e6-159">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

