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
ms.openlocfilehash: 68a1fef672b4f32c6ff0ebfea56bf240b7281f0f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32336881"
---
# <a name="pidlidsharingproviderguid-canonical-property"></a><span data-ttu-id="2fa34-103">PidLidSharingProviderGuid 规范属性</span><span class="sxs-lookup"><span data-stu-id="2fa34-103">PidLidSharingProviderGuid Canonical Property</span></span>

  
  
<span data-ttu-id="2fa34-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2fa34-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2fa34-105">指定共享提供程序全局唯一标识符 (GUID) 。</span><span class="sxs-lookup"><span data-stu-id="2fa34-105">Specifies the sharing provider globally unique identifier (GUID).</span></span> <span data-ttu-id="2fa34-106">这是共享邮件的属性。</span><span class="sxs-lookup"><span data-stu-id="2fa34-106">This is a property of a sharing message.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2fa34-107">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2fa34-107">Associated properties:</span></span>  <br/> |<span data-ttu-id="2fa34-108">dispidSharingProviderGuid</span><span class="sxs-lookup"><span data-stu-id="2fa34-108">dispidSharingProviderGuid</span></span>  <br/> |
|<span data-ttu-id="2fa34-109">属性集：</span><span class="sxs-lookup"><span data-stu-id="2fa34-109">Property set:</span></span>  <br/> |<span data-ttu-id="2fa34-110">PSETID_Sharing</span><span class="sxs-lookup"><span data-stu-id="2fa34-110">PSETID_Sharing</span></span>  <br/> |
|<span data-ttu-id="2fa34-111">LONG ID (的一) ：</span><span class="sxs-lookup"><span data-stu-id="2fa34-111">Long ID (LID):</span></span>  <br/> |<span data-ttu-id="2fa34-112">0x00008A01</span><span class="sxs-lookup"><span data-stu-id="2fa34-112">0x00008A01</span></span>  <br/> |
|<span data-ttu-id="2fa34-113">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2fa34-113">Data type:</span></span>  <br/> |<span data-ttu-id="2fa34-114">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="2fa34-114">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="2fa34-115">区域：</span><span class="sxs-lookup"><span data-stu-id="2fa34-115">Area:</span></span>  <br/> |<span data-ttu-id="2fa34-116">共享</span><span class="sxs-lookup"><span data-stu-id="2fa34-116">Sharing</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2fa34-117">备注</span><span class="sxs-lookup"><span data-stu-id="2fa34-117">Remarks</span></span>

<span data-ttu-id="2fa34-118">此属性的值必须设置为"%xAE.F0.06.00.00.00.00.00.C0.00.00.00.00.00.46"。</span><span class="sxs-lookup"><span data-stu-id="2fa34-118">The value of this property must be set to "%xAE.F0.06.00.00.00.00.00.C0.00.00.00.00.00.00.46".</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="2fa34-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="2fa34-119">Related resources</span></span>

### <a name="protocol-specifications"></a><span data-ttu-id="2fa34-120">协议规范</span><span class="sxs-lookup"><span data-stu-id="2fa34-120">Protocol specifications</span></span>

<span data-ttu-id="2fa34-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2fa34-121">[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2fa34-122">提供属性集定义和对相关协议规范Exchange Server引用。</span><span class="sxs-lookup"><span data-stu-id="2fa34-122">Provides property set definitions and references to related Exchange Server protocol specifications.</span></span>
    
<span data-ttu-id="2fa34-123">[[MS-OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="2fa34-123">[[MS-OXSHARE]](https://msdn.microsoft.com/library/e4e5bd27-d5e0-43f9-a6ea-550876724f3d%28Office.15%29.aspx)</span></span>
  
> <span data-ttu-id="2fa34-124">在客户端之间共享邮箱文件夹。</span><span class="sxs-lookup"><span data-stu-id="2fa34-124">Shares mailbox folders between clients.</span></span>
    
### <a name="header-files"></a><span data-ttu-id="2fa34-125">头文件</span><span class="sxs-lookup"><span data-stu-id="2fa34-125">Header files</span></span>

<span data-ttu-id="2fa34-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2fa34-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="2fa34-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2fa34-127">Provides data type definitions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2fa34-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2fa34-128">See also</span></span>



[<span data-ttu-id="2fa34-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2fa34-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2fa34-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2fa34-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2fa34-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2fa34-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2fa34-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2fa34-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

