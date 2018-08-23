---
title: PidTagProviderOrdinal 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagProviderOrdinal
api_type:
- COM
ms.assetid: d062b54d-7c32-4369-ab69-f7193773a1c0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 4cd865fbc443a20ebf4b4cd9722fe52c44d5eddc
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573808"
---
# <a name="pidtagproviderordinal-canonical-property"></a><span data-ttu-id="47f99-103">PidTagProviderOrdinal 规范属性</span><span class="sxs-lookup"><span data-stu-id="47f99-103">PidTagProviderOrdinal Canonical Property</span></span>

  
  
<span data-ttu-id="47f99-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="47f99-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="47f99-105">包含服务提供商的提供程序表中的位置的从零开始的索引。</span><span class="sxs-lookup"><span data-stu-id="47f99-105">Contains the zero-based index of a service provider's position in the provider table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="47f99-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="47f99-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="47f99-107">PR_PROVIDER_ORDINAL</span><span class="sxs-lookup"><span data-stu-id="47f99-107">PR_PROVIDER_ORDINAL</span></span>  <br/> |
|<span data-ttu-id="47f99-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="47f99-108">Identifier:</span></span>  <br/> |<span data-ttu-id="47f99-109">0x300D</span><span class="sxs-lookup"><span data-stu-id="47f99-109">0x300D</span></span>  <br/> |
|<span data-ttu-id="47f99-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="47f99-110">Data type:</span></span>  <br/> |<span data-ttu-id="47f99-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="47f99-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="47f99-112">区域：</span><span class="sxs-lookup"><span data-stu-id="47f99-112">Area:</span></span>  <br/> |<span data-ttu-id="47f99-113">常见的 MAPI</span><span class="sxs-lookup"><span data-stu-id="47f99-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="47f99-114">注解</span><span class="sxs-lookup"><span data-stu-id="47f99-114">Remarks</span></span>

<span data-ttu-id="47f99-115">通过 MAPI 计算此属性。</span><span class="sxs-lookup"><span data-stu-id="47f99-115">This property is computed by MAPI.</span></span>
  
<span data-ttu-id="47f99-116">通过调用[IMsgServiceAdmin::GetProviderTable](imsgserviceadmin-getprovidertable.md)方法来获取提供程序表中。</span><span class="sxs-lookup"><span data-stu-id="47f99-116">Obtain the provider table by calling the [IMsgServiceAdmin::GetProviderTable](imsgserviceadmin-getprovidertable.md) method.</span></span> <span data-ttu-id="47f99-117">此属性以显示传输顺序在提供程序表格进行排序。</span><span class="sxs-lookup"><span data-stu-id="47f99-117">Sort the provider table on this property to display the transport order.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="47f99-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="47f99-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="47f99-119">头文件</span><span class="sxs-lookup"><span data-stu-id="47f99-119">Header files</span></span>

<span data-ttu-id="47f99-120">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="47f99-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="47f99-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="47f99-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="47f99-122">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="47f99-122">Mapitags.h</span></span>
  
> <span data-ttu-id="47f99-123">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="47f99-123">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="47f99-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47f99-124">See also</span></span>



[<span data-ttu-id="47f99-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="47f99-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="47f99-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="47f99-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="47f99-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="47f99-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="47f99-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="47f99-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

