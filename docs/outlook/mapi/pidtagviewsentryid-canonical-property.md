---
title: PidTagViewsEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagViewsEntryId
api_type:
- COM
ms.assetid: 8350a37c-6f42-4bef-82e0-35aa12b09fcf
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1980e3bd815b370f125f4449dd7b7f340a7dcb9a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778526"
---
# <a name="pidtagviewsentryid-canonical-property"></a><span data-ttu-id="43e65-103">PidTagViewsEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="43e65-103">PidTagViewsEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="43e65-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="43e65-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="43e65-105">包含用户定义的视图文件夹的项标识符。</span><span class="sxs-lookup"><span data-stu-id="43e65-105">Contains the entry identifier of the user-defined Views folder.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="43e65-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="43e65-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="43e65-107">PR_VIEWS_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="43e65-107">PR_VIEWS_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="43e65-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="43e65-108">Identifier:</span></span>  <br/> |<span data-ttu-id="43e65-109">0x35E5</span><span class="sxs-lookup"><span data-stu-id="43e65-109">0x35E5</span></span>  <br/> |
|<span data-ttu-id="43e65-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="43e65-110">Data type:</span></span>  <br/> |<span data-ttu-id="43e65-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="43e65-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="43e65-112">区域：</span><span class="sxs-lookup"><span data-stu-id="43e65-112">Area:</span></span>  <br/> |<span data-ttu-id="43e65-113">MAPI 邮件存储</span><span class="sxs-lookup"><span data-stu-id="43e65-113">MAPI message store</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="43e65-114">说明</span><span class="sxs-lookup"><span data-stu-id="43e65-114">Remarks</span></span>

<span data-ttu-id="43e65-115">公共视图文件夹包含一组预定义的标准视图说明符，而视图文件夹包含由消息的用户定义的说明符。</span><span class="sxs-lookup"><span data-stu-id="43e65-115">The common view folder contains a predefined set of standard view specifiers, while the view folder contains specifiers defined by a messaging user.</span></span> <span data-ttu-id="43e65-116">这些文件夹，不可见人际邮件 (IPM) 层次结构中，可以包含多个视图说明符，每个存储为邮件。</span><span class="sxs-lookup"><span data-stu-id="43e65-116">These folders, which are not visible in the interpersonal message (IPM) hierarchy, can hold many view specifiers, each one stored as a message.</span></span> <span data-ttu-id="43e65-117">客户端应用程序可以选择合并两个说明符集并使其同时可用。</span><span class="sxs-lookup"><span data-stu-id="43e65-117">The client application can choose to merge the two sets of specifiers and make them both available.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="43e65-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="43e65-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="43e65-119">头文件</span><span class="sxs-lookup"><span data-stu-id="43e65-119">Header files</span></span>

<span data-ttu-id="43e65-120">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="43e65-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="43e65-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="43e65-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="43e65-122">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="43e65-122">Mapitags.h</span></span>
  
> <span data-ttu-id="43e65-123">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="43e65-123">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="43e65-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43e65-124">See also</span></span>



[<span data-ttu-id="43e65-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="43e65-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="43e65-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="43e65-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="43e65-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="43e65-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="43e65-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="43e65-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

