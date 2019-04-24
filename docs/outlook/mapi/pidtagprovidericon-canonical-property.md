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
ms.openlocfilehash: 55e6c8fb013e544ae04740aeaeb23ac23949cffb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286458"
---
# <a name="pidtagprovidericon-canonical-property"></a><span data-ttu-id="ca7ce-103">PidTagProviderIcon 规范属性</span><span class="sxs-lookup"><span data-stu-id="ca7ce-103">PidTagProviderIcon Canonical Property</span></span>

  
  
<span data-ttu-id="ca7ce-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="ca7ce-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="ca7ce-105">包含一个 Unicode 字符串, 该字符串指定要在联机和脱机状态的 Microsoft Office Outlook 状态栏中为 MAPI 提供程序显示的自定义图标或图标。</span><span class="sxs-lookup"><span data-stu-id="ca7ce-105">Contains a Unicode string that specifies a custom icon or icons to be displayed for a MAPI provider in the Microsoft Office Outlook status bar in both online and offline states.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="ca7ce-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="ca7ce-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="ca7ce-107">PR_PROVIDER_ICON、PR_PROVIDER_ICON_W</span><span class="sxs-lookup"><span data-stu-id="ca7ce-107">PR_PROVIDER_ICON, PR_PROVIDER_ICON_W</span></span>  <br/> |
|<span data-ttu-id="ca7ce-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="ca7ce-108">Identifier:</span></span>  <br/> |<span data-ttu-id="ca7ce-109">0x3417</span><span class="sxs-lookup"><span data-stu-id="ca7ce-109">0x3417</span></span>  <br/> |
|<span data-ttu-id="ca7ce-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="ca7ce-110">Data type:</span></span>  <br/> |<span data-ttu-id="ca7ce-111">PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="ca7ce-111">PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="ca7ce-112">区域：</span><span class="sxs-lookup"><span data-stu-id="ca7ce-112">Area:</span></span>  <br/> |<span data-ttu-id="ca7ce-113">MAPI 邮件存储</span><span class="sxs-lookup"><span data-stu-id="ca7ce-113">MAPI message store</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="ca7ce-114">注解</span><span class="sxs-lookup"><span data-stu-id="ca7ce-114">Remarks</span></span>

<span data-ttu-id="ca7ce-115">这些属性指定的资源文件中包含一个自定义图标, 该图标表示处于联机状态的 MAPI 提供程序, 也可以选择另一个自定义图标处于脱机状态。</span><span class="sxs-lookup"><span data-stu-id="ca7ce-115">These properties specify the resource file that contains a custom icon that represents a MAPI provider in an online state, and optionally, another custom icon in the offline state.</span></span> <span data-ttu-id="ca7ce-116">Outlook 始终请求 Unicode 表示形式的这些属性。</span><span class="sxs-lookup"><span data-stu-id="ca7ce-116">Outlook always requests these properties in Unicode representation.</span></span> 
  
<span data-ttu-id="ca7ce-117">例如, 以下属性值指示 Outlook 从模块 mymod32 加载图标 ID 1001, 并将该图标用于联机状态: `mymod32.dll,#1001`。</span><span class="sxs-lookup"><span data-stu-id="ca7ce-117">For example, the following property value instructs Outlook to load icon ID 1001 from the module mymod32.dll and use that icon for the online state:  `mymod32.dll,#1001`.</span></span> <span data-ttu-id="ca7ce-118">由于脱机状态没有提供程序特定的图标, 在这种情况下, 将在状态栏中使用标准的 Outlook 脱机图标。</span><span class="sxs-lookup"><span data-stu-id="ca7ce-118">Since there is no provider-specific icon for the offline state, in this case, the standard Outlook offline icon is used in the status bar.</span></span> 
  
<span data-ttu-id="ca7ce-119">下面的属性值指示 Outlook 从模块 mymod32 加载图标 id 1001, 并将该图标用于联机状态, 并从该相同的模块加载图标 id 1002, 以用于脱机状态: `mymod32.dll,#1001,#1002`。</span><span class="sxs-lookup"><span data-stu-id="ca7ce-119">The following property value instructs Outlook to load icon ID 1001 from the module mymod32.dll and use that icon for the online state, and to also load icon ID 1002 from this same module to be used for the offline state:  `mymod32.dll,#1001,#1002`.</span></span> <span data-ttu-id="ca7ce-120">状态栏中不使用 Outlook 图标。</span><span class="sxs-lookup"><span data-stu-id="ca7ce-120">No Outlook icon is used in the status bar.</span></span> 
  
<span data-ttu-id="ca7ce-121">默认情况下, 如果未指定任何自定义图标, 提供程序将由 Outlook 默认图标用于联机状态和脱机状态。</span><span class="sxs-lookup"><span data-stu-id="ca7ce-121">By default, if no custom icons are specified, the provider is represented by the Outlook default icons for the online state and the offline state.</span></span> <span data-ttu-id="ca7ce-122">提供程序可以根据需要指定显示名称, 该显示名称将显示在状态栏中的图标旁边。</span><span class="sxs-lookup"><span data-stu-id="ca7ce-122">The provider can optionally specify a display name to be shown adjacent to the icon in the status bar.</span></span> <span data-ttu-id="ca7ce-123">有关详细信息, 请参阅**PR_PROVIDER_DISPLAY_NAME_W** ([PidTagProviderDisplayName](pidtagproviderdisplayname-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="ca7ce-123">For more information, see **PR_PROVIDER_DISPLAY_NAME_W** ([PidTagProviderDisplayName](pidtagproviderdisplayname-canonical-property.md)).</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="ca7ce-124">相关资源</span><span class="sxs-lookup"><span data-stu-id="ca7ce-124">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="ca7ce-125">头文件</span><span class="sxs-lookup"><span data-stu-id="ca7ce-125">Header files</span></span>

<span data-ttu-id="ca7ce-126">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="ca7ce-126">Mapidefs.h</span></span>
  
> <span data-ttu-id="ca7ce-127">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="ca7ce-127">Provides data type definitions.</span></span>
    
<span data-ttu-id="ca7ce-128">Mapitags</span><span class="sxs-lookup"><span data-stu-id="ca7ce-128">Mapitags.h</span></span>
  
> <span data-ttu-id="ca7ce-129">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="ca7ce-129">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ca7ce-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ca7ce-130">See also</span></span>



[<span data-ttu-id="ca7ce-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="ca7ce-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="ca7ce-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="ca7ce-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="ca7ce-133">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="ca7ce-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="ca7ce-134">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="ca7ce-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

