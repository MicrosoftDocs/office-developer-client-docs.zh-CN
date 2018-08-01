---
title: PidTagProviderIcon 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagProviderIcon
api_type:
- COM
ms.assetid: 59c84b1f-13b5-484b-b703-2fb9fcc6c7eb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 92407d56bd095135ac1c6c292aa4b1da4755e93c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778084"
---
# <a name="pidtagprovidericon-canonical-property"></a><span data-ttu-id="6a3ce-103">PidTagProviderIcon 规范属性</span><span class="sxs-lookup"><span data-stu-id="6a3ce-103">PidTagProviderIcon Canonical Property</span></span>

  
  
<span data-ttu-id="6a3ce-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="6a3ce-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="6a3ce-105">包含指定自定义图标或图标以显示在 Microsoft Office Outlook 的状态栏中联机和脱机状态 MAPI 提供程序的 Unicode 字符串。</span><span class="sxs-lookup"><span data-stu-id="6a3ce-105">Contains a Unicode string that specifies a custom icon or icons to be displayed for a MAPI provider in the Microsoft Office Outlook status bar in both online and offline states.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="6a3ce-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="6a3ce-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="6a3ce-107">PR_PROVIDER_ICON PR_PROVIDER_ICON_W</span><span class="sxs-lookup"><span data-stu-id="6a3ce-107">PR_PROVIDER_ICON, PR_PROVIDER_ICON_W</span></span>  <br/> |
|<span data-ttu-id="6a3ce-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="6a3ce-108">Identifier:</span></span>  <br/> |<span data-ttu-id="6a3ce-109">0x3417</span><span class="sxs-lookup"><span data-stu-id="6a3ce-109">0x3417</span></span>  <br/> |
|<span data-ttu-id="6a3ce-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="6a3ce-110">Data type:</span></span>  <br/> |<span data-ttu-id="6a3ce-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="6a3ce-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="6a3ce-112">区域：</span><span class="sxs-lookup"><span data-stu-id="6a3ce-112">Area:</span></span>  <br/> |<span data-ttu-id="6a3ce-113">MAPI 邮件存储</span><span class="sxs-lookup"><span data-stu-id="6a3ce-113">MAPI message store</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="6a3ce-114">说明</span><span class="sxs-lookup"><span data-stu-id="6a3ce-114">Remarks</span></span>

<span data-ttu-id="6a3ce-115">这些属性指定资源文件包含自定义图标表示处于联机状态，MAPI 提供程序和 （可选），另一个自定义图标处于脱机状态。</span><span class="sxs-lookup"><span data-stu-id="6a3ce-115">These properties specify the resource file that contains a custom icon that represents a MAPI provider in an online state, and optionally, another custom icon in the offline state.</span></span> <span data-ttu-id="6a3ce-116">Outlook 始终请求 Unicode 表示这些属性。</span><span class="sxs-lookup"><span data-stu-id="6a3ce-116">Outlook always requests these properties in Unicode representation.</span></span> 
  
<span data-ttu-id="6a3ce-117">例如，以下属性值指示 Outlook 从模块 mymod32.dll 加载图标 ID 1001 并该图标用于联机状态： `mymod32.dll,#1001`。</span><span class="sxs-lookup"><span data-stu-id="6a3ce-117">For example, the following property value instructs Outlook to load icon ID 1001 from the module mymod32.dll and use that icon for the online state:  `mymod32.dll,#1001`.</span></span> <span data-ttu-id="6a3ce-118">没有为脱机状态提供程序特定的图标，因为在这种情况下，标准的 Outlook 脱机图标使用在状态栏中。</span><span class="sxs-lookup"><span data-stu-id="6a3ce-118">Since there is no provider-specific icon for the offline state, in this case, the standard Outlook offline icon is used in the status bar.</span></span> 
  
<span data-ttu-id="6a3ce-119">以下属性值指示 Outlook 从模块 mymod32.dll 加载图标 ID 1001 和该图标用于联机状态，并为还从这一相同模块用于脱机状态加载图标 ID 1002: `mymod32.dll,#1001,#1002`。</span><span class="sxs-lookup"><span data-stu-id="6a3ce-119">The following property value instructs Outlook to load icon ID 1001 from the module mymod32.dll and use that icon for the online state, and to also load icon ID 1002 from this same module to be used for the offline state:  `mymod32.dll,#1001,#1002`.</span></span> <span data-ttu-id="6a3ce-120">在状态栏中不使用任何 Outlook 图标。</span><span class="sxs-lookup"><span data-stu-id="6a3ce-120">No Outlook icon is used in the status bar.</span></span> 
  
<span data-ttu-id="6a3ce-121">默认情况下，如果未不指定任何自定义图标，则提供程序是由联机状态和脱机状态的 Outlook 默认图标表示。</span><span class="sxs-lookup"><span data-stu-id="6a3ce-121">By default, if no custom icons are specified, the provider is represented by the Outlook default icons for the online state and the offline state.</span></span> <span data-ttu-id="6a3ce-122">提供程序 （可选） 可以指定要在状态栏中显示图标旁边显示名称。</span><span class="sxs-lookup"><span data-stu-id="6a3ce-122">The provider can optionally specify a display name to be shown adjacent to the icon in the status bar.</span></span> <span data-ttu-id="6a3ce-123">有关详细信息，请参阅**PR_PROVIDER_DISPLAY_NAME_W** ([PidTagProviderDisplayName](pidtagproviderdisplayname-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="6a3ce-123">For more information, see **PR_PROVIDER_DISPLAY_NAME_W** ([PidTagProviderDisplayName](pidtagproviderdisplayname-canonical-property.md)).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="6a3ce-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="6a3ce-124">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="6a3ce-125">头文件</span><span class="sxs-lookup"><span data-stu-id="6a3ce-125">Header files</span></span>

<span data-ttu-id="6a3ce-126">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="6a3ce-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="6a3ce-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="6a3ce-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="6a3ce-128">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="6a3ce-128">Mapitags.h</span></span>
  
> <span data-ttu-id="6a3ce-129">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="6a3ce-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6a3ce-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6a3ce-130">See also</span></span>



[<span data-ttu-id="6a3ce-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="6a3ce-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="6a3ce-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="6a3ce-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="6a3ce-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="6a3ce-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="6a3ce-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="6a3ce-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

