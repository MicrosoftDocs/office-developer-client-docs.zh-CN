---
title: PidTagOwnStoreEntryId 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagOwnStoreEntryId
api_type:
- COM
ms.assetid: 6a82ee90-10a1-49e0-8f3a-a2cd9f490f99
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b9ea8af971f9a731aecab0ee6f4b8ea67b651643
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778021"
---
# <a name="pidtagownstoreentryid-canonical-property"></a><span data-ttu-id="9c4d4-103">PidTagOwnStoreEntryId 规范属性</span><span class="sxs-lookup"><span data-stu-id="9c4d4-103">PidTagOwnStoreEntryId Canonical Property</span></span>

  
  
<span data-ttu-id="9c4d4-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9c4d4-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9c4d4-105">包含传输紧密耦合的消息存储的项标识符。</span><span class="sxs-lookup"><span data-stu-id="9c4d4-105">Contains the entry identifier of a transport's tightly coupled message store.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9c4d4-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="9c4d4-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9c4d4-107">PR_OWN_STORE_ENTRYID</span><span class="sxs-lookup"><span data-stu-id="9c4d4-107">PR_OWN_STORE_ENTRYID</span></span>  <br/> |
|<span data-ttu-id="9c4d4-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="9c4d4-108">Identifier:</span></span>  <br/> |<span data-ttu-id="9c4d4-109">0x3E06</span><span class="sxs-lookup"><span data-stu-id="9c4d4-109">0x3E06</span></span>  <br/> |
|<span data-ttu-id="9c4d4-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9c4d4-110">Data type:</span></span>  <br/> |<span data-ttu-id="9c4d4-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="9c4d4-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="9c4d4-112">区域：</span><span class="sxs-lookup"><span data-stu-id="9c4d4-112">Area:</span></span>  <br/> |<span data-ttu-id="9c4d4-113">消息存储属性</span><span class="sxs-lookup"><span data-stu-id="9c4d4-113">Message Store Properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9c4d4-114">说明</span><span class="sxs-lookup"><span data-stu-id="9c4d4-114">Remarks</span></span>

<span data-ttu-id="9c4d4-115">如果存在，则此属性指定为紧密耦合的存储的项标识符。</span><span class="sxs-lookup"><span data-stu-id="9c4d4-115">This property specifies the entry identifier for the tightly coupled store, if one exists.</span></span> <span data-ttu-id="9c4d4-116">例如，传输提供程序可以指定专用文件夹，以便 MAPI 后台处理程序可以连接到存储传输提供程序存储项标识符。</span><span class="sxs-lookup"><span data-stu-id="9c4d4-116">For example, a transport provider can specify the private folder store entry identifier so that the MAPI spooler can connect the transport provider to the store.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="9c4d4-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="9c4d4-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="9c4d4-118">头文件</span><span class="sxs-lookup"><span data-stu-id="9c4d4-118">Header files</span></span>

<span data-ttu-id="9c4d4-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9c4d4-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="9c4d4-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9c4d4-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="9c4d4-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="9c4d4-121">Mapitags.h</span></span>
  
> <span data-ttu-id="9c4d4-122">包含列为相关属性的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="9c4d4-122">Contains definitions of properties listed as associated properties.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9c4d4-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c4d4-123">See also</span></span>



[<span data-ttu-id="9c4d4-124">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9c4d4-124">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9c4d4-125">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9c4d4-125">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9c4d4-126">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="9c4d4-126">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9c4d4-127">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9c4d4-127">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

