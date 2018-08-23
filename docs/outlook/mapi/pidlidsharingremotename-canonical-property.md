---
title: PidLidSharingRemoteName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidLidSharingRemoteName
api_type:
- COM
ms.assetid: be975f74-4b95-45a4-bbee-959fa8e4ad45
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: eddcc911653830f63ae4afc564af891d3d7213e2
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22595235"
---
# <a name="pidlidsharingremotename-canonical-property"></a><span data-ttu-id="cd991-103">PidLidSharingRemoteName 规范属性</span><span class="sxs-lookup"><span data-stu-id="cd991-103">PidLidSharingRemoteName Canonical Property</span></span>

  
  
<span data-ttu-id="cd991-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cd991-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cd991-105">指定共享远程文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="cd991-105">Specifies the name of the remote folder that is being shared.</span></span> <span data-ttu-id="cd991-106">这是邮件的共享的属性。</span><span class="sxs-lookup"><span data-stu-id="cd991-106">This is a property of a sharing message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="cd991-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="cd991-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="cd991-108">dispidSharingRemoteName</span><span class="sxs-lookup"><span data-stu-id="cd991-108">dispidSharingRemoteName</span></span>  <br/> |
|<span data-ttu-id="cd991-109">属性进行设置：</span><span class="sxs-lookup"><span data-stu-id="cd991-109">Property set:</span></span>  <br/> |<span data-ttu-id="cd991-110">PSETID_Sharing</span><span class="sxs-lookup"><span data-stu-id="cd991-110">PSETID_Sharing</span></span>  <br/> |
|<span data-ttu-id="cd991-111">长 ID （盖）：</span><span class="sxs-lookup"><span data-stu-id="cd991-111">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="cd991-112">0x00008A05</span><span class="sxs-lookup"><span data-stu-id="cd991-112">0x00008A05</span></span>  <br/> |
|<span data-ttu-id="cd991-113">数据类型：</span><span class="sxs-lookup"><span data-stu-id="cd991-113">Data type:</span></span>  <br/> |<span data-ttu-id="cd991-114">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="cd991-114">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="cd991-115">区域：</span><span class="sxs-lookup"><span data-stu-id="cd991-115">Area:</span></span>  <br/> |<span data-ttu-id="cd991-116">共享</span><span class="sxs-lookup"><span data-stu-id="cd991-116">Sharing</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cd991-117">注解</span><span class="sxs-lookup"><span data-stu-id="cd991-117">Remarks</span></span>

<span data-ttu-id="cd991-118">此属性必须设置为**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) 属性的值中，在共享文件夹中。</span><span class="sxs-lookup"><span data-stu-id="cd991-118">This property must be set to the value of the **PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md)) property on the folder being shared.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="cd991-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="cd991-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="cd991-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="cd991-120">Protocol specifications</span></span>

<span data-ttu-id="cd991-121">[[MS OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cd991-121">[[MS-OXPROPS]](http://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cd991-122">提供属性集定义和相关的 Exchange Server 协议规范的引用。</span><span class="sxs-lookup"><span data-stu-id="cd991-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="cd991-123">[[MS OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="cd991-123">[[MS-OXSHARE]](http://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="cd991-124">共享客户端之间的邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="cd991-124">Shares mailbox folders between clients.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="cd991-125">头文件</span><span class="sxs-lookup"><span data-stu-id="cd991-125">Header files</span></span>

<span data-ttu-id="cd991-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="cd991-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="cd991-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="cd991-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cd991-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd991-128">See also</span></span>



[<span data-ttu-id="cd991-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="cd991-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="cd991-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="cd991-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="cd991-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="cd991-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="cd991-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="cd991-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

