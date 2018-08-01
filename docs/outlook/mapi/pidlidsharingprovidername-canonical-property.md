---
title: PidLidSharingProviderName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingProviderName
api_type:
- COM
ms.assetid: 67e6497c-e053-4b2d-a81c-c6cf6017f8bd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a184207463e1f6139df2baa064101e8d2d8dc896
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777055"
---
# <a name="pidlidsharingprovidername-canonical-property"></a><span data-ttu-id="cc25f-103">PidLidSharingProviderName 规范属性</span><span class="sxs-lookup"><span data-stu-id="cc25f-103">PidLidSharingProviderName Canonical Property</span></span>

  
  
<span data-ttu-id="cc25f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="cc25f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="cc25f-105">指定由**dispidSharingProviderGuid** ([PidLidSharingProviderGuid](pidlidsharingproviderguid-canonical-property.md)) 标识的共享服务提供商的用户可显示名称。</span><span class="sxs-lookup"><span data-stu-id="cc25f-105">Specifies the user-displayable name of the sharing provider that is identified by **dispidSharingProviderGuid** ([PidLidSharingProviderGuid](pidlidsharingproviderguid-canonical-property.md)).</span></span> <span data-ttu-id="cc25f-106">这是邮件的共享的属性。</span><span class="sxs-lookup"><span data-stu-id="cc25f-106">This is a property of a sharing message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cc25f-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="cc25f-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="cc25f-108">dispidSharingProviderName</span><span class="sxs-lookup"><span data-stu-id="cc25f-108">dispidSharingProviderName</span></span>  <br/> |
|<span data-ttu-id="cc25f-109">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="cc25f-109">Property set:</span></span>  <br/> |<span data-ttu-id="cc25f-110">PSETID_Sharing</span><span class="sxs-lookup"><span data-stu-id="cc25f-110">PSETID_Sharing</span></span>  <br/> |
|<span data-ttu-id="cc25f-111">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="cc25f-111">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="cc25f-112">0x00008A02</span><span class="sxs-lookup"><span data-stu-id="cc25f-112">0x00008A02</span></span>  <br/> |
|<span data-ttu-id="cc25f-113">数据类型：</span><span class="sxs-lookup"><span data-stu-id="cc25f-113">Data type:</span></span>  <br/> |<span data-ttu-id="cc25f-114">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="cc25f-114">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="cc25f-115">区域：</span><span class="sxs-lookup"><span data-stu-id="cc25f-115">Area:</span></span>  <br/> |<span data-ttu-id="cc25f-116">共享</span><span class="sxs-lookup"><span data-stu-id="cc25f-116">Sharing</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cc25f-117">说明</span><span class="sxs-lookup"><span data-stu-id="cc25f-117">Remarks</span></span>

<span data-ttu-id="cc25f-118">应忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="cc25f-118">This property should be ignored.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="cc25f-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="cc25f-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="cc25f-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="cc25f-120">Protocol specifications</span></span>

<span data-ttu-id="cc25f-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cc25f-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cc25f-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="cc25f-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="cc25f-123">[[MS OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cc25f-123">[[MS-OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cc25f-124">共享客户端之间的邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="cc25f-124">Shares mailbox folders between clients.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="cc25f-125">头文件</span><span class="sxs-lookup"><span data-stu-id="cc25f-125">Header files</span></span>

<span data-ttu-id="cc25f-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="cc25f-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="cc25f-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="cc25f-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cc25f-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc25f-128">See also</span></span>



[<span data-ttu-id="cc25f-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="cc25f-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="cc25f-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="cc25f-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="cc25f-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="cc25f-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="cc25f-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cc25f-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

