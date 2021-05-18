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
ms.openlocfilehash: 57fdc754ed4be29dbdd50a198707d8f39a14b3d4
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286486"
---
# <a name="pidtagproviderdllname-canonical-property"></a><span data-ttu-id="7fd5e-103">PidTagProviderDllName 规范属性</span><span class="sxs-lookup"><span data-stu-id="7fd5e-103">PidTagProviderDllName Canonical Property</span></span>

  
  
<span data-ttu-id="7fd5e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="7fd5e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="7fd5e-105">包含 MAPI 服务提供程序动态链接库的基本文件名 (DLL) 。</span><span class="sxs-lookup"><span data-stu-id="7fd5e-105">Contains the base file name of the MAPI service provider dynamic-link library (DLL).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="7fd5e-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="7fd5e-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="7fd5e-107">PR_PROVIDER_DLL_NAME、PR_PROVIDER_DLL_NAME_A、PR_PROVIDER_DLL_NAME_W</span><span class="sxs-lookup"><span data-stu-id="7fd5e-107">PR_PROVIDER_DLL_NAME, PR_PROVIDER_DLL_NAME_A, PR_PROVIDER_DLL_NAME_W</span></span>  <br/> |
|<span data-ttu-id="7fd5e-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="7fd5e-108">Identifier:</span></span>  <br/> |<span data-ttu-id="7fd5e-109">0x300A</span><span class="sxs-lookup"><span data-stu-id="7fd5e-109">0x300A</span></span>  <br/> |
|<span data-ttu-id="7fd5e-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="7fd5e-110">Data type:</span></span>  <br/> |<span data-ttu-id="7fd5e-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="7fd5e-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="7fd5e-112">区域：</span><span class="sxs-lookup"><span data-stu-id="7fd5e-112">Area:</span></span>  <br/> |<span data-ttu-id="7fd5e-113">MAPI common</span><span class="sxs-lookup"><span data-stu-id="7fd5e-113">MAPI common</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="7fd5e-114">备注</span><span class="sxs-lookup"><span data-stu-id="7fd5e-114">Remarks</span></span>

<span data-ttu-id="7fd5e-115">MAPI 使用 DLL 文件命名约定。</span><span class="sxs-lookup"><span data-stu-id="7fd5e-115">MAPI uses a DLL file naming convention.</span></span> <span data-ttu-id="7fd5e-116">它将字符串 32 附加到基 DLL 名称以标识在 32 位平台上运行的版本。</span><span class="sxs-lookup"><span data-stu-id="7fd5e-116">It appends the string 32 to the base DLL name to identify the version that runs on 32-bit platforms.</span></span> <span data-ttu-id="7fd5e-117">例如，当MAPI.DLL名称时，MAPI 将构造名称MAPI32.DLL表示相应的 32 位版本的 DLL。</span><span class="sxs-lookup"><span data-stu-id="7fd5e-117">For example, when the name MAPI.DLL is specified, MAPI constructs the name MAPI32.DLL to represent the corresponding 32-bit version of the DLL.</span></span>
  
<span data-ttu-id="7fd5e-118">这些属性应指定基本名称。</span><span class="sxs-lookup"><span data-stu-id="7fd5e-118">These properties should specify the base name.</span></span> <span data-ttu-id="7fd5e-119">MAPI 会在适当时追加字符串 32。</span><span class="sxs-lookup"><span data-stu-id="7fd5e-119">MAPI appends the string 32 as appropriate.</span></span> <span data-ttu-id="7fd5e-120">将字符串 32 作为此属性的一部分会导致错误。</span><span class="sxs-lookup"><span data-stu-id="7fd5e-120">Including the string 32 as part of this property results in an error.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="7fd5e-121">相关资源</span><span class="sxs-lookup"><span data-stu-id="7fd5e-121">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="7fd5e-122">头文件</span><span class="sxs-lookup"><span data-stu-id="7fd5e-122">Header files</span></span>

<span data-ttu-id="7fd5e-123">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="7fd5e-123">Mapidefs.h</span></span>
  
> <span data-ttu-id="7fd5e-124">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="7fd5e-124">Provides data type definitions.</span></span>
    
<span data-ttu-id="7fd5e-125">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="7fd5e-125">Mapitags.h</span></span>
  
> <span data-ttu-id="7fd5e-126">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="7fd5e-126">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7fd5e-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7fd5e-127">See also</span></span>



[<span data-ttu-id="7fd5e-128">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="7fd5e-128">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="7fd5e-129">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="7fd5e-129">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="7fd5e-130">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="7fd5e-130">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="7fd5e-131">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="7fd5e-131">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

