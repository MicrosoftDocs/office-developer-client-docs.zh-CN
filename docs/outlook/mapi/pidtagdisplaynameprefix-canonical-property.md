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
# <a name="pidtagdisplaynameprefix-canonical-property"></a><span data-ttu-id="38111-103">PidTagDisplayNamePrefix 规范属性</span><span class="sxs-lookup"><span data-stu-id="38111-103">PidTagDisplayNamePrefix Canonical Property</span></span>

  
  
<span data-ttu-id="38111-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="38111-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="38111-105">包含显示名称用户 (的前缀，例如 Miss、Mr.、Mrs.) 。</span><span class="sxs-lookup"><span data-stu-id="38111-105">Contains the display name prefix (such as Miss, Mr., Mrs.) for the messaging user.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="38111-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="38111-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="38111-107">PR_DISPLAY_NAME_PREFIX、PR_DISPLAY_NAME_PREFIX_A、PR_DISPLAY_NAME_PREFIX_W</span><span class="sxs-lookup"><span data-stu-id="38111-107">PR_DISPLAY_NAME_PREFIX, PR_DISPLAY_NAME_PREFIX_A, PR_DISPLAY_NAME_PREFIX_W</span></span>  <br/> |
|<span data-ttu-id="38111-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="38111-108">Identifier:</span></span>  <br/> |<span data-ttu-id="38111-109">0x3A45</span><span class="sxs-lookup"><span data-stu-id="38111-109">0x3A45</span></span>  <br/> |
|<span data-ttu-id="38111-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="38111-110">Data type:</span></span>  <br/> |<span data-ttu-id="38111-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="38111-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="38111-112">区域：</span><span class="sxs-lookup"><span data-stu-id="38111-112">Area:</span></span>  <br/> |<span data-ttu-id="38111-113">MAPI 邮件用户</span><span class="sxs-lookup"><span data-stu-id="38111-113">MAPI mail user</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="38111-114">备注</span><span class="sxs-lookup"><span data-stu-id="38111-114">Remarks</span></span>

<span data-ttu-id="38111-115">这些属性提供有关邮件用户的标识和访问信息。</span><span class="sxs-lookup"><span data-stu-id="38111-115">These properties provide identification and access information about a messaging user.</span></span> <span data-ttu-id="38111-116">内容由邮件用户和邮件用户的组织定义。</span><span class="sxs-lookup"><span data-stu-id="38111-116">The content is defined by the messaging user and the messaging user's organization.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="38111-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="38111-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="38111-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="38111-118">Protocol specifications</span></span>

<span data-ttu-id="38111-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="38111-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="38111-120">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="38111-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="38111-121">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="38111-121">[[MS-OXOCNTC]](https://msdn.microsoft.com/library/9b636532-9150-4836-9635-9c9b756c9ccf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="38111-122">指定联系人和个人通讯组列表允许的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="38111-122">Specifies the properties and operations that are permissible for contacts and personal distribution lists.</span></span>
    
<span data-ttu-id="38111-123">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="38111-123">[[MS-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="38111-124">指定用户、联系人、组和资源的列表的属性和操作。</span><span class="sxs-lookup"><span data-stu-id="38111-124">Specifies the properties and operations for lists of users, contacts, groups, and resources.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="38111-125">头文件</span><span class="sxs-lookup"><span data-stu-id="38111-125">Header files</span></span>

<span data-ttu-id="38111-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="38111-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="38111-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="38111-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="38111-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="38111-128">Mapitags.h</span></span>
  
> <span data-ttu-id="38111-129">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="38111-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="38111-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38111-130">See also</span></span>



[<span data-ttu-id="38111-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="38111-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="38111-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="38111-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="38111-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="38111-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="38111-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="38111-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

