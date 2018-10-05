---
title: PidTagSubfolders 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagSubfolders
api_type:
- COM
ms.assetid: b456b07b-4d83-46bf-a305-4f322ea7dbd1
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8de14542c0d2a4e6d95fb4258697b827f82b8d06
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25384400"
---
# <a name="pidtagsubfolders-canonical-property"></a><span data-ttu-id="4e290-103">PidTagSubfolders 规范属性</span><span class="sxs-lookup"><span data-stu-id="4e290-103">PidTagSubfolders Canonical Property</span></span>

  
  
<span data-ttu-id="4e290-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4e290-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4e290-105">包含 TRUE，则文件夹包含子文件夹。</span><span class="sxs-lookup"><span data-stu-id="4e290-105">Contains TRUE if a folder contains subfolders.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4e290-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4e290-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4e290-107">PR_SUBFOLDERS</span><span class="sxs-lookup"><span data-stu-id="4e290-107">PR_SUBFOLDERS</span></span>  <br/> |
|<span data-ttu-id="4e290-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="4e290-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4e290-109">0x360A</span><span class="sxs-lookup"><span data-stu-id="4e290-109">0x360A</span></span>  <br/> |
|<span data-ttu-id="4e290-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4e290-110">Data type:</span></span>  <br/> |<span data-ttu-id="4e290-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="4e290-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="4e290-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4e290-112">Area:</span></span>  <br/> |<span data-ttu-id="4e290-113">MAPI 容器</span><span class="sxs-lookup"><span data-stu-id="4e290-113">MAPI container</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4e290-114">说明</span><span class="sxs-lookup"><span data-stu-id="4e290-114">Remarks</span></span>

<span data-ttu-id="4e290-115">消息存储必须提供此属性的所有文件夹。</span><span class="sxs-lookup"><span data-stu-id="4e290-115">Message stores must supply this property for all folders.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="4e290-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="4e290-116">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="4e290-117">协议规范</span><span class="sxs-lookup"><span data-stu-id="4e290-117">Protocol specifications</span></span>

<span data-ttu-id="4e290-118">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4e290-118">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4e290-119">提供了相关的 Exchange Server 协议规范参考。</span><span class="sxs-lookup"><span data-stu-id="4e290-119">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="4e290-120">[[MS OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="4e290-120">[[MS-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="4e290-121">处理文件夹的操作。</span><span class="sxs-lookup"><span data-stu-id="4e290-121">Handles folder operations.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="4e290-122">头文件</span><span class="sxs-lookup"><span data-stu-id="4e290-122">Header files</span></span>

<span data-ttu-id="4e290-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4e290-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="4e290-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4e290-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="4e290-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="4e290-125">Mapitags.h</span></span>
  
> <span data-ttu-id="4e290-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4e290-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4e290-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e290-127">See also</span></span>



[<span data-ttu-id="4e290-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4e290-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4e290-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4e290-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4e290-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4e290-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4e290-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4e290-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

