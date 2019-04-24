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
# <a name="pidtaghasdeferredactionmessages-canonical-property"></a><span data-ttu-id="19d84-103">PidTagHasDeferredActionMessages 规范属性</span><span class="sxs-lookup"><span data-stu-id="19d84-103">PidTagHasDeferredActionMessages Canonical Property</span></span>

  
  
<span data-ttu-id="19d84-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="19d84-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="19d84-105">如果邮件至少有一个延迟操作规则, 则包含 TRUE。</span><span class="sxs-lookup"><span data-stu-id="19d84-105">Contains TRUE if a message has at least one deferred action rule.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="19d84-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="19d84-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="19d84-107">PR_HAS_DAMS</span><span class="sxs-lookup"><span data-stu-id="19d84-107">PR_HAS_DAMS</span></span>  <br/> |
|<span data-ttu-id="19d84-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="19d84-108">Identifier:</span></span>  <br/> |<span data-ttu-id="19d84-109">0x3FEA</span><span class="sxs-lookup"><span data-stu-id="19d84-109">0x3FEA</span></span>  <br/> |
|<span data-ttu-id="19d84-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="19d84-110">Data type:</span></span>  <br/> |<span data-ttu-id="19d84-111">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="19d84-111">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="19d84-112">区域：</span><span class="sxs-lookup"><span data-stu-id="19d84-112">Area:</span></span>  <br/> |<span data-ttu-id="19d84-113">规则</span><span class="sxs-lookup"><span data-stu-id="19d84-113">Rules</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="19d84-114">相关资源</span><span class="sxs-lookup"><span data-stu-id="19d84-114">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="19d84-115">协议规范</span><span class="sxs-lookup"><span data-stu-id="19d84-115">Protocol specifications</span></span>

<span data-ttu-id="19d84-116">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="19d84-116">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="19d84-117">提供对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="19d84-117">Provides references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="19d84-118">[[毫秒-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="19d84-118">[[MS-OXORULE]](https://msdn.microsoft.com/library/70ac9436-501e-43e2-9163-20d2b546b886%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="19d84-119">在服务器上操纵传入电子邮件。</span><span class="sxs-lookup"><span data-stu-id="19d84-119">Manipulates incoming email messages on a server.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="19d84-120">头文件</span><span class="sxs-lookup"><span data-stu-id="19d84-120">Header files</span></span>

<span data-ttu-id="19d84-121">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="19d84-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="19d84-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="19d84-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="19d84-123">Mapitags</span><span class="sxs-lookup"><span data-stu-id="19d84-123">Mapitags.h</span></span>
  
> <span data-ttu-id="19d84-124">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="19d84-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="19d84-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19d84-125">See also</span></span>



[<span data-ttu-id="19d84-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="19d84-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="19d84-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="19d84-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="19d84-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="19d84-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="19d84-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="19d84-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

