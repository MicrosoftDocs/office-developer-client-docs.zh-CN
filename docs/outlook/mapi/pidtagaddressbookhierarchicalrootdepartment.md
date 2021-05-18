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
# <a name="pidtagaddressbookhierarchicalrootdepartment"></a><span data-ttu-id="3ce64-103">PidTagAddressBookHierarchicalRootDepartment</span><span class="sxs-lookup"><span data-stu-id="3ce64-103">PidTagAddressBookHierarchicalRootDepartment</span></span>

  
  
<span data-ttu-id="3ce64-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3ce64-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
 <span data-ttu-id="3ce64-105">包含层次结构地址根 (DN) DN (HAB) 。</span><span class="sxs-lookup"><span data-stu-id="3ce64-105">Contains the distinguished name (DN) of the hierarchical address root (HAB).</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3ce64-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3ce64-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3ce64-107">PR_EMS_AB_HAB_ROOT_DEPARTMENT、PR_EMS_AB_HAB_ROOT_DEPARTMENT_A</span><span class="sxs-lookup"><span data-stu-id="3ce64-107">PR_EMS_AB_HAB_ROOT_DEPARTMENT, PR_EMS_AB_HAB_ROOT_DEPARTMENT_A</span></span>  <br/> |
|<span data-ttu-id="3ce64-108">属性集：</span><span class="sxs-lookup"><span data-stu-id="3ce64-108">Property set:</span></span>  <br/> |<span data-ttu-id="3ce64-109">通讯簿</span><span class="sxs-lookup"><span data-stu-id="3ce64-109">Address Book</span></span>  <br/> |
|<span data-ttu-id="3ce64-110">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="3ce64-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="3ce64-111">0x8C98</span><span class="sxs-lookup"><span data-stu-id="3ce64-111">0x8C98</span></span>  <br/> |
|<span data-ttu-id="3ce64-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3ce64-112">Data type:</span></span>  <br/> |<span data-ttu-id="3ce64-113">PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="3ce64-113">PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="3ce64-114">区域：</span><span class="sxs-lookup"><span data-stu-id="3ce64-114">Area:</span></span>  <br/> |<span data-ttu-id="3ce64-115">Exchange通讯簿</span><span class="sxs-lookup"><span data-stu-id="3ce64-115">Exchange Address Book</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3ce64-116">备注</span><span class="sxs-lookup"><span data-stu-id="3ce64-116">Remarks</span></span>

<span data-ttu-id="3ce64-117">这是全局地址列表上的一个属性 (GAL) ，表示分层地址根的可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="3ce64-117">This is a property on the global address list (GAL) container and represents the distinguished name of the hierarchical address root.</span></span> <span data-ttu-id="3ce64-118">此属性仅存在于脱机通讯簿中，从不存在于 AD DS (Active Directory 域服务) 。</span><span class="sxs-lookup"><span data-stu-id="3ce64-118">This property is only present in the offline address book and never in Active Directory Domain Services (AD DS).</span></span> <span data-ttu-id="3ce64-119">调用方应MAPI_CACHE_ONLY GetProps 调用，以避免远程过程调用。</span><span class="sxs-lookup"><span data-stu-id="3ce64-119">Callers should pass MAPI_CACHE_ONLY to the GetProps call to avoid a remote procedure call.</span></span> <span data-ttu-id="3ce64-120">如果不存在，则调用方应该PR_EMS_AB_HAB_ROOT_DEPARTMENT类型为 PT_OBJECT，以查找根部门。</span><span class="sxs-lookup"><span data-stu-id="3ce64-120">If this is not present, callers should use PR_EMS_AB_HAB_ROOT_DEPARTMENT, which is of type PT_OBJECT, to find the root department.</span></span> 
  
