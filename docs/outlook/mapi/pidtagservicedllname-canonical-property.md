---
title: PidTagServiceDllName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagServiceDllName
api_type:
- COM
ms.assetid: a651af84-1711-449e-ba7e-5ce09cafa02b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: adf24bcd02d7efc303f911ee01a64325150339ce
ms.sourcegitcommit: 18f3d9462048859fe040e12136ff66f19066764b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2019
ms.locfileid: "31980451"
---
# <a name="pidtagservicedllname-canonical-property"></a><span data-ttu-id="fb108-103">PidTagServiceDllName 规范属性</span><span class="sxs-lookup"><span data-stu-id="fb108-103">PidTagServiceDllName Canonical Property</span></span>

  
  
<span data-ttu-id="fb108-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fb108-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fb108-105">包含包含要调用配置的邮件服务提供程序入口点函数的 DLL 的文件名。</span><span class="sxs-lookup"><span data-stu-id="fb108-105">Contains the filename of the DLL containing the message service provider entry point function to call for configuration.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="fb108-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="fb108-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="fb108-107">PR_SERVICE_DLL_NAME、PR_SERVICE_DLL_NAME_A、PR_SERVICE_DLL_NAME_W</span><span class="sxs-lookup"><span data-stu-id="fb108-107">PR_SERVICE_DLL_NAME, PR_SERVICE_DLL_NAME_A, PR_SERVICE_DLL_NAME_W</span></span>  <br/> |
|<span data-ttu-id="fb108-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="fb108-108">Identifier:</span></span>  <br/> |<span data-ttu-id="fb108-109">0x3D0A</span><span class="sxs-lookup"><span data-stu-id="fb108-109">0x3D0A</span></span>  <br/> |
|<span data-ttu-id="fb108-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="fb108-110">Data type:</span></span>  <br/> |<span data-ttu-id="fb108-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="fb108-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="fb108-112">区域：</span><span class="sxs-lookup"><span data-stu-id="fb108-112">Area:</span></span>  <br/> |<span data-ttu-id="fb108-113">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="fb108-113">MAPI profile</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fb108-114">注解</span><span class="sxs-lookup"><span data-stu-id="fb108-114">Remarks</span></span>

<span data-ttu-id="fb108-115">当入口点函数名称显示在**PR_SERVICE_ENTRY_NAME** ([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md)) 方法中时, 它表示该入口点存在。</span><span class="sxs-lookup"><span data-stu-id="fb108-115">When the entry point function name appears in the **PR_SERVICE_ENTRY_NAME** ([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md)) method, it indicates that the entry point exists.</span></span>
  
<span data-ttu-id="fb108-116">MAPI 使用 DLL 文件命名约定。</span><span class="sxs-lookup"><span data-stu-id="fb108-116">MAPI uses a DLL file naming convention.</span></span> <span data-ttu-id="fb108-117">它将字符串32追加到基 DLL 名称, 以标识在32位平台上运行的版本。</span><span class="sxs-lookup"><span data-stu-id="fb108-117">It appends the string 32 to the base DLL name to identify the version that runs on 32-bit platforms.</span></span> <span data-ttu-id="fb108-118">例如, 当名称为 MAPI 时。DLL 的指定, MAPI 将构造名称 MAPI32。dll 的 dll, 用于表示相应的32位版本的 dll。</span><span class="sxs-lookup"><span data-stu-id="fb108-118">For example, when the name MAPI.DLL is specified, MAPI constructs the name MAPI32.DLL to represent the corresponding 32-bit version of the DLL.</span></span>
  
<span data-ttu-id="fb108-119">这些属性应指定基名称。</span><span class="sxs-lookup"><span data-stu-id="fb108-119">These properties should specify the base name.</span></span> <span data-ttu-id="fb108-120">MAPI 将根据需要追加字符串32。</span><span class="sxs-lookup"><span data-stu-id="fb108-120">MAPI appends the string 32 as appropriate.</span></span> <span data-ttu-id="fb108-121">作为这些属性的一部分包含字符串32将导致错误。</span><span class="sxs-lookup"><span data-stu-id="fb108-121">Including the string 32 as part of these properties result in an error.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="fb108-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="fb108-122">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="fb108-123">头文件</span><span class="sxs-lookup"><span data-stu-id="fb108-123">Header files</span></span>

<span data-ttu-id="fb108-124">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="fb108-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="fb108-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="fb108-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="fb108-126">Mapitags</span><span class="sxs-lookup"><span data-stu-id="fb108-126">Mapitags.h</span></span>
  
> <span data-ttu-id="fb108-127">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="fb108-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="fb108-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb108-128">See also</span></span>



[<span data-ttu-id="fb108-129">PidTagProviderDllName 规范属性</span><span class="sxs-lookup"><span data-stu-id="fb108-129">PidTagProviderDllName Canonical Property</span></span>](pidtagproviderdllname-canonical-property.md)


[<span data-ttu-id="fb108-130">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="fb108-130">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="fb108-131">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="fb108-131">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="fb108-132">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="fb108-132">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="fb108-133">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="fb108-133">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

