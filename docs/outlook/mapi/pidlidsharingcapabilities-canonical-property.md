---
title: PidLidSharingCapabilities 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingCapabilities
api_type:
- COM
ms.assetid: 86b3eab2-2594-4204-aedf-8ce2ee3b81ce
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d44851e1c863cb117eed3462eb98de87f8d1f0be
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358889"
---
# <a name="pidlidsharingcapabilities-canonical-property"></a><span data-ttu-id="7845c-103">PidLidSharingCapabilities 规范属性</span><span class="sxs-lookup"><span data-stu-id="7845c-103">PidLidSharingCapabilities Canonical Property</span></span>

  
  
<span data-ttu-id="7845c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7845c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7845c-105">指定为共享邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="7845c-105">Designates as a property of a sharing message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7845c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7845c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7845c-107">dispidSharingCaps</span><span class="sxs-lookup"><span data-stu-id="7845c-107">dispidSharingCaps</span></span>  <br/> |
|<span data-ttu-id="7845c-108">属性集:</span><span class="sxs-lookup"><span data-stu-id="7845c-108">Property set:</span></span>  <br/> |<span data-ttu-id="7845c-109">PSETID_Sharing</span><span class="sxs-lookup"><span data-stu-id="7845c-109">PSETID_Sharing</span></span>  <br/> |
|<span data-ttu-id="7845c-110">长 ID (盖子):</span><span class="sxs-lookup"><span data-stu-id="7845c-110">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="7845c-111">0x00008A17</span><span class="sxs-lookup"><span data-stu-id="7845c-111">0x00008A17</span></span>  <br/> |
|<span data-ttu-id="7845c-112">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7845c-112">Data type:</span></span>  <br/> |<span data-ttu-id="7845c-113">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="7845c-113">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="7845c-114">区域：</span><span class="sxs-lookup"><span data-stu-id="7845c-114">Area:</span></span>  <br/> |<span data-ttu-id="7845c-115">共享</span><span class="sxs-lookup"><span data-stu-id="7845c-115">Sharing</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7845c-116">注解</span><span class="sxs-lookup"><span data-stu-id="7845c-116">Remarks</span></span>

<span data-ttu-id="7845c-117">此属性必须设置为以下值之一:</span><span class="sxs-lookup"><span data-stu-id="7845c-117">This property must be set to one of the following values:</span></span>
  
|<span data-ttu-id="7845c-118">**值**</span><span class="sxs-lookup"><span data-stu-id="7845c-118">**Value**</span></span>|<span data-ttu-id="7845c-119">**应用场景**</span><span class="sxs-lookup"><span data-stu-id="7845c-119">**Scenario**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7845c-120">0x00040290</span><span class="sxs-lookup"><span data-stu-id="7845c-120">0x00040290</span></span>  <br/> |<span data-ttu-id="7845c-121">此共享邮件对象与特殊文件夹相关。</span><span class="sxs-lookup"><span data-stu-id="7845c-121">This Sharing Message object relates to a special folder.</span></span>  <br/> |
|<span data-ttu-id="7845c-122">0x000402B0</span><span class="sxs-lookup"><span data-stu-id="7845c-122">0x000402B0</span></span>  <br/> |<span data-ttu-id="7845c-123">此共享邮件对象与特殊文件夹无关。</span><span class="sxs-lookup"><span data-stu-id="7845c-123">This Sharing Message object does not relate to a special folder.</span></span>  <br/> |
   
## <a name="related-resources"></a><span data-ttu-id="7845c-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="7845c-124">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="7845c-125">协议规范</span><span class="sxs-lookup"><span data-stu-id="7845c-125">Protocol specifications</span></span>

<span data-ttu-id="7845c-126">[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7845c-126">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7845c-127">提供属性集定义和对相关 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="7845c-127">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="7845c-128">[[毫秒-OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="7845c-128">[[MS-OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="7845c-129">在客户端之间共享邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="7845c-129">Shares mailbox folders between clients.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="7845c-130">头文件</span><span class="sxs-lookup"><span data-stu-id="7845c-130">Header files</span></span>

<span data-ttu-id="7845c-131">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="7845c-131">Mapidefs.h</span></span>
  
> <span data-ttu-id="7845c-132">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7845c-132">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7845c-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7845c-133">See also</span></span>



[<span data-ttu-id="7845c-134">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7845c-134">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7845c-135">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7845c-135">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7845c-136">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7845c-136">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7845c-137">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7845c-137">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

