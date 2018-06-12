---
title: SizedDtblLabel
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedDtblLabel
api_type:
- COM
ms.assetid: c7cb8cf9-7abd-4ee3-b88c-d61695f4ed31
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: c2e275e373677e50510a0aa87f5060070a870a0f
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778806"
---
# <a name="sizeddtbllabel"></a><span data-ttu-id="4a097-103">SizedDtblLabel</span><span class="sxs-lookup"><span data-stu-id="4a097-103">SizedDtblLabel</span></span>

<span data-ttu-id="4a097-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="4a097-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="4a097-105">创建一个名为的结构包含用于描述 label 控件和指定长度的关联的标签[DTBLLABEL](dtbllabel.md)结构。</span><span class="sxs-lookup"><span data-stu-id="4a097-105">Creates a named structure that includes a [DTBLLABEL](dtbllabel.md) structure for describing a label control and the associated label of a specified length.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4a097-106">头文件中指定：</span><span class="sxs-lookup"><span data-stu-id="4a097-106">Specified in header file:</span></span>  <br/> |<span data-ttu-id="4a097-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="4a097-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="4a097-108">相关的结构</span><span class="sxs-lookup"><span data-stu-id="4a097-108">Related structure</span></span>  <br/> |<span data-ttu-id="4a097-109">**DTBLLABEL**</span><span class="sxs-lookup"><span data-stu-id="4a097-109">**DTBLLABEL**</span></span> <br/> |
   
```cpp
SizedDtblLabel (n, u)
```

## <a name="parameters"></a><span data-ttu-id="4a097-110">参数</span><span class="sxs-lookup"><span data-stu-id="4a097-110">Parameters</span></span>

<span data-ttu-id="4a097-111">_n_</span><span class="sxs-lookup"><span data-stu-id="4a097-111">_n_</span></span>
  
> <span data-ttu-id="4a097-112">标签的长度。</span><span class="sxs-lookup"><span data-stu-id="4a097-112">Length of the label.</span></span> <span data-ttu-id="4a097-113">这包括结束 NULL 字符。</span><span class="sxs-lookup"><span data-stu-id="4a097-113">This includes the ending NULL character.</span></span> 
    
<span data-ttu-id="4a097-114">_u_</span><span class="sxs-lookup"><span data-stu-id="4a097-114">_u_</span></span>
  
> <span data-ttu-id="4a097-115">新结构的的名称。</span><span class="sxs-lookup"><span data-stu-id="4a097-115">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="4a097-116">备注</span><span class="sxs-lookup"><span data-stu-id="4a097-116">Remarks</span></span>

<span data-ttu-id="4a097-117">**SizedDtblLabel**宏允许您定义显示表标签时已知的标签中的字符数。</span><span class="sxs-lookup"><span data-stu-id="4a097-117">The **SizedDtblLabel** macro lets you define a display table label when the number of characters in the label is known.</span></span> <span data-ttu-id="4a097-118">使用下列成员来创建新的结构：</span><span class="sxs-lookup"><span data-stu-id="4a097-118">The new structure is created with the following members:</span></span> 
  
```cpp
DTBLLABEL dtbllabel;
TCHAR lpszLabelName[n];
```

<span data-ttu-id="4a097-119">若要将指针生成结构从**SizedDtblLabel**宏作为**DTBLLABEL**结构指针，执行以下的强制转换：</span><span class="sxs-lookup"><span data-stu-id="4a097-119">To use a pointer to the resulting structure from the **SizedDtblLabel** macro as a **DTBLLABEL** structure pointer, perform the following cast:</span></span> 
  
```cpp
lpDtblLabel = (LPDTBLLABEL) &SizedDtblLabel;
```

## <a name="see-also"></a><span data-ttu-id="4a097-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4a097-120">See also</span></span>

- [<span data-ttu-id="4a097-121">DTBLLABEL</span><span class="sxs-lookup"><span data-stu-id="4a097-121">DTBLLABEL</span></span>](dtbllabel.md)
- [<span data-ttu-id="4a097-122">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="4a097-122">Macros Related to Structures</span></span>](macros-related-to-structures.md)

