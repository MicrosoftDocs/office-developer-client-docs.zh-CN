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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7e50589b52f3e99bf2569a55bb7d3ca4f8247fd6
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22591658"
---
# <a name="sizeddtbledit"></a><span data-ttu-id="851ba-103">SizedDtblEdit</span><span class="sxs-lookup"><span data-stu-id="851ba-103">SizedDtblEdit</span></span>

<span data-ttu-id="851ba-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="851ba-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="851ba-105">创建一个名为的结构包含用于描述编辑控件和最大可以在控件中输入的字符数[DTBLEDIT](dtbledit.md)结构。</span><span class="sxs-lookup"><span data-stu-id="851ba-105">Creates a named structure that includes a [DTBLEDIT](dtbledit.md) structure for describing an edit control and the maximum number of characters that can be entered in the control.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="851ba-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="851ba-106">Header file:</span></span>  <br/> |<span data-ttu-id="851ba-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="851ba-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="851ba-108">相关的结构：</span><span class="sxs-lookup"><span data-stu-id="851ba-108">Related structure:</span></span>  <br/> |<span data-ttu-id="851ba-109">**DTBLEDIT**</span><span class="sxs-lookup"><span data-stu-id="851ba-109">**DTBLEDIT**</span></span> <br/> |
   
```cpp
SizedDtblEdit (n, u)
```

## <a name="parameters"></a><span data-ttu-id="851ba-110">参数</span><span class="sxs-lookup"><span data-stu-id="851ba-110">Parameters</span></span>

<span data-ttu-id="851ba-111">_n_</span><span class="sxs-lookup"><span data-stu-id="851ba-111">_n_</span></span>
  
> <span data-ttu-id="851ba-112">最大可编辑控件中输入的字符数。</span><span class="sxs-lookup"><span data-stu-id="851ba-112">Maximum number of characters that can be entered in the edit control.</span></span>
    
<span data-ttu-id="851ba-113">_u_</span><span class="sxs-lookup"><span data-stu-id="851ba-113">_u_</span></span>
  
> <span data-ttu-id="851ba-114">新结构的的名称。</span><span class="sxs-lookup"><span data-stu-id="851ba-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="851ba-115">注解</span><span class="sxs-lookup"><span data-stu-id="851ba-115">Remarks</span></span>

<span data-ttu-id="851ba-116">**SizedDtblEdit**宏允许您定义的编辑控件时已知的已启用的字符数。</span><span class="sxs-lookup"><span data-stu-id="851ba-116">The **SizedDtblEdit** macro lets you define an edit control when the number of enabled characters is known.</span></span> <span data-ttu-id="851ba-117">使用下列成员来创建新的结构：</span><span class="sxs-lookup"><span data-stu-id="851ba-117">The new structure is created with the following members:</span></span> 
  
```cpp
DTBLEDIT dtbledit;
TCHAR lpszCharsAllowed[n];

```

<span data-ttu-id="851ba-118">若要将指针生成结构从**SizedDtblEdit**宏作为**DTBLEDIT**结构指针，执行以下的强制转换：</span><span class="sxs-lookup"><span data-stu-id="851ba-118">To use a pointer to the resulting structure from the **SizedDtblEdit** macro as a **DTBLEDIT** structure pointer, perform the following cast:</span></span> 
  
```cpp
lpDtblEdit = (LPDTBLEDIT) &SizedDtblEdit;

```

## <a name="see-also"></a><span data-ttu-id="851ba-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="851ba-119">See also</span></span>

- [<span data-ttu-id="851ba-120">DTBLEDIT</span><span class="sxs-lookup"><span data-stu-id="851ba-120">DTBLEDIT</span></span>](dtbledit.md)
- [<span data-ttu-id="851ba-121">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="851ba-121">Macros Related to Structures</span></span>](macros-related-to-structures.md)

