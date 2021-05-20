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
ms.openlocfilehash: 32d150e508f5c208e15d5ee5f0b8c800a1e597f9
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429857"
---
# <a name="pidtagresourcepath-canonical-property"></a><span data-ttu-id="4332d-103">PidTagResourcePath 规范属性</span><span class="sxs-lookup"><span data-stu-id="4332d-103">PidTagResourcePath Canonical Property</span></span>

  
  
<span data-ttu-id="4332d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4332d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4332d-105">包含指向服务提供商服务器的路径。</span><span class="sxs-lookup"><span data-stu-id="4332d-105">Contains a path to the service provider's server.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4332d-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="4332d-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="4332d-107">PR_RESOURCE_PATH、PR_RESOURCE_PATH_A、PR_RESOURCE_PATH_W</span><span class="sxs-lookup"><span data-stu-id="4332d-107">PR_RESOURCE_PATH, PR_RESOURCE_PATH_A, PR_RESOURCE_PATH_W</span></span>  <br/> |
|<span data-ttu-id="4332d-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="4332d-108">Identifier:</span></span>  <br/> |<span data-ttu-id="4332d-109">0x3E07</span><span class="sxs-lookup"><span data-stu-id="4332d-109">0x3E07</span></span>  <br/> |
|<span data-ttu-id="4332d-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="4332d-110">Data type:</span></span>  <br/> |<span data-ttu-id="4332d-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="4332d-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="4332d-112">区域：</span><span class="sxs-lookup"><span data-stu-id="4332d-112">Area:</span></span>  <br/> |<span data-ttu-id="4332d-113">MAPI 状态</span><span class="sxs-lookup"><span data-stu-id="4332d-113">MAPI status</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4332d-114">备注</span><span class="sxs-lookup"><span data-stu-id="4332d-114">Remarks</span></span>

<span data-ttu-id="4332d-115">这些属性中包含的路径表示建议的路径，用户可以在路径中查找资源。</span><span class="sxs-lookup"><span data-stu-id="4332d-115">The path contained in these properties represents the suggested path where the user can find resources.</span></span> <span data-ttu-id="4332d-116">这些属性的定义特定于提供程序。</span><span class="sxs-lookup"><span data-stu-id="4332d-116">The definition of these properties is provider specific.</span></span> <span data-ttu-id="4332d-117">例如，计划应用程序使用这些属性来指定其计划应用程序文件的建议位置。</span><span class="sxs-lookup"><span data-stu-id="4332d-117">For example, a scheduling application uses these properties to specify the suggested location for its scheduling application files.</span></span>
  
<span data-ttu-id="4332d-118">邮件传递用户配置文件提供这些属性是一种便利，以便客户端应用程序无需提示消息用户输入网络路径或网络驱动器号。</span><span class="sxs-lookup"><span data-stu-id="4332d-118">The messaging user profile furnishes these properties as a convenience so that a client application does not have to prompt the messaging user for a network path or network drive letter.</span></span>
  
<span data-ttu-id="4332d-119">MAPI 仅适用于美国国家标准协会的文件名 (ANSI) 字符集。</span><span class="sxs-lookup"><span data-stu-id="4332d-119">MAPI works only with filenames in the American National Standards Institute (ANSI) character set.</span></span> <span data-ttu-id="4332d-120">使用原始设备制造商中的文件名的应用程序 (OEM) 集必须先将其转换为 ANSI，然后才能调用 MAPI。</span><span class="sxs-lookup"><span data-stu-id="4332d-120">Applications that use filenames in an original equipment manufacturer (OEM) character set must convert them to ANSI before calling MAPI.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="4332d-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="4332d-121">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="4332d-122">头文件</span><span class="sxs-lookup"><span data-stu-id="4332d-122">Header files</span></span>

<span data-ttu-id="4332d-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4332d-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="4332d-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="4332d-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="4332d-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="4332d-125">Mapitags.h</span></span>
  
> <span data-ttu-id="4332d-126">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="4332d-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4332d-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4332d-127">See also</span></span>



[<span data-ttu-id="4332d-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="4332d-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="4332d-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="4332d-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="4332d-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="4332d-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="4332d-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="4332d-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

