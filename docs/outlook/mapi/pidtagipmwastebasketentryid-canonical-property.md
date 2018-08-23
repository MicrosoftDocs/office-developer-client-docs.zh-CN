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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 66bbf49d737c42ecc2f6c765a60540163649f447
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573892"
---
# <a name="pidtagipmwastebasketentryid-canonical-property"></a><span data-ttu-id="57b5a-103">PidTagIpmWastebasketEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="57b5a-103">PidTagIpmWastebasketEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="57b5a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="57b5a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="57b5a-105">包含标准人际邮件 (IPM) 已删除邮件文件夹的项标识符。</span><span class="sxs-lookup"><span data-stu-id="57b5a-105">Contains the entry identifier of the standard interpersonal message (IPM) Deleted Items folder.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="57b5a-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="57b5a-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="57b5a-107">PR_IPM_WASTEBASKET_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="57b5a-107">PR_IPM_WASTEBASKET_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="57b5a-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="57b5a-108">Identifier:</span></span>  <br/> |<span data-ttu-id="57b5a-109">0x35E3</span><span class="sxs-lookup"><span data-stu-id="57b5a-109">0x35E3</span></span>  <br/> |
|<span data-ttu-id="57b5a-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="57b5a-110">Data type:</span></span>  <br/> |<span data-ttu-id="57b5a-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="57b5a-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="57b5a-112">区域：</span><span class="sxs-lookup"><span data-stu-id="57b5a-112">Area:</span></span>  <br/> |<span data-ttu-id="57b5a-113">Folder</span><span class="sxs-lookup"><span data-stu-id="57b5a-113">Folder</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="57b5a-114">注解</span><span class="sxs-lookup"><span data-stu-id="57b5a-114">Remarks</span></span>

<span data-ttu-id="57b5a-115">客户端应用程序应将已删除人际邮件移动到已删除邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="57b5a-115">A client application should move deleted interpersonal messages to the Deleted Items folder.</span></span> <span data-ttu-id="57b5a-116">如果邮件已在此文件夹中，或不支持此属性，客户端应删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="57b5a-116">If the message is already in this folder, or if this property is not supported, the client should delete the message.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="57b5a-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="57b5a-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="57b5a-118">头文件</span><span class="sxs-lookup"><span data-stu-id="57b5a-118">Header files</span></span>

<span data-ttu-id="57b5a-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="57b5a-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="57b5a-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="57b5a-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="57b5a-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="57b5a-121">Mapitags.h</span></span>
  
> <span data-ttu-id="57b5a-122">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="57b5a-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="57b5a-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57b5a-123">See also</span></span>



[<span data-ttu-id="57b5a-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="57b5a-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="57b5a-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="57b5a-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="57b5a-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="57b5a-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="57b5a-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="57b5a-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

