---
title: PidTagProviderDllName 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagProviderDllName
api_type:
- COM
ms.assetid: 9ddb38eb-9a32-4dbe-b42c-6ea9db98acd2
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: d75f22af3f8c9184da55ec57e08cf4db832ed174
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778080"
---
# <a name="pidtagproviderdllname-canonical-property"></a><span data-ttu-id="9f176-103">PidTagProviderDllName 规范属性</span><span class="sxs-lookup"><span data-stu-id="9f176-103">PidTagProviderDllName Canonical Property</span></span>

  
  
<span data-ttu-id="9f176-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="9f176-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="9f176-105">包含基文件名的 MAPI 服务提供程序动态链接库 (DLL)。</span><span class="sxs-lookup"><span data-stu-id="9f176-105">Contains the base file name of the MAPI service provider dynamic-link library (DLL).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9f176-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="9f176-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="9f176-107">PR_PROVIDER_DLL_NAME，PR_PROVIDER_DLL_NAME_A，PR_PROVIDER_DLL_NAME_W</span><span class="sxs-lookup"><span data-stu-id="9f176-107">PR_PROVIDER_DLL_NAME, PR_PROVIDER_DLL_NAME_A, PR_PROVIDER_DLL_NAME_W</span></span>  <br/> |
|<span data-ttu-id="9f176-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="9f176-108">Identifier:</span></span>  <br/> |<span data-ttu-id="9f176-109">0x300A</span><span class="sxs-lookup"><span data-stu-id="9f176-109">0x300A</span></span>  <br/> |
|<span data-ttu-id="9f176-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="9f176-110">Data type:</span></span>  <br/> |<span data-ttu-id="9f176-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="9f176-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="9f176-112">区域：</span><span class="sxs-lookup"><span data-stu-id="9f176-112">Area:</span></span>  <br/> |<span data-ttu-id="9f176-113">常见的 MAPI</span><span class="sxs-lookup"><span data-stu-id="9f176-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="9f176-114">说明</span><span class="sxs-lookup"><span data-stu-id="9f176-114">Remarks</span></span>

<span data-ttu-id="9f176-115">MAPI 使用 DLL 文件命名约定。</span><span class="sxs-lookup"><span data-stu-id="9f176-115">MAPI uses a DLL file naming convention.</span></span> <span data-ttu-id="9f176-116">基文件名包含唯一标识 DLL 的最多包含 6 个字符。</span><span class="sxs-lookup"><span data-stu-id="9f176-116">The base filename contains up to six characters that uniquely identify the DLL.</span></span> <span data-ttu-id="9f176-117">MAPI 将字符串 32 追加到基的 DLL 名称，来确定在 32 位平台运行的版本。</span><span class="sxs-lookup"><span data-stu-id="9f176-117">MAPI appends the string 32 to the base DLL name to identify the version that runs on 32-bit platforms.</span></span> <span data-ttu-id="9f176-118">例如，当 MAPI 的名称。指定 DLL，MAPI 构造 MAPI32 的名称。表示的 dll 的相应 32 位版本的 DLL。</span><span class="sxs-lookup"><span data-stu-id="9f176-118">For example, when the name MAPI.DLL is specified, MAPI constructs the name MAPI32.DLL to represent the corresponding 32-bit version of the DLL.</span></span>
  
<span data-ttu-id="9f176-119">这些属性应指定的基名称。</span><span class="sxs-lookup"><span data-stu-id="9f176-119">These properties should specify the base name.</span></span> <span data-ttu-id="9f176-120">MAPI 将根据 32 字符串。</span><span class="sxs-lookup"><span data-stu-id="9f176-120">MAPI appends the string 32 as appropriate.</span></span> <span data-ttu-id="9f176-121">此属性将导致出错的一部分包括 32 的字符串。</span><span class="sxs-lookup"><span data-stu-id="9f176-121">Including the string 32 as part of this property results in an error.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="9f176-122">相关资源</span><span class="sxs-lookup"><span data-stu-id="9f176-122">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="9f176-123">头文件</span><span class="sxs-lookup"><span data-stu-id="9f176-123">Header files</span></span>

<span data-ttu-id="9f176-124">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="9f176-124">Mapidefs.h</span></span>
  
> <span data-ttu-id="9f176-125">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="9f176-125">Provides data type definitions.</span></span>
    
<span data-ttu-id="9f176-126">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="9f176-126">Mapitags.h</span></span>
  
> <span data-ttu-id="9f176-127">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="9f176-127">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="9f176-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9f176-128">See also</span></span>



[<span data-ttu-id="9f176-129">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="9f176-129">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="9f176-130">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="9f176-130">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="9f176-131">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="9f176-131">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="9f176-132">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="9f176-132">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

