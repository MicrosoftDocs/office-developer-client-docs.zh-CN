---
title: PidTagAddressBookHierarchicalRootDepartment
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAddressBookHierarchicalRootDepartment
api_type:
- HeaderDef
ms.assetid: c611640b-1a70-4a76-b7ff-c8ad8d320892
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 49c9b0a80f9bc3b45dfafa6f4e037fe55af289d5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777352"
---
# <a name="pidtagaddressbookhierarchicalrootdepartment"></a><span data-ttu-id="5e146-103">PidTagAddressBookHierarchicalRootDepartment</span><span class="sxs-lookup"><span data-stu-id="5e146-103">PidTagAddressBookHierarchicalRootDepartment</span></span>

  
  
<span data-ttu-id="5e146-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="5e146-104">**Applies to**: Outlook</span></span> 
  
 <span data-ttu-id="5e146-105">包含分层通讯根 (HAB) 的可分辨的名称 (DN)。</span><span class="sxs-lookup"><span data-stu-id="5e146-105">Contains the distinguished name (DN) of the hierarchical address root (HAB).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="5e146-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="5e146-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="5e146-107">PR_EMS_AB_HAB_ROOT_DEPARTMENT PR_EMS_AB_HAB_ROOT_DEPARTMENT_A</span><span class="sxs-lookup"><span data-stu-id="5e146-107">PR_EMS_AB_HAB_ROOT_DEPARTMENT, PR_EMS_AB_HAB_ROOT_DEPARTMENT_A</span></span>  <br/> |
|<span data-ttu-id="5e146-108">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="5e146-108">Property set:</span></span>  <br/> |<span data-ttu-id="5e146-109">通讯簿</span><span class="sxs-lookup"><span data-stu-id="5e146-109">Address Book</span></span>  <br/> |
|<span data-ttu-id="5e146-110">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="5e146-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="5e146-111">0x8C98</span><span class="sxs-lookup"><span data-stu-id="5e146-111">0x8C98</span></span>  <br/> |
|<span data-ttu-id="5e146-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="5e146-112">Data type:</span></span>  <br/> |<span data-ttu-id="5e146-113">PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="5e146-113">PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="5e146-114">区域：</span><span class="sxs-lookup"><span data-stu-id="5e146-114">Area:</span></span>  <br/> |<span data-ttu-id="5e146-115">Exchange 通讯簿</span><span class="sxs-lookup"><span data-stu-id="5e146-115">Exchange Address Book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="5e146-116">说明</span><span class="sxs-lookup"><span data-stu-id="5e146-116">Remarks</span></span>

<span data-ttu-id="5e146-117">这是全局地址列表 (GAL) 容器的属性，并代表分层通讯根的可分辨的名称。</span><span class="sxs-lookup"><span data-stu-id="5e146-117">This is a property on the global address list (GAL) container and represents the distinguished name of the hierarchical address root.</span></span> <span data-ttu-id="5e146-118">此属性才存在脱机通讯簿中而不会在 Active Directory 域服务 (AD DS)。</span><span class="sxs-lookup"><span data-stu-id="5e146-118">This property is only present in the offline address book and never in Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="5e146-119">呼叫者应将 MAPI_CACHE_ONLY 传递给 GetProps 呼叫，以避免远程过程调用。</span><span class="sxs-lookup"><span data-stu-id="5e146-119">Callers should pass MAPI_CACHE_ONLY to the GetProps call to avoid a remote procedure call.</span></span> <span data-ttu-id="5e146-120">如果不存在，呼叫者应使用 PR_EMS_AB_HAB_ROOT_DEPARTMENT，其类型 PT_OBJECT 为，查找根部门。</span><span class="sxs-lookup"><span data-stu-id="5e146-120">If this is not present, callers should use PR_EMS_AB_HAB_ROOT_DEPARTMENT, which is of type PT_OBJECT, to find the root department.</span></span> 
  
