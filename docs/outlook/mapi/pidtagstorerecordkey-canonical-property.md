---
title: PidTagStoreRecordKey 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagStoreRecordKey
api_type:
- COM
ms.assetid: 27347302-bd52-4f62-98f1-6c37f9a66463
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d6f858a9f1d3d4620a86621e3f5ecb4ad4609691
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278727"
---
# <a name="pidtagstorerecordkey-canonical-property"></a><span data-ttu-id="d80b8-103">PidTagStoreRecordKey 规范属性</span><span class="sxs-lookup"><span data-stu-id="d80b8-103">PidTagStoreRecordKey Canonical Property</span></span>

  
  
<span data-ttu-id="d80b8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d80b8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d80b8-105">包含对象驻留的邮件 (的唯) 二进制比较标识符。</span><span class="sxs-lookup"><span data-stu-id="d80b8-105">Contains the unique binary-comparable identifier (record key) of the message store in which an object resides.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="d80b8-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="d80b8-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="d80b8-107">PR_STORE_RECORD_KEY</span><span class="sxs-lookup"><span data-stu-id="d80b8-107">PR_STORE_RECORD_KEY</span></span>  <br/> |
|<span data-ttu-id="d80b8-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="d80b8-108">Identifier:</span></span>  <br/> |<span data-ttu-id="d80b8-109">0x0FFA</span><span class="sxs-lookup"><span data-stu-id="d80b8-109">0x0FFA</span></span>  <br/> |
|<span data-ttu-id="d80b8-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="d80b8-110">Data type:</span></span>  <br/> |<span data-ttu-id="d80b8-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="d80b8-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="d80b8-112">区域：</span><span class="sxs-lookup"><span data-stu-id="d80b8-112">Area:</span></span>  <br/> |<span data-ttu-id="d80b8-113">ID 属性</span><span class="sxs-lookup"><span data-stu-id="d80b8-113">ID properties</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="d80b8-114">备注</span><span class="sxs-lookup"><span data-stu-id="d80b8-114">Remarks</span></span>

<span data-ttu-id="d80b8-115">对于邮件存储，此属性与[PidTagRecordKey](pidtagrecordkey-canonical-property.md) 属性PR_RECORD_KEY (存储) 相同。</span><span class="sxs-lookup"><span data-stu-id="d80b8-115">For a message store, this property is identical to the store's own **PR_RECORD_KEY** ([PidTagRecordKey](pidtagrecordkey-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="d80b8-116">此属性和 PR_RECORD_KEY 之间的关系与 PR_STORE_ENTRYID ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) 和 **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)) 之间的关系相同。</span><span class="sxs-lookup"><span data-stu-id="d80b8-116">The relationship between this property and **PR_RECORD_KEY** is the same as the relationship between **PR_STORE_ENTRYID** ([PidTagStoreEntryId](pidtagstoreentryid-canonical-property.md)) and **PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md)).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="d80b8-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="d80b8-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="d80b8-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="d80b8-118">Protocol specifications</span></span>

<span data-ttu-id="d80b8-119">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d80b8-119">[[MS-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d80b8-120">处理邮件和附件对象。</span><span class="sxs-lookup"><span data-stu-id="d80b8-120">Handles message and attachment objects.</span></span>
    
<span data-ttu-id="d80b8-121">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="d80b8-121">[[MS-OXCICAL]](https://msdn.microsoft.com/library/a685a040-5b69-4c84-b084-795113fb4012%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="d80b8-122">在 IETF RFC2445、RFC2446 和 RFC2447 以及约会和会议对象之间转换。</span><span class="sxs-lookup"><span data-stu-id="d80b8-122">Converts between IETF RFC2445, RFC2446, and RFC2447, and appointment and meeting objects.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="d80b8-123">头文件</span><span class="sxs-lookup"><span data-stu-id="d80b8-123">Header files</span></span>

<span data-ttu-id="d80b8-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="d80b8-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="d80b8-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="d80b8-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="d80b8-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="d80b8-126">Mapitags.h</span></span>
  
> <span data-ttu-id="d80b8-127">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="d80b8-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="d80b8-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d80b8-128">See also</span></span>



[<span data-ttu-id="d80b8-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="d80b8-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="d80b8-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="d80b8-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="d80b8-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="d80b8-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="d80b8-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="d80b8-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

