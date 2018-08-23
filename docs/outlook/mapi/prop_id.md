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
ms.openlocfilehash: e1846b4be93bf6300ea89a9ae3133fbba82b344e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22573122"
---
# <a name="propid"></a><span data-ttu-id="f628a-103">PROP_ID</span><span class="sxs-lookup"><span data-stu-id="f628a-103">PROP_ID</span></span>

  
  
<span data-ttu-id="f628a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="f628a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="f628a-105">返回指定的属性标记属性标识符。</span><span class="sxs-lookup"><span data-stu-id="f628a-105">Returns the property identifier of a specified property tag.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="f628a-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="f628a-106">Header file:</span></span>  <br/> |<span data-ttu-id="f628a-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f628a-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="f628a-108">相关的结构：</span><span class="sxs-lookup"><span data-stu-id="f628a-108">Related structure:</span></span>  <br/> |[<span data-ttu-id="f628a-109">SPropValue</span><span class="sxs-lookup"><span data-stu-id="f628a-109">SPropValue</span></span>](spropvalue.md) <br/> |
   
```cpp
PROP_ID (ulPropTag)
```

## <a name="parameters"></a><span data-ttu-id="f628a-110">参数</span><span class="sxs-lookup"><span data-stu-id="f628a-110">Parameters</span></span>

 <span data-ttu-id="f628a-111">_ulPropTag_</span><span class="sxs-lookup"><span data-stu-id="f628a-111">_ulPropTag_</span></span>
  
> <span data-ttu-id="f628a-112">包含要返回的标识符的属性标记。</span><span class="sxs-lookup"><span data-stu-id="f628a-112">Property tag that contains the identifier to be returned.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f628a-113">注解</span><span class="sxs-lookup"><span data-stu-id="f628a-113">Remarks</span></span>

<span data-ttu-id="f628a-114">每个属性标记包含低序位 word （0 到 15 位） 中的属性类型和高顺序单词 （通过 31 16 位） 中的属性标识符。</span><span class="sxs-lookup"><span data-stu-id="f628a-114">Every property tag contains the property type in the low-order word (bits 0 through 15) and the property identifier in the high-order word (bits 16 through 31).</span></span> <span data-ttu-id="f628a-115">**PROP_ID**宏提取属性标识符，并将其放入位 0 到 15 的整数要返回。</span><span class="sxs-lookup"><span data-stu-id="f628a-115">The **PROP_ID** macro extracts the property identifier and puts it in bits 0 through 15 of the integer to be returned.</span></span> <span data-ttu-id="f628a-116">返回值的剩余的位设置为零。</span><span class="sxs-lookup"><span data-stu-id="f628a-116">The remaining bits of the return value are set to zeros.</span></span> 
  
<span data-ttu-id="f628a-117">例如， **PROP_ID**宏可用于检索要传递给[IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md)标识符。</span><span class="sxs-lookup"><span data-stu-id="f628a-117">The **PROP_ID** macro can be used, for example, to retrieve an identifier to pass to [IMAPIProp::GetNamesFromIDs](imapiprop-getnamesfromids.md).</span></span> <span data-ttu-id="f628a-118">**GetNamesFromIDs**检索与命名属性的标识符关联的属性名称。</span><span class="sxs-lookup"><span data-stu-id="f628a-118">**GetNamesFromIDs** retrieves the property name associated with an identifier for a named property.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="f628a-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f628a-119">See also</span></span>



[<span data-ttu-id="f628a-120">SPropValue</span><span class="sxs-lookup"><span data-stu-id="f628a-120">SPropValue</span></span>](spropvalue.md)


[<span data-ttu-id="f628a-121">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="f628a-121">Macros Related to Structures</span></span>](macros-related-to-structures.md)

