---
title: PidTagHasDeferredActionMessages 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagHasDeferredActionMessages
api_type:
- HeaderDef
ms.assetid: f9085c59-18b1-451d-85d7-b08377708a9d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 954a49a05b51a2b58ed4e7a2bb3f6609a3cdb6e0
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316119"
---
# <a name="pidtaghasdeferredactionmessages-canonical-property"></a><span data-ttu-id="48afb-103">PidTagHasDeferredActionMessages 规范属性</span><span class="sxs-lookup"><span data-stu-id="48afb-103">PidTagHasDeferredActionMessages Canonical Property</span></span>

  
  
<span data-ttu-id="48afb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="48afb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="48afb-105">如果邮件至少具有一个延迟操作规则，则包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="48afb-105">Contains TRUE if a message has at least one deferred action rule.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="48afb-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="48afb-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="48afb-107">PR_HAS_DAMS</span><span class="sxs-lookup"><span data-stu-id="48afb-107">PR_HAS_DAMS</span></span>  <br/> |
|<span data-ttu-id="48afb-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="48afb-108">Identifier:</span></span>  <br/> |<span data-ttu-id="48afb-109">0x3FEA</span><span class="sxs-lookup"><span data-stu-id="48afb-109">0x3FEA</span></span>  <br/> |
|<span data-ttu-id="48afb-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="48afb-110">Data type:</span></span>  <br/> |<span data-ttu-id="48afb-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="48afb-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="48afb-112">区域：</span><span class="sxs-lookup"><span data-stu-id="48afb-112">Area:</span></span>  <br/> |<span data-ttu-id="48afb-113">Rules</span><span class="sxs-lookup"><span data-stu-id="48afb-113">Rules</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="48afb-114">相关资源</span><span class="sxs-lookup"><span data-stu-id="48afb-114">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="48afb-115">协议规范</span><span class="sxs-lookup"><span data-stu-id="48afb-115">Protocol specifications</span></span>

<span data-ttu-id="48afb-116">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="48afb-116">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="48afb-117">提供对相关协议Exchange Server的引用。</span><span class="sxs-lookup"><span data-stu-id="48afb-117">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="48afb-118">[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="48afb-118">[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="48afb-119">在服务器上处理传入电子邮件。</span><span class="sxs-lookup"><span data-stu-id="48afb-119">Manipulates incoming email messages on a server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="48afb-120">头文件</span><span class="sxs-lookup"><span data-stu-id="48afb-120">Header files</span></span>

<span data-ttu-id="48afb-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="48afb-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="48afb-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="48afb-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="48afb-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="48afb-123">Mapitags.h</span></span>
  
> <span data-ttu-id="48afb-124">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="48afb-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="48afb-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="48afb-125">See also</span></span>



[<span data-ttu-id="48afb-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="48afb-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="48afb-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="48afb-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="48afb-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="48afb-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="48afb-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="48afb-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

