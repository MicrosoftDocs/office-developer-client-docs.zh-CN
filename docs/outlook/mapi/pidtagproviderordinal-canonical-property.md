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
ms.openlocfilehash: b56ee557884e12728c98827f9eb1a280d7a29c30
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778089"
---
# <a name="pidtagproviderordinal-canonical-property"></a><span data-ttu-id="7f706-103">PidTagProviderOrdinal 规范属性</span><span class="sxs-lookup"><span data-stu-id="7f706-103">PidTagProviderOrdinal Canonical Property</span></span>

  
  
<span data-ttu-id="7f706-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="7f706-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="7f706-105">包含服务提供商的提供程序表中的位置的从零开始的索引。</span><span class="sxs-lookup"><span data-stu-id="7f706-105">Contains the zero-based index of a service provider's position in the provider table.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7f706-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7f706-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7f706-107">PR_PROVIDER_ORDINAL</span><span class="sxs-lookup"><span data-stu-id="7f706-107">PR_PROVIDER_ORDINAL</span></span>  <br/> |
|<span data-ttu-id="7f706-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="7f706-108">Identifier:</span></span>  <br/> |<span data-ttu-id="7f706-109">0x300D</span><span class="sxs-lookup"><span data-stu-id="7f706-109">0x300D</span></span>  <br/> |
|<span data-ttu-id="7f706-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7f706-110">Data type:</span></span>  <br/> |<span data-ttu-id="7f706-111">PT_LONG</span><span class="sxs-lookup"><span data-stu-id="7f706-111">PT_LONG</span></span>  <br/> |
|<span data-ttu-id="7f706-112">区域：</span><span class="sxs-lookup"><span data-stu-id="7f706-112">Area:</span></span>  <br/> |<span data-ttu-id="7f706-113">常见的 MAPI</span><span class="sxs-lookup"><span data-stu-id="7f706-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7f706-114">说明</span><span class="sxs-lookup"><span data-stu-id="7f706-114">Remarks</span></span>

<span data-ttu-id="7f706-115">通过 MAPI 计算此属性。</span><span class="sxs-lookup"><span data-stu-id="7f706-115">This property is computed by MAPI.</span></span>
  
<span data-ttu-id="7f706-116">通过调用[IMsgServiceAdmin::GetProviderTable](imsgserviceadmin-getprovidertable.md)方法来获取提供程序表中。</span><span class="sxs-lookup"><span data-stu-id="7f706-116">Obtain the provider table by calling the [IMsgServiceAdmin::GetProviderTable](imsgserviceadmin-getprovidertable.md) method.</span></span> <span data-ttu-id="7f706-117">此属性以显示传输顺序在提供程序表格进行排序。</span><span class="sxs-lookup"><span data-stu-id="7f706-117">Sort the provider table on this property to display the transport order.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="7f706-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="7f706-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="7f706-119">头文件</span><span class="sxs-lookup"><span data-stu-id="7f706-119">Header files</span></span>

<span data-ttu-id="7f706-120">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7f706-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="7f706-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7f706-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="7f706-122">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="7f706-122">Mapitags.h</span></span>
  
> <span data-ttu-id="7f706-123">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="7f706-123">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7f706-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7f706-124">See also</span></span>



[<span data-ttu-id="7f706-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7f706-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7f706-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7f706-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7f706-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7f706-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7f706-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7f706-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

