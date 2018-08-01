---
title: PidTagResourcePath 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagResourcePath
api_type:
- COM
ms.assetid: ac49538e-6ee8-4ab4-9d79-88a83c7d0149
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d7385ea403e7ea45c97f6fd98e422ad7eb762c4c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778227"
---
# <a name="pidtagresourcepath-canonical-property"></a><span data-ttu-id="1166c-103">PidTagResourcePath 规范属性</span><span class="sxs-lookup"><span data-stu-id="1166c-103">PidTagResourcePath Canonical Property</span></span>

  
  
<span data-ttu-id="1166c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="1166c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="1166c-105">包含服务提供商的服务器的路径。</span><span class="sxs-lookup"><span data-stu-id="1166c-105">Contains a path to the service provider's server.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="1166c-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="1166c-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="1166c-107">PR_RESOURCE_PATH，PR_RESOURCE_PATH_A，PR_RESOURCE_PATH_W</span><span class="sxs-lookup"><span data-stu-id="1166c-107">PR_RESOURCE_PATH, PR_RESOURCE_PATH_A, PR_RESOURCE_PATH_W</span></span>  <br/> |
|<span data-ttu-id="1166c-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="1166c-108">Identifier:</span></span>  <br/> |<span data-ttu-id="1166c-109">0x3E07</span><span class="sxs-lookup"><span data-stu-id="1166c-109">0x3E07</span></span>  <br/> |
|<span data-ttu-id="1166c-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="1166c-110">Data type:</span></span>  <br/> |<span data-ttu-id="1166c-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="1166c-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="1166c-112">区域：</span><span class="sxs-lookup"><span data-stu-id="1166c-112">Area:</span></span>  <br/> |<span data-ttu-id="1166c-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="1166c-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1166c-114">说明</span><span class="sxs-lookup"><span data-stu-id="1166c-114">Remarks</span></span>

<span data-ttu-id="1166c-115">这些属性中包含的路径代表所建议的路径，用户可以在何处找到资源。</span><span class="sxs-lookup"><span data-stu-id="1166c-115">The path contained in these properties represents the suggested path where the user can find resources.</span></span> <span data-ttu-id="1166c-116">提供程序特定的这些属性定义。</span><span class="sxs-lookup"><span data-stu-id="1166c-116">The definition of these properties is provider specific.</span></span> <span data-ttu-id="1166c-117">例如，计划应用程序使用这些属性来指定其日程安排的应用程序文件的建议的位置。</span><span class="sxs-lookup"><span data-stu-id="1166c-117">For example, a scheduling application uses these properties to specify the suggested location for its scheduling application files.</span></span>
  
<span data-ttu-id="1166c-118">消息的用户配置文件提供这些属性为方便起见，以便客户端应用程序不必提示消息用户输入的网络路径或网络驱动器号。</span><span class="sxs-lookup"><span data-stu-id="1166c-118">The messaging user profile furnishes these properties as a convenience so that a client application does not have to prompt the messaging user for a network path or network drive letter.</span></span>
  
<span data-ttu-id="1166c-119">MAPI 仅适用于协会 (ANSI) 字符集中的文件名。</span><span class="sxs-lookup"><span data-stu-id="1166c-119">MAPI works only with filenames in the American National Standards Institute (ANSI) character set.</span></span> <span data-ttu-id="1166c-120">使用文件名的原始设备制造商 (OEM) 字符集中的应用程序必须将其转换为 ANSI 调用 MAPI 之前。</span><span class="sxs-lookup"><span data-stu-id="1166c-120">Applications that use filenames in an original equipment manufacturer (OEM) character set must convert them to ANSI before calling MAPI.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="1166c-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="1166c-121">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="1166c-122">头文件</span><span class="sxs-lookup"><span data-stu-id="1166c-122">Header files</span></span>

<span data-ttu-id="1166c-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="1166c-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="1166c-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="1166c-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="1166c-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="1166c-125">Mapitags.h</span></span>
  
> <span data-ttu-id="1166c-126">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="1166c-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1166c-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1166c-127">See also</span></span>



[<span data-ttu-id="1166c-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="1166c-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="1166c-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="1166c-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="1166c-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="1166c-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="1166c-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="1166c-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

