---
title: PidLidSharingProviderGuid 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingProviderGuid
api_type:
- COM
ms.assetid: 103c9cf2-42fb-4fa5-b9c2-8a92725d3097
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: f3138a5994ffc6e32ffebd1a4d5b221db0dd2312
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777043"
---
# <a name="pidlidsharingproviderguid-canonical-property"></a><span data-ttu-id="12d6a-103">PidLidSharingProviderGuid 规范属性</span><span class="sxs-lookup"><span data-stu-id="12d6a-103">PidLidSharingProviderGuid Canonical Property</span></span>

  
  
<span data-ttu-id="12d6a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="12d6a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="12d6a-105">指定共享提供程序全局唯一标识符 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="12d6a-105">Specifies the sharing provider globally unique identifier (GUID).</span></span> <span data-ttu-id="12d6a-106">这是邮件的共享的属性。</span><span class="sxs-lookup"><span data-stu-id="12d6a-106">This is a property of a sharing message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="12d6a-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="12d6a-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="12d6a-108">dispidSharingProviderGuid</span><span class="sxs-lookup"><span data-stu-id="12d6a-108">dispidSharingProviderGuid</span></span>  <br/> |
|<span data-ttu-id="12d6a-109">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="12d6a-109">Property set:</span></span>  <br/> |<span data-ttu-id="12d6a-110">PSETID_Sharing</span><span class="sxs-lookup"><span data-stu-id="12d6a-110">PSETID_Sharing</span></span>  <br/> |
|<span data-ttu-id="12d6a-111">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="12d6a-111">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="12d6a-112">0x00008A01</span><span class="sxs-lookup"><span data-stu-id="12d6a-112">0x00008A01</span></span>  <br/> |
|<span data-ttu-id="12d6a-113">数据类型：</span><span class="sxs-lookup"><span data-stu-id="12d6a-113">Data type:</span></span>  <br/> |<span data-ttu-id="12d6a-114">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="12d6a-114">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="12d6a-115">区域：</span><span class="sxs-lookup"><span data-stu-id="12d6a-115">Area:</span></span>  <br/> |<span data-ttu-id="12d6a-116">共享</span><span class="sxs-lookup"><span data-stu-id="12d6a-116">Sharing</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="12d6a-117">说明</span><span class="sxs-lookup"><span data-stu-id="12d6a-117">Remarks</span></span>

<span data-ttu-id="12d6a-118">此属性的值必须设置为"%xae.f0.06.00.00.00.00.00.c0.00.00.00.00.00.00.46"。</span><span class="sxs-lookup"><span data-stu-id="12d6a-118">The value of this property must be set to "%xAE.F0.06.00.00.00.00.00.C0.00.00.00.00.00.00.46".</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="12d6a-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="12d6a-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="12d6a-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="12d6a-120">Protocol specifications</span></span>

<span data-ttu-id="12d6a-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="12d6a-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="12d6a-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="12d6a-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="12d6a-123">[[MS OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="12d6a-123">[[MS-OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="12d6a-124">共享客户端之间的邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="12d6a-124">Shares mailbox folders between clients.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="12d6a-125">头文件</span><span class="sxs-lookup"><span data-stu-id="12d6a-125">Header files</span></span>

<span data-ttu-id="12d6a-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="12d6a-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="12d6a-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="12d6a-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="12d6a-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="12d6a-128">See also</span></span>



[<span data-ttu-id="12d6a-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="12d6a-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="12d6a-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="12d6a-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="12d6a-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="12d6a-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="12d6a-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="12d6a-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

