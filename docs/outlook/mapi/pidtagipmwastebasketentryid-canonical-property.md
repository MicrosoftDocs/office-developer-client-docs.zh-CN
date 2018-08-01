---
title: PidTagIpmWastebasketEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagIpmWastebasketEntryId
api_type:
- HeaderDef
ms.assetid: 0f8dd043-66f0-4193-9b95-853bc3827f73
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: b9b8cff0a552c5c12108bdc4b31fe9c3930ab5d2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777799"
---
# <a name="pidtagipmwastebasketentryid-canonical-property"></a><span data-ttu-id="3ccef-103">PidTagIpmWastebasketEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="3ccef-103">PidTagIpmWastebasketEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="3ccef-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3ccef-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3ccef-105">包含标准人际邮件 (IPM) 已删除邮件文件夹的项标识符。</span><span class="sxs-lookup"><span data-stu-id="3ccef-105">Contains the entry identifier of the standard interpersonal message (IPM) Deleted Items folder.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3ccef-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="3ccef-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3ccef-107">PR_IPM_WASTEBASKET_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="3ccef-107">PR_IPM_WASTEBASKET_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="3ccef-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="3ccef-108">Identifier:</span></span>  <br/> |<span data-ttu-id="3ccef-109">0x35E3</span><span class="sxs-lookup"><span data-stu-id="3ccef-109">0x35E3</span></span>  <br/> |
|<span data-ttu-id="3ccef-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3ccef-110">Data type:</span></span>  <br/> |<span data-ttu-id="3ccef-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="3ccef-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="3ccef-112">区域：</span><span class="sxs-lookup"><span data-stu-id="3ccef-112">Area:</span></span>  <br/> |<span data-ttu-id="3ccef-113">Folder</span><span class="sxs-lookup"><span data-stu-id="3ccef-113">Folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3ccef-114">备注</span><span class="sxs-lookup"><span data-stu-id="3ccef-114">Remarks</span></span>

<span data-ttu-id="3ccef-115">客户端应用程序应将已删除人际邮件移动到已删除邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="3ccef-115">A client application should move deleted interpersonal messages to the Deleted Items folder.</span></span> <span data-ttu-id="3ccef-116">如果邮件已在此文件夹中，或不支持此属性，客户端应删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="3ccef-116">If the message is already in this folder, or if this property is not supported, the client should delete the message.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="3ccef-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="3ccef-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="3ccef-118">头文件</span><span class="sxs-lookup"><span data-stu-id="3ccef-118">Header files</span></span>

<span data-ttu-id="3ccef-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3ccef-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="3ccef-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3ccef-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="3ccef-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="3ccef-121">Mapitags.h</span></span>
  
> <span data-ttu-id="3ccef-122">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="3ccef-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3ccef-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ccef-123">See also</span></span>



[<span data-ttu-id="3ccef-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3ccef-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3ccef-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3ccef-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3ccef-126">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3ccef-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3ccef-127">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3ccef-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)
