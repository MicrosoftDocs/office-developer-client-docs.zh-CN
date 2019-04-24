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
ms.openlocfilehash: 22a1a62f4ee6ff492f36eb18e2d92c8d70febd72
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326122"
---
# <a name="pidtagaddressbookhierarchicalrootdepartment"></a><span data-ttu-id="031e9-103">PidTagAddressBookHierarchicalRootDepartment</span><span class="sxs-lookup"><span data-stu-id="031e9-103">PidTagAddressBookHierarchicalRootDepartment</span></span>

  
  
<span data-ttu-id="031e9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="031e9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="031e9-105">包含层次结构地址根 (HAB) 的可分辨名称 (DN)。</span><span class="sxs-lookup"><span data-stu-id="031e9-105">Contains the distinguished name (DN) of the hierarchical address root (HAB).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="031e9-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="031e9-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="031e9-107">PR_EMS_AB_HAB_ROOT_DEPARTMENT、PR_EMS_AB_HAB_ROOT_DEPARTMENT_A</span><span class="sxs-lookup"><span data-stu-id="031e9-107">PR_EMS_AB_HAB_ROOT_DEPARTMENT, PR_EMS_AB_HAB_ROOT_DEPARTMENT_A</span></span>  <br/> |
|<span data-ttu-id="031e9-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="031e9-108">Property set:</span></span>  <br/> |<span data-ttu-id="031e9-109">通讯簿</span><span class="sxs-lookup"><span data-stu-id="031e9-109">Address Book</span></span>  <br/> |
|<span data-ttu-id="031e9-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="031e9-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="031e9-111">0x8C98</span><span class="sxs-lookup"><span data-stu-id="031e9-111">0x8C98</span></span>  <br/> |
|<span data-ttu-id="031e9-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="031e9-112">Data type:</span></span>  <br/> |<span data-ttu-id="031e9-113">PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="031e9-113">PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="031e9-114">区域：</span><span class="sxs-lookup"><span data-stu-id="031e9-114">Area:</span></span>  <br/> |<span data-ttu-id="031e9-115">Exchange 通讯簿</span><span class="sxs-lookup"><span data-stu-id="031e9-115">Exchange Address Book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="031e9-116">注解</span><span class="sxs-lookup"><span data-stu-id="031e9-116">Remarks</span></span>

<span data-ttu-id="031e9-117">这是全局地址列表 (GAL) 容器上的一个属性, 表示层次结构地址根的可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="031e9-117">This is a property on the global address list (GAL) container and represents the distinguished name of the hierarchical address root.</span></span> <span data-ttu-id="031e9-118">此属性仅存在于脱机通讯簿中, 并且不在 Active Directory 域服务 (AD DS) 中。</span><span class="sxs-lookup"><span data-stu-id="031e9-118">This property is only present in the offline address book and never in Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="031e9-119">调用方应将 MAPI_CACHE_ONLY 传递给 GetProps 调用以避免远程过程调用。</span><span class="sxs-lookup"><span data-stu-id="031e9-119">Callers should pass MAPI_CACHE_ONLY to the GetProps call to avoid a remote procedure call.</span></span> <span data-ttu-id="031e9-120">如果不存在这种情况, 则呼叫者应使用类型为 PT_OBJECT 的 PR_EMS_AB_HAB_ROOT_DEPARTMENT 来查找根部门。</span><span class="sxs-lookup"><span data-stu-id="031e9-120">If this is not present, callers should use PR_EMS_AB_HAB_ROOT_DEPARTMENT, which is of type PT_OBJECT, to find the root department.</span></span> 
  