<span data-ttu-id="3ce64-121">获取根部门后，它可以具有一个对象类型 MAPI_MAILUSER或MAPI_DISTLIST。</span><span class="sxs-lookup"><span data-stu-id="3ce64-121">Once the root department is obtained, it can have an object type MAPI_MAILUSER or MAPI_DISTLIST.</span></span> <span data-ttu-id="3ce64-122">如果对象类型，MAPI_DISTLIST新架构。</span><span class="sxs-lookup"><span data-stu-id="3ce64-122">If the object type is MAPI_DISTLIST, the new schema is being employed.</span></span> <span data-ttu-id="3ce64-123">如果对象类型，MAPI_MAILUSER上一个架构。</span><span class="sxs-lookup"><span data-stu-id="3ce64-123">If the object type is MAPI_MAILUSER, the previous schema is being employed.</span></span> 
  
- <span data-ttu-id="3ce64-124">Microsoft Office Outlook 2007 Service Pack 2 支持这两种架构。</span><span class="sxs-lookup"><span data-stu-id="3ce64-124">Microsoft Office Outlook 2007 Service Pack 2 supports both schemas.</span></span> 
    
- <span data-ttu-id="3ce64-125">Microsoft Outlook 2010 和 Microsoft Outlook 2013 支持新架构。</span><span class="sxs-lookup"><span data-stu-id="3ce64-125">Microsoft Outlook 2010 and Microsoft Outlook 2013 support the new schema.</span></span>
    
<span data-ttu-id="3ce64-126">在新的架构中，所有部门组也是通讯组列表，并且MAPI_DISTLIST。</span><span class="sxs-lookup"><span data-stu-id="3ce64-126">In the new schema, all departmental groups are also distribution lists and are of type MAPI_DISTLIST.</span></span> <span data-ttu-id="3ce64-127">部门组的成员和部门组内的部门成员是通过使用通讯组PR_EMS_AB_MEMBER，与通讯组列表成员完全相同。</span><span class="sxs-lookup"><span data-stu-id="3ce64-127">Members of departmental groups, and departments within departmental groups are obtained by using PR_EMS_AB_MEMBER, exactly like distribution list members.</span></span>
  
<span data-ttu-id="3ce64-128">获取根部门后，它可以具有一个对象类型 MAPI_MAILUSER或MAPI_DISTLIST。</span><span class="sxs-lookup"><span data-stu-id="3ce64-128">Once the root department is obtained, it can have an object type MAPI_MAILUSER or MAPI_DISTLIST.</span></span> <span data-ttu-id="3ce64-129">如果对象类型新MAPI_DISTLIST，则使用新架构。</span><span class="sxs-lookup"><span data-stu-id="3ce64-129">If the object type is MAPI_DISTLIST, the new schema is being used.</span></span> <span data-ttu-id="3ce64-130">如果对象类型，MAPI_MAILUSER旧架构。</span><span class="sxs-lookup"><span data-stu-id="3ce64-130">If the object type is MAPI_MAILUSER, the old schema is being used.</span></span> 
  
<span data-ttu-id="3ce64-131">在新的架构中，所有部门组也是 DLL，并且MAPI_DISTLIST。</span><span class="sxs-lookup"><span data-stu-id="3ce64-131">In the new schema, all departmental groups are also DLs and are of type MAPI_DISTLIST.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="3ce64-132">相关资源</span><span class="sxs-lookup"><span data-stu-id="3ce64-132">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="3ce64-133">协议规范</span><span class="sxs-lookup"><span data-stu-id="3ce64-133">Protocol specifications</span></span>

<span data-ttu-id="3ce64-134">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="3ce64-134">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="3ce64-135">提供属性集定义和对相关协议规范Microsoft Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="3ce64-135">Provides property set definitions and references to related Microsoft Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="3ce64-136">头文件</span><span class="sxs-lookup"><span data-stu-id="3ce64-136">Header files</span></span>

<span data-ttu-id="3ce64-137">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3ce64-137">Mapidefs.h</span></span>
  
> <span data-ttu-id="3ce64-138">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3ce64-138">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3ce64-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ce64-139">See also</span></span>



[<span data-ttu-id="3ce64-140">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3ce64-140">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3ce64-141">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3ce64-141">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3ce64-142">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3ce64-142">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3ce64-143">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3ce64-143">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

