---
title: PidTagLocation 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagLocation
api_type:
- HeaderDef
ms.assetid: 99dffcd9-83dc-462e-b0ce-e2101e546cc6
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 558db0d89103d02f37297c058384cac96ea9ca26
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278783"
---
# <a name="pidtaglocation-canonical-property"></a><span data-ttu-id="b727c-103">PidTagLocation 规范属性</span><span class="sxs-lookup"><span data-stu-id="b727c-103">PidTagLocation Canonical Property</span></span>

  
  
<span data-ttu-id="b727c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b727c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b727c-105">以对收件人组织有用的格式包含收件人的位置。</span><span class="sxs-lookup"><span data-stu-id="b727c-105">Contains the location of the recipient in a format that is useful to the recipient's organization.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b727c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b727c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b727c-107">PR_LOCATION、PR_LOCATION_A、PR_LOCATION_W</span><span class="sxs-lookup"><span data-stu-id="b727c-107">PR_LOCATION, PR_LOCATION_A, PR_LOCATION_W</span></span>  <br/> |
|<span data-ttu-id="b727c-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="b727c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b727c-109">0x3A0D</span><span class="sxs-lookup"><span data-stu-id="b727c-109">0x3A0D</span></span>  <br/> |
|<span data-ttu-id="b727c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b727c-110">Data type:</span></span>  <br/> |<span data-ttu-id="b727c-111">PT_UNICODE、PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="b727c-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="b727c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b727c-112">Area:</span></span>  <br/> |<span data-ttu-id="b727c-113">Address</span><span class="sxs-lookup"><span data-stu-id="b727c-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b727c-114">注解</span><span class="sxs-lookup"><span data-stu-id="b727c-114">Remarks</span></span>

<span data-ttu-id="b727c-115">这些属性可提供收件人的标识和访问信息。</span><span class="sxs-lookup"><span data-stu-id="b727c-115">These properties provide identification and access information for a recipient.</span></span> <span data-ttu-id="b727c-116">它们由收件人及其组织定义。</span><span class="sxs-lookup"><span data-stu-id="b727c-116">They are defined by the recipient and their organization.</span></span> 
  
<span data-ttu-id="b727c-117">内容由收件人组织的需求定义。</span><span class="sxs-lookup"><span data-stu-id="b727c-117">The contents are defined by the needs of the recipient's organization.</span></span> <span data-ttu-id="b727c-118">例如, 一些组织可能通过指定建筑物号码和办公室号码来识别邮件用户。</span><span class="sxs-lookup"><span data-stu-id="b727c-118">For example, some organizations might identify messaging users by specifying the building number and office number.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="b727c-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="b727c-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b727c-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="b727c-120">Protocol specifications</span></span>

<span data-ttu-id="b727c-121">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b727c-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b727c-122">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="b727c-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b727c-123">[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b727c-123">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b727c-124">指定允许用于联系人和个人通讯组列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="b727c-124">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="b727c-125">[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b727c-125">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b727c-126">指定用户、联系人、组和资源列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="b727c-126">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b727c-127">头文件</span><span class="sxs-lookup"><span data-stu-id="b727c-127">Header files</span></span>

<span data-ttu-id="b727c-128">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="b727c-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="b727c-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b727c-129">Provides data type definitions.</span></span>
    
<span data-ttu-id="b727c-130">Mapitags</span><span class="sxs-lookup"><span data-stu-id="b727c-130">Mapitags.h</span></span>
  
> <span data-ttu-id="b727c-131">包含列为关联属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b727c-131">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b727c-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b727c-132">See also</span></span>



[<span data-ttu-id="b727c-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b727c-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b727c-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b727c-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b727c-135">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b727c-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b727c-136">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b727c-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

