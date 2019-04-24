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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8295ae6904f503ca831a00c1f35ac08596b5358c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32269998"
---
# <a name="pidtagdefaultprofile-canonical-property"></a><span data-ttu-id="ff137-103">PidTagDefaultProfile 规范属性</span><span class="sxs-lookup"><span data-stu-id="ff137-103">PidTagDefaultProfile Canonical Property</span></span>

  
  
<span data-ttu-id="ff137-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ff137-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ff137-105">如果邮件用户配置文件是 MAPI 的默认配置文件, 则该参数为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="ff137-105">Contains TRUE if a messaging user profile is the MAPI default profile.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ff137-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ff137-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ff137-107">PR_DEFAULT_PROFILE</span><span class="sxs-lookup"><span data-stu-id="ff137-107">PR_DEFAULT_PROFILE</span></span>  <br/> |
|<span data-ttu-id="ff137-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ff137-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ff137-109">0x3D04</span><span class="sxs-lookup"><span data-stu-id="ff137-109">0x3D04</span></span>  <br/> |
|<span data-ttu-id="ff137-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ff137-110">Data type:</span></span>  <br/> |<span data-ttu-id="ff137-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="ff137-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="ff137-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ff137-112">Area:</span></span>  <br/> |<span data-ttu-id="ff137-113">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="ff137-113">MAPI profile</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ff137-114">注解</span><span class="sxs-lookup"><span data-stu-id="ff137-114">Remarks</span></span>

<span data-ttu-id="ff137-115">此属性不显示为任何对象的属性, 而只作为配置文件表中的一列。</span><span class="sxs-lookup"><span data-stu-id="ff137-115">This property does not appear as a property of any object but only as a column in a profile table.</span></span> <span data-ttu-id="ff137-116">客户端应用程序可以使用[IProfAdmin:: SetDefaultProfile](iprofadmin-setdefaultprofile.md)方法来指定默认配置文件。</span><span class="sxs-lookup"><span data-stu-id="ff137-116">A client application can use the [IProfAdmin::SetDefaultProfile](iprofadmin-setdefaultprofile.md) method to designate the default profile.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="ff137-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="ff137-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="ff137-118">头文件</span><span class="sxs-lookup"><span data-stu-id="ff137-118">Header files</span></span>

<span data-ttu-id="ff137-119">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="ff137-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="ff137-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ff137-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="ff137-121">Mapitags</span><span class="sxs-lookup"><span data-stu-id="ff137-121">Mapitags.h</span></span>
  
> <span data-ttu-id="ff137-122">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ff137-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ff137-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff137-123">See also</span></span>



[<span data-ttu-id="ff137-124">PidTagDefaultStore 规范属性</span><span class="sxs-lookup"><span data-stu-id="ff137-124">PidTagDefaultStore Canonical Property</span></span>](pidtagdefaultstore-canonical-property.md)


[<span data-ttu-id="ff137-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ff137-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ff137-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ff137-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ff137-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ff137-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ff137-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ff137-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

