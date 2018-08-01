---
title: PidTagLanguages 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagLanguages
api_type:
- HeaderDef
ms.assetid: 16d4e92d-d48e-4e06-9886-2d21f3d10640
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3870ca7aaf8c1b178155d385f88e130a46d3b787
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19777797"
---
# <a name="pidtaglanguages-canonical-property"></a><span data-ttu-id="0200f-103">PidTagLanguages 规范属性</span><span class="sxs-lookup"><span data-stu-id="0200f-103">PidTagLanguages Canonical Property</span></span>

  
  
<span data-ttu-id="0200f-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="0200f-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="0200f-105">包含一条消息中采用的语言的 ASCII 列表。</span><span class="sxs-lookup"><span data-stu-id="0200f-105">Contains an ASCII list of the languages that are incorporated in a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="0200f-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="0200f-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="0200f-107">PR_LANGUAGES，PR_LANGUAGES_A，PR_LANGUAGES_W</span><span class="sxs-lookup"><span data-stu-id="0200f-107">PR_LANGUAGES, PR_LANGUAGES_A, PR_LANGUAGES_W</span></span>  <br/> |
|<span data-ttu-id="0200f-108">标识符：</span><span class="sxs-lookup"><span data-stu-id="0200f-108">Identifier:</span></span>  <br/> |<span data-ttu-id="0200f-109">0x002F</span><span class="sxs-lookup"><span data-stu-id="0200f-109">0x002F</span></span>  <br/> |
|<span data-ttu-id="0200f-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="0200f-110">Data type:</span></span>  <br/> |<span data-ttu-id="0200f-111">PT_STRING8 PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="0200f-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="0200f-112">区域：</span><span class="sxs-lookup"><span data-stu-id="0200f-112">Area:</span></span>  <br/> |<span data-ttu-id="0200f-113">常规消息</span><span class="sxs-lookup"><span data-stu-id="0200f-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="0200f-114">说明</span><span class="sxs-lookup"><span data-stu-id="0200f-114">Remarks</span></span>

<span data-ttu-id="0200f-115">这些属性包含序列的以逗号分隔的两个字符的国家/地区代码。</span><span class="sxs-lookup"><span data-stu-id="0200f-115">These properties contain a sequence of two-character country/region codes that are separated by commas.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="0200f-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="0200f-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="0200f-117">头文件</span><span class="sxs-lookup"><span data-stu-id="0200f-117">Header files</span></span>

<span data-ttu-id="0200f-118">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="0200f-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="0200f-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="0200f-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="0200f-120">Mapitags.h</span><span class="sxs-lookup"><span data-stu-id="0200f-120">Mapitags.h</span></span>
  
> <span data-ttu-id="0200f-121">包含作为替代名称列出的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="0200f-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="0200f-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0200f-122">See also</span></span>



[<span data-ttu-id="0200f-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="0200f-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="0200f-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="0200f-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="0200f-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="0200f-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="0200f-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="0200f-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

