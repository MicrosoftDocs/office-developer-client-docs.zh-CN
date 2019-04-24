---
title: PidTagServiceName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagServiceName
api_type:
- COM
ms.assetid: 9a63d647-7504-42fc-b317-6b02b89070eb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e5659113b1c6579913042ae0c8dfcd03e9802621
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359477"
---
# <a name="pidtagservicename-canonical-property"></a><span data-ttu-id="3a3bc-103">PidTagServiceName 规范属性</span><span class="sxs-lookup"><span data-stu-id="3a3bc-103">PidTagServiceName Canonical Property</span></span>

  
  
<span data-ttu-id="3a3bc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3a3bc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3a3bc-105">包含由用户在 mapisvc.inf 文件中设置的邮件服务的名称。</span><span class="sxs-lookup"><span data-stu-id="3a3bc-105">Contains the name of a message service as set by the user in the MapiSvc.inf file.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3a3bc-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3a3bc-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3a3bc-107">PR_SERVICE_NAME、PR_SERVICE_NAME_A、PR_SERVICE_NAME_W</span><span class="sxs-lookup"><span data-stu-id="3a3bc-107">PR_SERVICE_NAME, PR_SERVICE_NAME_A, PR_SERVICE_NAME_W</span></span>  <br/> |
|<span data-ttu-id="3a3bc-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="3a3bc-108">Identifier:</span></span>  <br/> |<span data-ttu-id="3a3bc-109">0x3D09</span><span class="sxs-lookup"><span data-stu-id="3a3bc-109">0x3D09</span></span>  <br/> |
|<span data-ttu-id="3a3bc-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3a3bc-110">Data type:</span></span>  <br/> |<span data-ttu-id="3a3bc-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="3a3bc-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="3a3bc-112">区域：</span><span class="sxs-lookup"><span data-stu-id="3a3bc-112">Area:</span></span>  <br/> |<span data-ttu-id="3a3bc-113">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="3a3bc-113">MAPI profile</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3a3bc-114">注解</span><span class="sxs-lookup"><span data-stu-id="3a3bc-114">Remarks</span></span>

<span data-ttu-id="3a3bc-115">这些属性中包含的名称特定于邮件服务。</span><span class="sxs-lookup"><span data-stu-id="3a3bc-115">The name contained in these properties is specific to the message service.</span></span> <span data-ttu-id="3a3bc-116">它来自 mapisvc.inf 中的 "服务" 部分。</span><span class="sxs-lookup"><span data-stu-id="3a3bc-116">It comes from the [Services] section in MapiSvc.inf.</span></span>
  
<span data-ttu-id="3a3bc-117">这些属性在邮件服务表中显示为一列, 可用于筛选服务。</span><span class="sxs-lookup"><span data-stu-id="3a3bc-117">These properties appear as a column in the message service table and can be used to filter services.</span></span> <span data-ttu-id="3a3bc-118">由于它用于标识和筛选服务, 因此不应本地化该值。</span><span class="sxs-lookup"><span data-stu-id="3a3bc-118">Because it is used to identify and filter services, the value should not be localized.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="3a3bc-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="3a3bc-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="3a3bc-120">头文件</span><span class="sxs-lookup"><span data-stu-id="3a3bc-120">Header files</span></span>

<span data-ttu-id="3a3bc-121">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="3a3bc-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="3a3bc-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3a3bc-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="3a3bc-123">Mapitags</span><span class="sxs-lookup"><span data-stu-id="3a3bc-123">Mapitags.h</span></span>
  
> <span data-ttu-id="3a3bc-124">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="3a3bc-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3a3bc-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a3bc-125">See also</span></span>



[<span data-ttu-id="3a3bc-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3a3bc-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3a3bc-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3a3bc-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3a3bc-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3a3bc-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3a3bc-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3a3bc-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

