---
title: PidTagServiceExtraUids 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagServiceExtraUids
api_type:
- COM
ms.assetid: 4838a9af-7818-49aa-ace8-cb94dda8471f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 71f802014200d4b767c346c14df53f1193d44b0d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778406"
---
# <a name="pidtagserviceextrauids-canonical-property"></a><span data-ttu-id="3d4ae-103">PidTagServiceExtraUids 规范属性</span><span class="sxs-lookup"><span data-stu-id="3d4ae-103">PidTagServiceExtraUids Canonical Property</span></span>

  
  
<span data-ttu-id="3d4ae-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3d4ae-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3d4ae-105">包含标识邮件服务的其他配置文件部分的[MAPIUID](mapiuid.md)结构的列表。</span><span class="sxs-lookup"><span data-stu-id="3d4ae-105">Contains a list of [MAPIUID](mapiuid.md) structures that identify additional profile sections for the message service.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3d4ae-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3d4ae-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3d4ae-107">PR_SERVICE_EXTRA_UIDS</span><span class="sxs-lookup"><span data-stu-id="3d4ae-107">PR_SERVICE_EXTRA_UIDS</span></span>  <br/> |
|<span data-ttu-id="3d4ae-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="3d4ae-108">Identifier:</span></span>  <br/> |<span data-ttu-id="3d4ae-109">0x3D0D</span><span class="sxs-lookup"><span data-stu-id="3d4ae-109">0x3D0D</span></span>  <br/> |
|<span data-ttu-id="3d4ae-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3d4ae-110">Data type:</span></span>  <br/> |<span data-ttu-id="3d4ae-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="3d4ae-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="3d4ae-112">区域：</span><span class="sxs-lookup"><span data-stu-id="3d4ae-112">Area:</span></span>  <br/> |<span data-ttu-id="3d4ae-113">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="3d4ae-113">MAPI profile</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3d4ae-114">说明</span><span class="sxs-lookup"><span data-stu-id="3d4ae-114">Remarks</span></span>

<span data-ttu-id="3d4ae-115">可以为每个邮件筛选器创建新的配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="3d4ae-115">New profile sections can be created for each message filter.</span></span> <span data-ttu-id="3d4ae-116">当邮件服务的信息复制到另一个配置文件时，务必要复制的筛选器以及其他配置文件部分。</span><span class="sxs-lookup"><span data-stu-id="3d4ae-116">When the information about the message service is to be copied to another profile, it is important to copy the additional profile sections for the filters as well.</span></span> <span data-ttu-id="3d4ae-117">使用其他配置文件节的服务提供商可以存储这些配置文件节的**MAPIUID**结构中**PR_SERVICE_EXTRA_UIDS**，它允许 MAPI 复制其他消息服务信息。</span><span class="sxs-lookup"><span data-stu-id="3d4ae-117">A service provider that uses additional profile sections can store the **MAPIUID** structures of those profile sections in **PR_SERVICE_EXTRA_UIDS**, which allows MAPI to copy the additional message service information.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="3d4ae-118">相关资源</span><span class="sxs-lookup"><span data-stu-id="3d4ae-118">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="3d4ae-119">头文件</span><span class="sxs-lookup"><span data-stu-id="3d4ae-119">Header files</span></span>

<span data-ttu-id="3d4ae-120">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3d4ae-120">Mapidefs.h</span></span>
  
> <span data-ttu-id="3d4ae-121">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3d4ae-121">Provides data type definitions.</span></span>
    
<span data-ttu-id="3d4ae-122">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="3d4ae-122">Mapitags.h</span></span>
  
> <span data-ttu-id="3d4ae-123">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="3d4ae-123">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3d4ae-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d4ae-124">See also</span></span>



[<span data-ttu-id="3d4ae-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3d4ae-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3d4ae-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3d4ae-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3d4ae-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3d4ae-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3d4ae-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3d4ae-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

