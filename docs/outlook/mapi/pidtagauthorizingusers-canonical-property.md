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
ms.openlocfilehash: ec078429bb5321ffd7271c553d435e07e903926a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777370"
---
# <a name="pidtagauthorizingusers-canonical-property"></a><span data-ttu-id="cb276-103">PidTagAuthorizingUsers 规范属性</span><span class="sxs-lookup"><span data-stu-id="cb276-103">PidTagAuthorizingUsers Canonical Property</span></span>

  
  
<span data-ttu-id="cb276-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="cb276-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="cb276-105">包含用户有权发送一条消息的项标识符的列表。</span><span class="sxs-lookup"><span data-stu-id="cb276-105">Contains a list of entry identifiers for users who have authorized the sending of a message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cb276-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="cb276-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="cb276-107">PR_AUTHORIZING_USERS</span><span class="sxs-lookup"><span data-stu-id="cb276-107">PR_AUTHORIZING_USERS</span></span>  <br/> |
|<span data-ttu-id="cb276-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="cb276-108">Identifier:</span></span>  <br/> |<span data-ttu-id="cb276-109">0x0003</span><span class="sxs-lookup"><span data-stu-id="cb276-109">0x0003</span></span>  <br/> |
|<span data-ttu-id="cb276-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="cb276-110">Data type:</span></span>  <br/> |<span data-ttu-id="cb276-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="cb276-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="cb276-112">区域：</span><span class="sxs-lookup"><span data-stu-id="cb276-112">Area:</span></span>  <br/> |<span data-ttu-id="cb276-113">Exchange</span><span class="sxs-lookup"><span data-stu-id="cb276-113">Exchange</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cb276-114">说明</span><span class="sxs-lookup"><span data-stu-id="cb276-114">Remarks</span></span>

<span data-ttu-id="cb276-115">消息存储不保持此属性。</span><span class="sxs-lookup"><span data-stu-id="cb276-115">The message store does not maintain this property.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="cb276-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="cb276-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="cb276-117">头文件</span><span class="sxs-lookup"><span data-stu-id="cb276-117">Header files</span></span>

<span data-ttu-id="cb276-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="cb276-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="cb276-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="cb276-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="cb276-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="cb276-120">Mapitags.h</span></span>
  
> <span data-ttu-id="cb276-121">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="cb276-121">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cb276-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cb276-122">See also</span></span>



[<span data-ttu-id="cb276-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="cb276-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="cb276-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="cb276-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="cb276-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="cb276-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="cb276-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cb276-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

