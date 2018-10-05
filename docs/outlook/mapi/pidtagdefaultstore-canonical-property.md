---
title: PidTagDefaultStore 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagDefaultStore
api_type:
- HeaderDef
ms.assetid: 6314d91c-4948-4fd1-bacc-932d4bb2c22f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0cbcc8185f6f46a1bfceb2dd6d0aaf9c5d7cab2e
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25385163"
---
# <a name="pidtagdefaultstore-canonical-property"></a><span data-ttu-id="c3182-103">PidTagDefaultStore 规范属性</span><span class="sxs-lookup"><span data-stu-id="c3182-103">PidTagDefaultStore Canonical Property</span></span>

  
  
<span data-ttu-id="c3182-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c3182-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c3182-105">如果消息存储为默认的邮件存储消息存储表中，包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="c3182-105">Contains TRUE if a message store is the default message store in the message store table.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="c3182-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="c3182-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="c3182-107">PR_DEFAULT_STORE</span><span class="sxs-lookup"><span data-stu-id="c3182-107">PR_DEFAULT_STORE</span></span>  <br/> |
|<span data-ttu-id="c3182-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="c3182-108">Identifier:</span></span>  <br/> |<span data-ttu-id="c3182-109">0x3400</span><span class="sxs-lookup"><span data-stu-id="c3182-109">0x3400</span></span>  <br/> |
|<span data-ttu-id="c3182-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="c3182-110">Data type:</span></span>  <br/> |<span data-ttu-id="c3182-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="c3182-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="c3182-112">区域：</span><span class="sxs-lookup"><span data-stu-id="c3182-112">Area:</span></span>  <br/> |<span data-ttu-id="c3182-113">MAPI 邮件存储</span><span class="sxs-lookup"><span data-stu-id="c3182-113">MAPI message store</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c3182-114">说明</span><span class="sxs-lookup"><span data-stu-id="c3182-114">Remarks</span></span>

<span data-ttu-id="c3182-115">此属性显示为消息存储表中的列。</span><span class="sxs-lookup"><span data-stu-id="c3182-115">This property appears as a column in the message store table.</span></span> <span data-ttu-id="c3182-116">值基于**PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="c3182-116">The value is based on **PR_RESOURCE_FLAGS** ([PidTagResourceFlags](pidtagresourceflags-canonical-property.md)).</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="c3182-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="c3182-117">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="c3182-118">协议规范</span><span class="sxs-lookup"><span data-stu-id="c3182-118">Protocol specifications</span></span>

<span data-ttu-id="c3182-119">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="c3182-119">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="c3182-120">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="c3182-120">Provides references to related Exchange Server protocol specifications.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="c3182-121">头文件</span><span class="sxs-lookup"><span data-stu-id="c3182-121">Header files</span></span>

<span data-ttu-id="c3182-122">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="c3182-122">Mapidefs.h</span></span>
  
> <span data-ttu-id="c3182-123">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="c3182-123">Provides data type definitions.</span></span>
    
<span data-ttu-id="c3182-124">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="c3182-124">Mapitags.h</span></span>
  
> <span data-ttu-id="c3182-125">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="c3182-125">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="c3182-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3182-126">See also</span></span>



[<span data-ttu-id="c3182-127">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="c3182-127">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="c3182-128">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="c3182-128">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="c3182-129">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="c3182-129">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="c3182-130">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="c3182-130">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

