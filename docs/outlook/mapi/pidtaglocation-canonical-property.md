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
ms.openlocfilehash: 5ef88992cefda851742bb332c643136603a4d6a0
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584588"
---
# <a name="pidtaglocation-canonical-property"></a><span data-ttu-id="b6ac2-103">PidTagLocation 规范属性</span><span class="sxs-lookup"><span data-stu-id="b6ac2-103">PidTagLocation Canonical Property</span></span>

  
  
<span data-ttu-id="b6ac2-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b6ac2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b6ac2-105">包含的收件人的组织非常有用的格式的收件人的位置。</span><span class="sxs-lookup"><span data-stu-id="b6ac2-105">Contains the location of the recipient in a format that is useful to the recipient's organization.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b6ac2-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b6ac2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b6ac2-107">PR_LOCATION，PR_LOCATION_A，PR_LOCATION_W</span><span class="sxs-lookup"><span data-stu-id="b6ac2-107">PR_LOCATION, PR_LOCATION_A, PR_LOCATION_W</span></span>  <br/> |
|<span data-ttu-id="b6ac2-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="b6ac2-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b6ac2-109">0x3A0D</span><span class="sxs-lookup"><span data-stu-id="b6ac2-109">0x3A0D</span></span>  <br/> |
|<span data-ttu-id="b6ac2-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b6ac2-110">Data type:</span></span>  <br/> |<span data-ttu-id="b6ac2-111">PT_UNICODE PT_STRING8</span><span class="sxs-lookup"><span data-stu-id="b6ac2-111">PT_UNICODE, PT_STRING8</span></span>  <br/> |
|<span data-ttu-id="b6ac2-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b6ac2-112">Area:</span></span>  <br/> |<span data-ttu-id="b6ac2-113">Address</span><span class="sxs-lookup"><span data-stu-id="b6ac2-113">Address</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b6ac2-114">注解</span><span class="sxs-lookup"><span data-stu-id="b6ac2-114">Remarks</span></span>

<span data-ttu-id="b6ac2-115">这些属性提供标识和访问收件人的信息。</span><span class="sxs-lookup"><span data-stu-id="b6ac2-115">These properties provide identification and access information for a recipient.</span></span> <span data-ttu-id="b6ac2-116">它们是按收件人和组织定义的。</span><span class="sxs-lookup"><span data-stu-id="b6ac2-116">They are defined by the recipient and their organization.</span></span> 
  
<span data-ttu-id="b6ac2-117">由收件人的组织的需要定义内容。</span><span class="sxs-lookup"><span data-stu-id="b6ac2-117">The contents are defined by the needs of the recipient's organization.</span></span> <span data-ttu-id="b6ac2-118">例如，某些组织可能通过指定构建号和办公室电话号码标识消息用户。</span><span class="sxs-lookup"><span data-stu-id="b6ac2-118">For example, some organizations might identify messaging users by specifying the building number and office number.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="b6ac2-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="b6ac2-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b6ac2-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="b6ac2-120">Protocol specifications</span></span>

<span data-ttu-id="b6ac2-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b6ac2-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b6ac2-122">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="b6ac2-122">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b6ac2-123">[[MS OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b6ac2-123">[[MS-OXOCNTC]](http://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b6ac2-124">指定的属性和操作所允许的联系人和个人通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="b6ac2-124">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="b6ac2-125">[[MS OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b6ac2-125">[[MS-OXOABK]](http://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b6ac2-126">指定的属性和用户、 联系人、 组和资源的操作列表。</span><span class="sxs-lookup"><span data-stu-id="b6ac2-126">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b6ac2-127">头文件</span><span class="sxs-lookup"><span data-stu-id="b6ac2-127">Header files</span></span>

<span data-ttu-id="b6ac2-128">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b6ac2-128">Mapidefs.h</span></span>
  
> <span data-ttu-id="b6ac2-129">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b6ac2-129">Provides data type definitions.</span></span>
    
<span data-ttu-id="b6ac2-130">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="b6ac2-130">Mapitags.h</span></span>
  
> <span data-ttu-id="b6ac2-131">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b6ac2-131">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b6ac2-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b6ac2-132">See also</span></span>



[<span data-ttu-id="b6ac2-133">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b6ac2-133">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b6ac2-134">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b6ac2-134">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b6ac2-135">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b6ac2-135">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b6ac2-136">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b6ac2-136">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

