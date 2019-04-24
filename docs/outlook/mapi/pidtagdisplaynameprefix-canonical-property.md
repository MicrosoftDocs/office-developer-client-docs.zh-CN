---
title: PidTagDisplayNamePrefix 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDisplayNamePrefix
api_type:
- HeaderDef
ms.assetid: 014ce1aa-30b9-4106-82a1-447c370853cf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f35ddc2ccec73e485322345fc3bd7d8c7428bc27
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32360793"
---
# <a name="pidtagdisplaynameprefix-canonical-property"></a><span data-ttu-id="b47b7-103">PidTagDisplayNamePrefix 规范属性</span><span class="sxs-lookup"><span data-stu-id="b47b7-103">PidTagDisplayNamePrefix Canonical Property</span></span>

  
  
<span data-ttu-id="b47b7-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b47b7-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b47b7-105">包含邮件用户的显示名称前缀 (如错失、Mr.、Mrs)。</span><span class="sxs-lookup"><span data-stu-id="b47b7-105">Contains the display name prefix (such as Miss, Mr., Mrs.) for the messaging user.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b47b7-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="b47b7-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="b47b7-107">PR_DISPLAY_NAME_PREFIX、PR_DISPLAY_NAME_PREFIX_A、PR_DISPLAY_NAME_PREFIX_W</span><span class="sxs-lookup"><span data-stu-id="b47b7-107">PR_DISPLAY_NAME_PREFIX, PR_DISPLAY_NAME_PREFIX_A, PR_DISPLAY_NAME_PREFIX_W</span></span>  <br/> |
|<span data-ttu-id="b47b7-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="b47b7-108">Identifier:</span></span>  <br/> |<span data-ttu-id="b47b7-109">0x3A45</span><span class="sxs-lookup"><span data-stu-id="b47b7-109">0x3A45</span></span>  <br/> |
|<span data-ttu-id="b47b7-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="b47b7-110">Data type:</span></span>  <br/> |<span data-ttu-id="b47b7-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="b47b7-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="b47b7-112">区域：</span><span class="sxs-lookup"><span data-stu-id="b47b7-112">Area:</span></span>  <br/> |<span data-ttu-id="b47b7-113">MAPI 邮件用户</span><span class="sxs-lookup"><span data-stu-id="b47b7-113">MAPI mail user</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="b47b7-114">注解</span><span class="sxs-lookup"><span data-stu-id="b47b7-114">Remarks</span></span>

<span data-ttu-id="b47b7-115">这些属性提供有关邮件用户的标识和访问信息。</span><span class="sxs-lookup"><span data-stu-id="b47b7-115">These properties provide identification and access information about a messaging user.</span></span> <span data-ttu-id="b47b7-116">内容由邮件用户和邮件用户的组织定义。</span><span class="sxs-lookup"><span data-stu-id="b47b7-116">The content is defined by the messaging user and the messaging user's organization.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="b47b7-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="b47b7-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="b47b7-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="b47b7-118">Protocol specifications</span></span>

<span data-ttu-id="b47b7-119">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b47b7-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b47b7-120">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="b47b7-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="b47b7-121">[[毫秒-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b47b7-121">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b47b7-122">指定允许用于联系人和个人通讯组列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="b47b7-122">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="b47b7-123">[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="b47b7-123">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="b47b7-124">指定用户、联系人、组和资源列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="b47b7-124">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="b47b7-125">头文件</span><span class="sxs-lookup"><span data-stu-id="b47b7-125">Header files</span></span>

<span data-ttu-id="b47b7-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="b47b7-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="b47b7-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="b47b7-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="b47b7-128">Mapitags</span><span class="sxs-lookup"><span data-stu-id="b47b7-128">Mapitags.h</span></span>
  
> <span data-ttu-id="b47b7-129">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="b47b7-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b47b7-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b47b7-130">See also</span></span>



[<span data-ttu-id="b47b7-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="b47b7-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="b47b7-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="b47b7-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="b47b7-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="b47b7-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="b47b7-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="b47b7-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

