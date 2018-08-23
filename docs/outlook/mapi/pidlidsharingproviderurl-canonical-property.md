---
title: PidLidSharingProviderUrl 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingProviderUrl
api_type:
- COM
ms.assetid: d217ab33-d697-4d27-a962-08d551d301f0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1b906ce83e26326755b483382eec8e494cbe7875
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577364"
---
# <a name="pidlidsharingproviderurl-canonical-property"></a><span data-ttu-id="172c8-103">PidLidSharingProviderUrl 规范属性</span><span class="sxs-lookup"><span data-stu-id="172c8-103">PidLidSharingProviderUrl Canonical Property</span></span>

  
  
<span data-ttu-id="172c8-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="172c8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="172c8-105">指定由**dispidSharingProviderGuid** ([PidLidSharingProviderGuid](pidlidsharingproviderguid-canonical-property.md)) 属性标识并与共享提供程序的 URL。</span><span class="sxs-lookup"><span data-stu-id="172c8-105">Specifies the URL that is related to the sharing provider and identified by the **dispidSharingProviderGuid** ([PidLidSharingProviderGuid](pidlidsharingproviderguid-canonical-property.md)) property.</span></span> <span data-ttu-id="172c8-106">这是邮件的共享的属性。</span><span class="sxs-lookup"><span data-stu-id="172c8-106">This is a property of a sharing message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="172c8-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="172c8-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="172c8-108">dispidSharingProviderUrl</span><span class="sxs-lookup"><span data-stu-id="172c8-108">dispidSharingProviderUrl</span></span>  <br/> |
|<span data-ttu-id="172c8-109">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="172c8-109">Property set:</span></span>  <br/> |<span data-ttu-id="172c8-110">PSETID_Sharing</span><span class="sxs-lookup"><span data-stu-id="172c8-110">PSETID_Sharing</span></span>  <br/> |
|<span data-ttu-id="172c8-111">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="172c8-111">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="172c8-112">0x00008A03</span><span class="sxs-lookup"><span data-stu-id="172c8-112">0x00008A03</span></span>  <br/> |
|<span data-ttu-id="172c8-113">数据类型：</span><span class="sxs-lookup"><span data-stu-id="172c8-113">Data type:</span></span>  <br/> |<span data-ttu-id="172c8-114">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="172c8-114">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="172c8-115">区域：</span><span class="sxs-lookup"><span data-stu-id="172c8-115">Area:</span></span>  <br/> |<span data-ttu-id="172c8-116">共享</span><span class="sxs-lookup"><span data-stu-id="172c8-116">Sharing</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="172c8-117">注解</span><span class="sxs-lookup"><span data-stu-id="172c8-117">Remarks</span></span>

<span data-ttu-id="172c8-118">此属性通常用于提供的共享提供程序，有关详细信息，但应忽略。</span><span class="sxs-lookup"><span data-stu-id="172c8-118">This property is generally used to provide more information about the sharing provider, but should be ignored.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="172c8-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="172c8-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="172c8-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="172c8-120">Protocol specifications</span></span>

<span data-ttu-id="172c8-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="172c8-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="172c8-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="172c8-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="172c8-123">[[MS OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="172c8-123">[[MS-OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="172c8-124">共享客户端之间的邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="172c8-124">Shares mailbox folders between clients.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="172c8-125">头文件</span><span class="sxs-lookup"><span data-stu-id="172c8-125">Header files</span></span>

<span data-ttu-id="172c8-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="172c8-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="172c8-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="172c8-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="172c8-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="172c8-128">See also</span></span>



[<span data-ttu-id="172c8-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="172c8-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="172c8-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="172c8-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="172c8-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="172c8-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="172c8-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="172c8-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

