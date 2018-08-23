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
ms.openlocfilehash: d950ee21c0c4c41e84c0fe1f8104219e63f84cec
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592673"
---
# <a name="pidtagservicename-canonical-property"></a><span data-ttu-id="61dae-103">PidTagServiceName 规范属性</span><span class="sxs-lookup"><span data-stu-id="61dae-103">PidTagServiceName Canonical Property</span></span>

  
  
<span data-ttu-id="61dae-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="61dae-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="61dae-105">包含由 MapiSvc.inf 文件中的用户设置消息服务的名称。</span><span class="sxs-lookup"><span data-stu-id="61dae-105">Contains the name of a message service as set by the user in the MapiSvc.inf file.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="61dae-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="61dae-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="61dae-107">PR_SERVICE_NAME，PR_SERVICE_NAME_A，PR_SERVICE_NAME_W</span><span class="sxs-lookup"><span data-stu-id="61dae-107">PR_SERVICE_NAME, PR_SERVICE_NAME_A, PR_SERVICE_NAME_W</span></span>  <br/> |
|<span data-ttu-id="61dae-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="61dae-108">Identifier:</span></span>  <br/> |<span data-ttu-id="61dae-109">0x3D09</span><span class="sxs-lookup"><span data-stu-id="61dae-109">0x3D09</span></span>  <br/> |
|<span data-ttu-id="61dae-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="61dae-110">Data type:</span></span>  <br/> |<span data-ttu-id="61dae-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="61dae-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="61dae-112">区域：</span><span class="sxs-lookup"><span data-stu-id="61dae-112">Area:</span></span>  <br/> |<span data-ttu-id="61dae-113">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="61dae-113">MAPI profile</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="61dae-114">注解</span><span class="sxs-lookup"><span data-stu-id="61dae-114">Remarks</span></span>

<span data-ttu-id="61dae-115">这些属性中包含的名称是特定于邮件服务。</span><span class="sxs-lookup"><span data-stu-id="61dae-115">The name contained in these properties is specific to the message service.</span></span> <span data-ttu-id="61dae-116">来自 MapiSvc.inf 中的 [服务] 一节。</span><span class="sxs-lookup"><span data-stu-id="61dae-116">It comes from the [Services] section in MapiSvc.inf.</span></span>
  
<span data-ttu-id="61dae-117">这些属性显示为邮件服务表中的列，并且可用于筛选的服务。</span><span class="sxs-lookup"><span data-stu-id="61dae-117">These properties appear as a column in the message service table and can be used to filter services.</span></span> <span data-ttu-id="61dae-118">因为它用于标识和筛选服务，不应本地化值。</span><span class="sxs-lookup"><span data-stu-id="61dae-118">Because it is used to identify and filter services, the value should not be localized.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="61dae-119">相关资源</span><span class="sxs-lookup"><span data-stu-id="61dae-119">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="61dae-120">头文件</span><span class="sxs-lookup"><span data-stu-id="61dae-120">Header files</span></span>

<span data-ttu-id="61dae-121">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="61dae-121">Mapidefs.h</span></span>
  
> <span data-ttu-id="61dae-122">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="61dae-122">Provides data type definitions.</span></span>
    
<span data-ttu-id="61dae-123">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="61dae-123">Mapitags.h</span></span>
  
> <span data-ttu-id="61dae-124">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="61dae-124">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="61dae-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="61dae-125">See also</span></span>



[<span data-ttu-id="61dae-126">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="61dae-126">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="61dae-127">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="61dae-127">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="61dae-128">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="61dae-128">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="61dae-129">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="61dae-129">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