<span data-ttu-id="5e146-121">根部门获得后，它可以具有 MAPI_MAILUSER 或 MAPI_DISTLIST 对象类型。</span><span class="sxs-lookup"><span data-stu-id="5e146-121">Once the root department is obtained, it can have an object type MAPI_MAILUSER or MAPI_DISTLIST.</span></span> <span data-ttu-id="5e146-122">如果对象类型，MAPI_DISTLIST 正在采用新的架构。</span><span class="sxs-lookup"><span data-stu-id="5e146-122">If the object type is MAPI_DISTLIST, the new schema is being employed.</span></span> <span data-ttu-id="5e146-123">对象类型是 MAPI_MAILUSER，如果要采用的以前的架构。</span><span class="sxs-lookup"><span data-stu-id="5e146-123">If the object type is MAPI_MAILUSER, the previous schema is being employed.</span></span> 
  
- <span data-ttu-id="5e146-124">Microsoft Office Outlook 2007 Service Pack 2 支持两个架构。</span><span class="sxs-lookup"><span data-stu-id="5e146-124">Microsoft Office Outlook 2007 Service Pack 2 supports both schemas.</span></span> 
    
- <span data-ttu-id="5e146-125">Microsoft Outlook 2010 和 Microsoft Outlook 2013 支持新的架构。</span><span class="sxs-lookup"><span data-stu-id="5e146-125">Microsoft Outlook 2010 and Microsoft Outlook 2013 support the new schema.</span></span>
    
<span data-ttu-id="5e146-126">在新的架构中，所有部门组还通讯组列表，以及为类型 MAPI_DISTLIST。</span><span class="sxs-lookup"><span data-stu-id="5e146-126">In the new schema, all departmental groups are also distribution lists and are of type MAPI_DISTLIST.</span></span> <span data-ttu-id="5e146-127">通过完全一样通讯组列表成员 PR_EMS_AB_MEMBER，获得是部门组和部门内部门组的成员。</span><span class="sxs-lookup"><span data-stu-id="5e146-127">Members of departmental groups, and departments within departmental groups are obtained by using PR_EMS_AB_MEMBER, exactly like distribution list members.</span></span>
  
<span data-ttu-id="5e146-128">根部门获得后，它可以具有 MAPI_MAILUSER 或 MAPI_DISTLIST 对象类型。</span><span class="sxs-lookup"><span data-stu-id="5e146-128">Once the root department is obtained, it can have an object type MAPI_MAILUSER or MAPI_DISTLIST.</span></span> <span data-ttu-id="5e146-129">对象类型是 MAPI_DISTLIST，如果正在使用新的架构。</span><span class="sxs-lookup"><span data-stu-id="5e146-129">If the object type is MAPI_DISTLIST, the new schema is being used.</span></span> <span data-ttu-id="5e146-130">对象类型是 MAPI_MAILUSER，如果正在使用旧的架构。</span><span class="sxs-lookup"><span data-stu-id="5e146-130">If the object type is MAPI_MAILUSER, the old schema is being used.</span></span> 
  
<span data-ttu-id="5e146-131">在新的架构中，所有部门组也是 Dl 和类型 MAPI_DISTLIST。</span><span class="sxs-lookup"><span data-stu-id="5e146-131">In the new schema, all departmental groups are also DLs and are of type MAPI_DISTLIST.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="5e146-132">相关资源</span><span class="sxs-lookup"><span data-stu-id="5e146-132">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="5e146-133">协议规范</span><span class="sxs-lookup"><span data-stu-id="5e146-133">Protocol specifications</span></span>

<span data-ttu-id="5e146-134">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="5e146-134">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="5e146-135">提供属性集定义和相关的 Microsoft Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="5e146-135">Provides property set definitions and references to related Microsoft Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="5e146-136">头文件</span><span class="sxs-lookup"><span data-stu-id="5e146-136">Header files</span></span>

<span data-ttu-id="5e146-137">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="5e146-137">Mapidefs.h</span></span>
  
> <span data-ttu-id="5e146-138">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="5e146-138">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="5e146-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e146-139">See also</span></span>



[<span data-ttu-id="5e146-140">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="5e146-140">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="5e146-141">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="5e146-141">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="5e146-142">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="5e146-142">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="5e146-143">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="5e146-143">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