<span data-ttu-id="031e9-121">获取根部门后, 它可以具有对象类型 MAPI_MAILUSER 或 MAPI_DISTLIST。</span><span class="sxs-lookup"><span data-stu-id="031e9-121">Once the root department is obtained, it can have an object type MAPI_MAILUSER or MAPI_DISTLIST.</span></span> <span data-ttu-id="031e9-122">如果对象类型为 MAPI_DISTLIST, 则将采用新架构。</span><span class="sxs-lookup"><span data-stu-id="031e9-122">If the object type is MAPI_DISTLIST, the new schema is being employed.</span></span> <span data-ttu-id="031e9-123">如果对象类型为 MAPI_MAILUSER, 则将采用前一个架构。</span><span class="sxs-lookup"><span data-stu-id="031e9-123">If the object type is MAPI_MAILUSER, the previous schema is being employed.</span></span> 
  
- <span data-ttu-id="031e9-124">Microsoft Office Outlook 2007 Service Pack 2 支持这两种架构。</span><span class="sxs-lookup"><span data-stu-id="031e9-124">Microsoft Office Outlook 2007 Service Pack 2 supports both schemas.</span></span> 
    
- <span data-ttu-id="031e9-125">microsoft outlook 2010 和 microsoft outlook 2013 支持新架构。</span><span class="sxs-lookup"><span data-stu-id="031e9-125">Microsoft Outlook 2010 and Microsoft Outlook 2013 support the new schema.</span></span>
    
<span data-ttu-id="031e9-126">在新架构中, 所有部门组也都是通讯组列表, 其类型为 MAPI_DISTLIST。</span><span class="sxs-lookup"><span data-stu-id="031e9-126">In the new schema, all departmental groups are also distribution lists and are of type MAPI_DISTLIST.</span></span> <span data-ttu-id="031e9-127">部门组的成员以及部门组中的部门是通过使用 PR_EMS_AB_MEMBER (与通讯组列表成员完全一样) 获取的。</span><span class="sxs-lookup"><span data-stu-id="031e9-127">Members of departmental groups, and departments within departmental groups are obtained by using PR_EMS_AB_MEMBER, exactly like distribution list members.</span></span>
  
<span data-ttu-id="031e9-128">获取根部门后, 它可以具有对象类型 MAPI_MAILUSER 或 MAPI_DISTLIST。</span><span class="sxs-lookup"><span data-stu-id="031e9-128">Once the root department is obtained, it can have an object type MAPI_MAILUSER or MAPI_DISTLIST.</span></span> <span data-ttu-id="031e9-129">如果对象类型为 MAPI_DISTLIST, 则使用新架构。</span><span class="sxs-lookup"><span data-stu-id="031e9-129">If the object type is MAPI_DISTLIST, the new schema is being used.</span></span> <span data-ttu-id="031e9-130">如果对象类型为 MAPI_MAILUSER, 则使用旧架构。</span><span class="sxs-lookup"><span data-stu-id="031e9-130">If the object type is MAPI_MAILUSER, the old schema is being used.</span></span> 
  
<span data-ttu-id="031e9-131">在新架构中, 所有部门组也都是 dl, 其类型为 MAPI_DISTLIST。</span><span class="sxs-lookup"><span data-stu-id="031e9-131">In the new schema, all departmental groups are also DLs and are of type MAPI_DISTLIST.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="031e9-132">相关资源</span><span class="sxs-lookup"><span data-stu-id="031e9-132">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="031e9-133">协议规范</span><span class="sxs-lookup"><span data-stu-id="031e9-133">Protocol specifications</span></span>

<span data-ttu-id="031e9-134">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="031e9-134">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="031e9-135">提供属性集定义和对相关 Microsoft Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="031e9-135">Provides property set definitions and references to related Microsoft Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="031e9-136">头文件</span><span class="sxs-lookup"><span data-stu-id="031e9-136">Header files</span></span>

<span data-ttu-id="031e9-137">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="031e9-137">Mapidefs.h</span></span>
  
> <span data-ttu-id="031e9-138">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="031e9-138">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="031e9-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="031e9-139">See also</span></span>



[<span data-ttu-id="031e9-140">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="031e9-140">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="031e9-141">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="031e9-141">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="031e9-142">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="031e9-142">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="031e9-143">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="031e9-143">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

