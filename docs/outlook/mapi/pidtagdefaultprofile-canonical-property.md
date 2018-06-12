---
title: PidTagDefaultProfile 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDefaultProfile
api_type:
- HeaderDef
ms.assetid: 47f745a4-5a9c-42af-b076-a72548ef4d31
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 6cd255c60987ec7a279e509aa2925a8029cce62e
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777518"
---
# <a name="pidtagdefaultprofile-canonical-property"></a><span data-ttu-id="b9ccc-103">PidTagDefaultProfile 规范属性</span><span class="sxs-lookup"><span data-stu-id="b9ccc-103">PidTagDefaultProfile Canonical Property</span></span>

  
  
<span data-ttu-id="b9ccc-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b9ccc-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b9ccc-105">如果邮件的用户配置文件的 MAPI 默认配置文件，包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="b9ccc-105">Contains TRUE if a messaging user profile is the MAPI default profile.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="b9ccc-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="b9ccc-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b9ccc-107">PR_DEFAULT_PROFILE</span><span class="sxs-lookup"><span data-stu-id="b9ccc-107">PR_DEFAULT_PROFILE</span></span>  <br/> |
|<span data-ttu-id="b9ccc-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="b9ccc-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b9ccc-109">0x3D04</span><span class="sxs-lookup"><span data-stu-id="b9ccc-109">0x3D04</span></span>  <br/> |
|<span data-ttu-id="b9ccc-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b9ccc-110">Data type:</span></span>  <br/> |<span data-ttu-id="b9ccc-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="b9ccc-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="b9ccc-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b9ccc-112">Area:</span></span>  <br/> |<span data-ttu-id="b9ccc-113">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="b9ccc-113">MAPI profile</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b9ccc-114">备注</span><span class="sxs-lookup"><span data-stu-id="b9ccc-114">Remarks</span></span>

<span data-ttu-id="b9ccc-115">此属性不显示任何对象的属性但只能作为 profile 表中的列。</span><span class="sxs-lookup"><span data-stu-id="b9ccc-115">This property does not appear as a property of any object but only as a column in a profile table.</span></span> <span data-ttu-id="b9ccc-116">客户端应用程序可以使用[IProfAdmin::SetDefaultProfile](iprofadmin-setdefaultprofile.md)方法指定的默认配置文件。</span><span class="sxs-lookup"><span data-stu-id="b9ccc-116">A client application can use the [IProfAdmin::SetDefaultProfile](iprofadmin-setdefaultprofile.md) method to designate the default profile.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="b9ccc-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="b9ccc-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="b9ccc-118">头文件</span><span class="sxs-lookup"><span data-stu-id="b9ccc-118">Header files</span></span>

<span data-ttu-id="b9ccc-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b9ccc-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="b9ccc-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b9ccc-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="b9ccc-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="b9ccc-121">Mapitags.h</span></span>
  
> <span data-ttu-id="b9ccc-122">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b9ccc-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b9ccc-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9ccc-123">See also</span></span>



[<span data-ttu-id="b9ccc-124">PidTagDefaultStore 规范属性</span><span class="sxs-lookup"><span data-stu-id="b9ccc-124">PidTagDefaultStore Canonical Property</span></span>](pidtagdefaultstore-canonical-property.md)


[<span data-ttu-id="b9ccc-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b9ccc-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b9ccc-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b9ccc-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b9ccc-127">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b9ccc-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b9ccc-128">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b9ccc-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

