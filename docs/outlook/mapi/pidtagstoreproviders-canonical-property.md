---
title: PidTagStoreProviders 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagStoreProviders
api_type:
- COM
ms.assetid: a2c4a933-b371-43ec-af0f-6140d8b5c7ea
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 45d19b35f05b3347e78973bb72e526a2198d9bad
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415836"
---
# <a name="pidtagstoreproviders-canonical-property"></a><span data-ttu-id="2b8d2-103">PidTagStoreProviders 规范属性</span><span class="sxs-lookup"><span data-stu-id="2b8d2-103">PidTagStoreProviders Canonical Property</span></span>

  
  
<span data-ttu-id="2b8d2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2b8d2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2b8d2-105">包含当前配置文件中邮件存储提供程序的标识符列表。</span><span class="sxs-lookup"><span data-stu-id="2b8d2-105">Contains a list of identifiers of message store providers in the current profile.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="2b8d2-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="2b8d2-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="2b8d2-107">PR_STORE_PROVIDERS</span><span class="sxs-lookup"><span data-stu-id="2b8d2-107">PR_STORE_PROVIDERS</span></span>  <br/> |
|<span data-ttu-id="2b8d2-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="2b8d2-108">Identifier:</span></span>  <br/> |<span data-ttu-id="2b8d2-109">0x3D00</span><span class="sxs-lookup"><span data-stu-id="2b8d2-109">0x3D00</span></span>  <br/> |
|<span data-ttu-id="2b8d2-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="2b8d2-110">Data type:</span></span>  <br/> |<span data-ttu-id="2b8d2-111">PT_BINARY</span><span class="sxs-lookup"><span data-stu-id="2b8d2-111">PT_BINARY</span></span>  <br/> |
|<span data-ttu-id="2b8d2-112">区域：</span><span class="sxs-lookup"><span data-stu-id="2b8d2-112">Area:</span></span>  <br/> |<span data-ttu-id="2b8d2-113">MAPI 配置文件</span><span class="sxs-lookup"><span data-stu-id="2b8d2-113">MAPI profile</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2b8d2-114">备注</span><span class="sxs-lookup"><span data-stu-id="2b8d2-114">Remarks</span></span>

<span data-ttu-id="2b8d2-115">不要使用此属性。</span><span class="sxs-lookup"><span data-stu-id="2b8d2-115">Do not use this property.</span></span> <span data-ttu-id="2b8d2-116">它保留供 MAPI 使用。</span><span class="sxs-lookup"><span data-stu-id="2b8d2-116">It is reserved for use by MAPI.</span></span>
  
## <a name="related-resources"></a><span data-ttu-id="2b8d2-117">相关资源</span><span class="sxs-lookup"><span data-stu-id="2b8d2-117">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="2b8d2-118">头文件</span><span class="sxs-lookup"><span data-stu-id="2b8d2-118">Header files</span></span>

<span data-ttu-id="2b8d2-119">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2b8d2-119">Mapidefs.h</span></span>
  
> <span data-ttu-id="2b8d2-120">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="2b8d2-120">Provides data type definitions.</span></span>
    
<span data-ttu-id="2b8d2-121">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="2b8d2-121">Mapitags.h</span></span>
  
> <span data-ttu-id="2b8d2-122">包含作为备用名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="2b8d2-122">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="2b8d2-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2b8d2-123">See also</span></span>



[<span data-ttu-id="2b8d2-124">MAPIUID</span><span class="sxs-lookup"><span data-stu-id="2b8d2-124">MAPIUID</span></span>](mapiuid.md)


[<span data-ttu-id="2b8d2-125">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="2b8d2-125">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="2b8d2-126">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="2b8d2-126">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="2b8d2-127">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="2b8d2-127">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="2b8d2-128">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="2b8d2-128">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

