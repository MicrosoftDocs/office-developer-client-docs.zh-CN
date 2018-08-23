---
title: PidTagAuthorizingUsers 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagAuthorizingUsers
api_type:
- HeaderDef
ms.assetid: d291777e-c0c6-4de2-9bf5-5c1d95f3db6c
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 806ce556d77d704a1da866c6c69363cb59bd1c7d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581759"
---
# <a name="pidtagauthorizingusers-canonical-property"></a><span data-ttu-id="fe5f4-103">PidTagAuthorizingUsers 规范属性</span><span class="sxs-lookup"><span data-stu-id="fe5f4-103">PidTagAuthorizingUsers Canonical Property</span></span>

  
  
<span data-ttu-id="fe5f4-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fe5f4-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fe5f4-105">包含用户有权发送一条消息的项标识符的列表。</span><span class="sxs-lookup"><span data-stu-id="fe5f4-105">Contains a list of entry identifiers for users who have authorized the sending of a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fe5f4-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="fe5f4-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="fe5f4-107">PR_AUTHORIZING_USERS</span><span class="sxs-lookup"><span data-stu-id="fe5f4-107">PR_AUTHORIZING_USERS</span></span>  <br/> |
|<span data-ttu-id="fe5f4-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="fe5f4-108">Identifier:</span></span>  <br/> |<span data-ttu-id="fe5f4-109">0x0003</span><span class="sxs-lookup"><span data-stu-id="fe5f4-109">0x0003</span></span>  <br/> |
|<span data-ttu-id="fe5f4-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="fe5f4-110">Data type:</span></span>  <br/> |<span data-ttu-id="fe5f4-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="fe5f4-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="fe5f4-112">区域：</span><span class="sxs-lookup"><span data-stu-id="fe5f4-112">Area:</span></span>  <br/> |<span data-ttu-id="fe5f4-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="fe5f4-113">Exchange</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fe5f4-114">注解</span><span class="sxs-lookup"><span data-stu-id="fe5f4-114">Remarks</span></span>

<span data-ttu-id="fe5f4-115">消息存储不保持此属性。</span><span class="sxs-lookup"><span data-stu-id="fe5f4-115">The message store does not maintain this property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="fe5f4-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="fe5f4-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="fe5f4-117">头文件</span><span class="sxs-lookup"><span data-stu-id="fe5f4-117">Header files</span></span>

<span data-ttu-id="fe5f4-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="fe5f4-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="fe5f4-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="fe5f4-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="fe5f4-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="fe5f4-120">Mapitags.h</span></span>
  
> <span data-ttu-id="fe5f4-121">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="fe5f4-121">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fe5f4-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fe5f4-122">See also</span></span>



[<span data-ttu-id="fe5f4-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="fe5f4-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="fe5f4-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="fe5f4-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="fe5f4-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="fe5f4-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="fe5f4-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fe5f4-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

