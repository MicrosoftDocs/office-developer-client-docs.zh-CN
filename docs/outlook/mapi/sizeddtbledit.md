---
title: SizedDtblEdit
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedDtblEdit
api_type:
- COM
ms.assetid: a658d027-03a2-4cde-bf99-563e8521cb31
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 4ea77023bdc9442325f4af46d23c107e7172ceaf
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778789"
---
# <a name="sizeddtbledit"></a><span data-ttu-id="3a8de-103">SizedDtblEdit</span><span class="sxs-lookup"><span data-stu-id="3a8de-103">SizedDtblEdit</span></span>

<span data-ttu-id="3a8de-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3a8de-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3a8de-105">创建一个名为的结构包含用于描述编辑控件和最大可以在控件中输入的字符数[DTBLEDIT](dtbledit.md)结构。</span><span class="sxs-lookup"><span data-stu-id="3a8de-105">Creates a named structure that includes a [DTBLEDIT](dtbledit.md) structure for describing an edit control and the maximum number of characters that can be entered in the control.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="3a8de-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="3a8de-106">Header file:</span></span>  <br/> |<span data-ttu-id="3a8de-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="3a8de-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="3a8de-108">相关的结构：</span><span class="sxs-lookup"><span data-stu-id="3a8de-108">Related structure:</span></span>  <br/> |<span data-ttu-id="3a8de-109">**DTBLEDIT**</span><span class="sxs-lookup"><span data-stu-id="3a8de-109">**DTBLEDIT**</span></span> <br/> |
   
```cpp
SizedDtblEdit (n, u)
```

## <a name="parameters"></a><span data-ttu-id="3a8de-110">参数</span><span class="sxs-lookup"><span data-stu-id="3a8de-110">Parameters</span></span>

<span data-ttu-id="3a8de-111">_n_</span><span class="sxs-lookup"><span data-stu-id="3a8de-111">_n_</span></span>
  
> <span data-ttu-id="3a8de-112">最大可编辑控件中输入的字符数。</span><span class="sxs-lookup"><span data-stu-id="3a8de-112">Maximum number of characters that can be entered in the edit control.</span></span>
    
<span data-ttu-id="3a8de-113">_u_</span><span class="sxs-lookup"><span data-stu-id="3a8de-113">_u_</span></span>
  
> <span data-ttu-id="3a8de-114">新结构的的名称。</span><span class="sxs-lookup"><span data-stu-id="3a8de-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="3a8de-115">备注</span><span class="sxs-lookup"><span data-stu-id="3a8de-115">Remarks</span></span>

<span data-ttu-id="3a8de-116">**SizedDtblEdit**宏允许您定义的编辑控件时已知的已启用的字符数。</span><span class="sxs-lookup"><span data-stu-id="3a8de-116">The **SizedDtblEdit** macro lets you define an edit control when the number of enabled characters is known.</span></span> <span data-ttu-id="3a8de-117">使用下列成员来创建新的结构：</span><span class="sxs-lookup"><span data-stu-id="3a8de-117">The new structure is created with the following members:</span></span> 
  
```cpp
DTBLEDIT dtbledit;
TCHAR lpszCharsAllowed[n];

```

<span data-ttu-id="3a8de-118">若要将指针生成结构从**SizedDtblEdit**宏作为**DTBLEDIT**结构指针，执行以下的强制转换：</span><span class="sxs-lookup"><span data-stu-id="3a8de-118">To use a pointer to the resulting structure from the **SizedDtblEdit** macro as a **DTBLEDIT** structure pointer, perform the following cast:</span></span> 
  
```cpp
lpDtblEdit = (LPDTBLEDIT) &SizedDtblEdit;

```

## <a name="see-also"></a><span data-ttu-id="3a8de-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3a8de-119">See also</span></span>

- [<span data-ttu-id="3a8de-120">DTBLEDIT</span><span class="sxs-lookup"><span data-stu-id="3a8de-120">DTBLEDIT</span></span>](dtbledit.md)
- [<span data-ttu-id="3a8de-121">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="3a8de-121">Macros Related to Structures</span></span>](macros-related-to-structures.md)

