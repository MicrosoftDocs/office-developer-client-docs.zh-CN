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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 54fe624c98ddb631326853f387372468a61b2f70
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778404"
---
# <a name="pidtagservicedllname-canonical-property"></a><span data-ttu-id="44df3-103">PidTagServiceDllName 规范属性</span><span class="sxs-lookup"><span data-stu-id="44df3-103">PidTagServiceDllName Canonical Property</span></span>

  
  
<span data-ttu-id="44df3-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="44df3-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="44df3-105">包含要配置的呼叫的 dll 包含消息服务提供程序入口点函数的文件名。</span><span class="sxs-lookup"><span data-stu-id="44df3-105">Contains the filename of the DLL containing the message service provider entry point function to call for configuration.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="44df3-106">关联的属性：</span><span class="sxs-lookup"><span data-stu-id="44df3-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="44df3-107">PR_SERVICE_DLL_NAME，PR_SERVICE_DLL_NAME_A，PR_SERVICE_DLL_NAME_W</span><span class="sxs-lookup"><span data-stu-id="44df3-107">PR_SERVICE_DLL_NAME, PR_SERVICE_DLL_NAME_A, PR_SERVICE_DLL_NAME_W</span></span>  <br/> |
|<span data-ttu-id="44df3-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="44df3-108">Identifier:</span></span>  <br/> |<span data-ttu-id="44df3-109">0x3D0A</span><span class="sxs-lookup"><span data-stu-id="44df3-109">0x3D0A</span></span>  <br/> |
|<span data-ttu-id="44df3-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="44df3-110">Data type:</span></span>  <br/> |<span data-ttu-id="44df3-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="44df3-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="44df3-112">区域：</span><span class="sxs-lookup"><span data-stu-id="44df3-112">Area:</span></span>  <br/> |<span data-ttu-id="44df3-113">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="44df3-113">MAPI profile</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="44df3-114">备注</span><span class="sxs-lookup"><span data-stu-id="44df3-114">Remarks</span></span>

<span data-ttu-id="44df3-115">当入口点函数名称出现在**PR_SERVICE_ENTRY_NAME** ([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md)) 方法时，它指示存在的入口点。</span><span class="sxs-lookup"><span data-stu-id="44df3-115">When the entry point function name appears in the **PR_SERVICE_ENTRY_NAME** ([PidTagServiceEntryName](pidtagserviceentryname-canonical-property.md)) method, it indicates that the entry point exists.</span></span>
  
<span data-ttu-id="44df3-116">MAPI 使用 DLL 文件命名约定。</span><span class="sxs-lookup"><span data-stu-id="44df3-116">MAPI uses a DLL file naming convention.</span></span> <span data-ttu-id="44df3-117">基文件名包含唯一标识 DLL 的最多包含 6 个字符。</span><span class="sxs-lookup"><span data-stu-id="44df3-117">The base filename contains up to six characters that uniquely identify the DLL.</span></span> <span data-ttu-id="44df3-118">MAPI 将字符串 32 追加到基的 DLL 名称，来确定在 32 位平台运行的版本。</span><span class="sxs-lookup"><span data-stu-id="44df3-118">MAPI appends the string 32 to the base DLL name to identify the version that runs on 32-bit platforms.</span></span> <span data-ttu-id="44df3-119">例如，当 MAPI 的名称。指定 DLL，MAPI 构造 MAPI32 的名称。表示的 dll 的相应 32 位版本的 DLL。</span><span class="sxs-lookup"><span data-stu-id="44df3-119">For example, when the name MAPI.DLL is specified, MAPI constructs the name MAPI32.DLL to represent the corresponding 32-bit version of the DLL.</span></span>
  
<span data-ttu-id="44df3-120">这些属性应指定的基名称。</span><span class="sxs-lookup"><span data-stu-id="44df3-120">These properties should specify the base name.</span></span> <span data-ttu-id="44df3-121">MAPI 将根据 32 字符串。</span><span class="sxs-lookup"><span data-stu-id="44df3-121">MAPI appends the string 32 as appropriate.</span></span> <span data-ttu-id="44df3-122">这些属性会导致出错的一部分包括 32 的字符串。</span><span class="sxs-lookup"><span data-stu-id="44df3-122">Including the string 32 as part of these properties result in an error.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="44df3-123">相关资源</span><span class="sxs-lookup"><span data-stu-id="44df3-123">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="44df3-124">头文件</span><span class="sxs-lookup"><span data-stu-id="44df3-124">Header files</span></span>

<span data-ttu-id="44df3-125">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="44df3-125">Mapidefs.h</span></span>
  
> <span data-ttu-id="44df3-126">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="44df3-126">Provides data type definitions.</span></span>
    
<span data-ttu-id="44df3-127">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="44df3-127">Mapitags.h</span></span>
  
> <span data-ttu-id="44df3-128">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="44df3-128">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="44df3-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="44df3-129">See also</span></span>



[<span data-ttu-id="44df3-130">PidTagProviderDllName 规范属性</span><span class="sxs-lookup"><span data-stu-id="44df3-130">PidTagProviderDllName Canonical Property</span></span>](pidtagproviderdllname-canonical-property.md)


[<span data-ttu-id="44df3-131">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="44df3-131">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="44df3-132">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="44df3-132">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="44df3-133">映射到 MAPI 名称的规范属性名称</span><span class="sxs-lookup"><span data-stu-id="44df3-133">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="44df3-134">MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="44df3-134">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

