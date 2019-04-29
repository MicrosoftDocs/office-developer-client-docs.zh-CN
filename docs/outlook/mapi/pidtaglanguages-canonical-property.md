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
ms.openlocfilehash: f3d8693644020dd77877db219b000f8f8c804376
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417838"
---
# <a name="pidtaglanguages-canonical-property"></a><span data-ttu-id="3d4e6-103">PidTagLanguages 规范属性</span><span class="sxs-lookup"><span data-stu-id="3d4e6-103">PidTagLanguages Canonical Property</span></span>

  
  
<span data-ttu-id="3d4e6-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3d4e6-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3d4e6-105">包含在邮件中并入的语言的 ASCII 列表。</span><span class="sxs-lookup"><span data-stu-id="3d4e6-105">Contains an ASCII list of the languages that are incorporated in a message.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3d4e6-106">相关属性：</span><span class="sxs-lookup"><span data-stu-id="3d4e6-106">Associated properties:</span></span>  <br/> |<span data-ttu-id="3d4e6-107">PR_LANGUAGES、PR_LANGUAGES_A、PR_LANGUAGES_W</span><span class="sxs-lookup"><span data-stu-id="3d4e6-107">PR_LANGUAGES, PR_LANGUAGES_A, PR_LANGUAGES_W</span></span>  <br/> |
|<span data-ttu-id="3d4e6-108">标识符:</span><span class="sxs-lookup"><span data-stu-id="3d4e6-108">Identifier:</span></span>  <br/> |<span data-ttu-id="3d4e6-109">0x002F</span><span class="sxs-lookup"><span data-stu-id="3d4e6-109">0x002F</span></span>  <br/> |
|<span data-ttu-id="3d4e6-110">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3d4e6-110">Data type:</span></span>  <br/> |<span data-ttu-id="3d4e6-111">PT_STRING8、PT_UNICODE</span><span class="sxs-lookup"><span data-stu-id="3d4e6-111">PT_STRING8, PT_UNICODE</span></span>  <br/> |
|<span data-ttu-id="3d4e6-112">区域：</span><span class="sxs-lookup"><span data-stu-id="3d4e6-112">Area:</span></span>  <br/> |<span data-ttu-id="3d4e6-113">常规邮件</span><span class="sxs-lookup"><span data-stu-id="3d4e6-113">General messaging</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3d4e6-114">说明</span><span class="sxs-lookup"><span data-stu-id="3d4e6-114">Remarks</span></span>

<span data-ttu-id="3d4e6-115">这些属性包含由逗号分隔的双字符国家/地区代码的序列。</span><span class="sxs-lookup"><span data-stu-id="3d4e6-115">These properties contain a sequence of two-character country/region codes that are separated by commas.</span></span> 
  
## <a name="related-resources"></a><span data-ttu-id="3d4e6-116">相关资源</span><span class="sxs-lookup"><span data-stu-id="3d4e6-116">Related resources</span></span>

### <a name="header-files"></a><span data-ttu-id="3d4e6-117">头文件</span><span class="sxs-lookup"><span data-stu-id="3d4e6-117">Header files</span></span>

<span data-ttu-id="3d4e6-118">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="3d4e6-118">Mapidefs.h</span></span>
  
> <span data-ttu-id="3d4e6-119">提供数据类型定义。</span><span class="sxs-lookup"><span data-stu-id="3d4e6-119">Provides data type definitions.</span></span>
    
<span data-ttu-id="3d4e6-120">Mapitags</span><span class="sxs-lookup"><span data-stu-id="3d4e6-120">Mapitags.h</span></span>
  
> <span data-ttu-id="3d4e6-121">包含列为替换名称的属性的定义。</span><span class="sxs-lookup"><span data-stu-id="3d4e6-121">Contains definitions of properties listed as alternate names.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="3d4e6-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d4e6-122">See also</span></span>



[<span data-ttu-id="3d4e6-123">MAPI 属性</span><span class="sxs-lookup"><span data-stu-id="3d4e6-123">MAPI Properties</span></span>](mapi-properties.md)
  
[<span data-ttu-id="3d4e6-124">MAPI 规范属性</span><span class="sxs-lookup"><span data-stu-id="3d4e6-124">MAPI Canonical Properties</span></span>](mapi-canonical-properties.md)
  
[<span data-ttu-id="3d4e6-125">将规范属性名称映射到 MAPI 名称</span><span class="sxs-lookup"><span data-stu-id="3d4e6-125">Mapping Canonical Property Names to MAPI Names</span></span>](mapping-canonical-property-names-to-mapi-names.md)
  
[<span data-ttu-id="3d4e6-126">将 MAPI 名称映射到规范属性名称</span><span class="sxs-lookup"><span data-stu-id="3d4e6-126">Mapping MAPI Names to Canonical Property Names</span></span>](mapping-mapi-names-to-canonical-property-names.md)

