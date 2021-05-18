---
title: PROP_ID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PROP_ID
api_type:
- COM
ms.assetid: 6ddaced5-49bb-41fe-95da-4e3300883bf7
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 228ea91969b35a1608dd6b3378b751312aa9c665
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409130"
---
# <a name="prop_id"></a><span data-ttu-id="82138-103">PROP_ID</span><span class="sxs-lookup"><span data-stu-id="82138-103">PROP_ID</span></span>

  
  
<span data-ttu-id="82138-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="82138-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="82138-105">返回指定属性标记的属性标识符。</span><span class="sxs-lookup"><span data-stu-id="82138-105">Returns the property identifier of a specified property tag.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="82138-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="82138-106">Header file:</span></span>  <br/> |<span data-ttu-id="82138-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="82138-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="82138-108">相关结构：</span><span class="sxs-lookup"><span data-stu-id="82138-108">Related structure:</span></span>  <br/> |[<span data-ttu-id="82138-109">SPropValue</span><span class="sxs-lookup"><span data-stu-id="82138-109">SPropValue</span></span>](spropvalue.md) <br/> |
   
```cpp
PROP_ID (ulPropTag)
```

## <a name="parameters"></a><span data-ttu-id="82138-110">参数</span><span class="sxs-lookup"><span data-stu-id="82138-110">Parameters</span></span>

 <span data-ttu-id="82138-111">_ulPropTag_</span><span class="sxs-lookup"><span data-stu-id="82138-111">_ulPropTag_</span></span>
  
> <span data-ttu-id="82138-112">包含要返回的标识符的属性标记。</span><span class="sxs-lookup"><span data-stu-id="82138-112">Property tag that contains the identifier to be returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="82138-113">备注</span><span class="sxs-lookup"><span data-stu-id="82138-113">Remarks</span></span>

<span data-ttu-id="82138-114">每个属性标记都包含低顺序单词 (位 0 到 15) 中的属性类型，高顺序单词的属性标识符 (位 16 到 31) 。</span><span class="sxs-lookup"><span data-stu-id="82138-114">Every property tag contains the property type in the low-order word (bits 0 through 15) and the property identifier in the high-order word (bits 16 through 31).</span></span> <span data-ttu-id="82138-115">该 **PROP_ID** 宏提取属性标识符，并将它放在要返回的整数的位 0 到 15 中。</span><span class="sxs-lookup"><span data-stu-id="82138-115">The **PROP_ID** macro extracts the property identifier and puts it in bits 0 through 15 of the integer to be returned.</span></span> <span data-ttu-id="82138-116">返回值的剩余位设置为零。</span><span class="sxs-lookup"><span data-stu-id="82138-116">The remaining bits of the return value are set to zeros.</span></span> 
  
<span data-ttu-id="82138-117">例如 **PROP_ID，** 该宏可用于检索要传递给 [IMAPIProp：：GetNamesFromIDs](imapiprop-getnamesfromids.md)的标识符。</span><span class="sxs-lookup"><span data-stu-id="82138-117">The **PROP_ID** macro can be used, for example, to retrieve an identifier to pass to [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md).</span></span> <span data-ttu-id="82138-118">**GetNamesFromIDs** 检索与命名属性的标识符关联的属性名称。</span><span class="sxs-lookup"><span data-stu-id="82138-118">**GetNamesFromIDs** retrieves the property name associated with an identifier for a named property.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="82138-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82138-119">See also</span></span>



[<span data-ttu-id="82138-120">SPropValue</span><span class="sxs-lookup"><span data-stu-id="82138-120">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="82138-121">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="82138-121">Macros Related to Structures</span></span>](macros-related-to-structures.md)

