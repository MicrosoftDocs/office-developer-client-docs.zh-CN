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
ms.openlocfilehash: 0e5a3a242938d851ce3248ef5f1eeb8da27c801e
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25386115"
---
# <a name="pidlidsharingprovidername-canonical-property"></a><span data-ttu-id="0c667-103">PidLidSharingProviderName 规范属性</span><span class="sxs-lookup"><span data-stu-id="0c667-103">PidLidSharingProviderName Canonical Property</span></span>

  
  
<span data-ttu-id="0c667-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="0c667-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="0c667-105">指定由**dispidSharingProviderGuid** ([PidLidSharingProviderGuid](pidlidsharingproviderguid-canonical-property.md)) 标识的共享服务提供商的用户可显示名称。</span><span class="sxs-lookup"><span data-stu-id="0c667-105">Specifies the user-displayable name of the sharing provider that is identified by **dispidSharingProviderGuid** ([PidLidSharingProviderGuid](pidlidsharingproviderguid-canonical-property.md)).</span></span> <span data-ttu-id="0c667-106">这是邮件的共享的属性。</span><span class="sxs-lookup"><span data-stu-id="0c667-106">This is a property of a sharing message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="0c667-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0c667-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="0c667-108">dispidSharingProviderName</span><span class="sxs-lookup"><span data-stu-id="0c667-108">dispidSharingProviderName</span></span>  <br/> |
|<span data-ttu-id="0c667-109">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="0c667-109">Property set:</span></span>  <br/> |<span data-ttu-id="0c667-110">PSETID_Sharing</span><span class="sxs-lookup"><span data-stu-id="0c667-110">PSETID_Sharing</span></span>  <br/> |
|<span data-ttu-id="0c667-111">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="0c667-111">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="0c667-112">0x00008A02</span><span class="sxs-lookup"><span data-stu-id="0c667-112">0x00008A02</span></span>  <br/> |
|<span data-ttu-id="0c667-113">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0c667-113">Data type:</span></span>  <br/> |<span data-ttu-id="0c667-114">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="0c667-114">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="0c667-115">区域：</span><span class="sxs-lookup"><span data-stu-id="0c667-115">Area:</span></span>  <br/> |<span data-ttu-id="0c667-116">共享</span><span class="sxs-lookup"><span data-stu-id="0c667-116">Sharing</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0c667-117">说明</span><span class="sxs-lookup"><span data-stu-id="0c667-117">Remarks</span></span>

<span data-ttu-id="0c667-118">应忽略此属性。</span><span class="sxs-lookup"><span data-stu-id="0c667-118">This property should be ignored.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="0c667-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="0c667-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="0c667-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="0c667-120">Protocol specifications</span></span>

<span data-ttu-id="0c667-121">[[MS OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0c667-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0c667-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="0c667-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="0c667-123">[[MS OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="0c667-123">[[MS-OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="0c667-124">共享客户端之间的邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="0c667-124">Shares mailbox folders between clients.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="0c667-125">头文件</span><span class="sxs-lookup"><span data-stu-id="0c667-125">Header files</span></span>

<span data-ttu-id="0c667-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0c667-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="0c667-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0c667-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0c667-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c667-128">See also</span></span>



[<span data-ttu-id="0c667-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0c667-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0c667-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0c667-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0c667-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0c667-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0c667-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0c667-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

