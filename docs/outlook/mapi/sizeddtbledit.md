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
ms.openlocfilehash: b5b9c42d944ad9d3ce92e99d08d29964944c8028
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437642"
---
# <a name="sizeddtbledit"></a><span data-ttu-id="fac8d-103">SizedDtblEdit</span><span class="sxs-lookup"><span data-stu-id="fac8d-103">SizedDtblEdit</span></span>

<span data-ttu-id="fac8d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="fac8d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="fac8d-105">创建一个命名结构，其中包含描述编辑控件的 [DTBLEDIT](dtbledit.md) 结构以及可在控件中输入的最大字符数。</span><span class="sxs-lookup"><span data-stu-id="fac8d-105">Creates a named structure that includes a [DTBLEDIT](dtbledit.md) structure for describing an edit control and the maximum number of characters that can be entered in the control.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="fac8d-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="fac8d-106">Header file:</span></span>  <br/> |<span data-ttu-id="fac8d-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="fac8d-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="fac8d-108">相关结构：</span><span class="sxs-lookup"><span data-stu-id="fac8d-108">Related structure:</span></span>  <br/> |<span data-ttu-id="fac8d-109">**DTBLEDIT**</span><span class="sxs-lookup"><span data-stu-id="fac8d-109">**DTBLEDIT**</span></span> <br/> |
   
```cpp
SizedDtblEdit (n, u)
```

## <a name="parameters"></a><span data-ttu-id="fac8d-110">参数</span><span class="sxs-lookup"><span data-stu-id="fac8d-110">Parameters</span></span>

<span data-ttu-id="fac8d-111">_n_</span><span class="sxs-lookup"><span data-stu-id="fac8d-111">_n_</span></span>
  
> <span data-ttu-id="fac8d-112">可以在编辑控件中输入的最大字符数。</span><span class="sxs-lookup"><span data-stu-id="fac8d-112">Maximum number of characters that can be entered in the edit control.</span></span>
    
<span data-ttu-id="fac8d-113">_u_</span><span class="sxs-lookup"><span data-stu-id="fac8d-113">_u_</span></span>
  
> <span data-ttu-id="fac8d-114">新结构的名称。</span><span class="sxs-lookup"><span data-stu-id="fac8d-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="fac8d-115">备注</span><span class="sxs-lookup"><span data-stu-id="fac8d-115">Remarks</span></span>

<span data-ttu-id="fac8d-116">**SizedDtblEdit** 宏允许您在启用的字符数已知时定义编辑控件。</span><span class="sxs-lookup"><span data-stu-id="fac8d-116">The **SizedDtblEdit** macro lets you define an edit control when the number of enabled characters is known.</span></span> <span data-ttu-id="fac8d-117">新结构由以下成员创建：</span><span class="sxs-lookup"><span data-stu-id="fac8d-117">The new structure is created with the following members:</span></span> 
  
```cpp
DTBLEDIT dtbledit;
TCHAR lpszCharsAllowed[n];

```

<span data-ttu-id="fac8d-118">若要将指向 **SizedDtblEdit** 宏生成的结构的指针用作 **DTBLEDIT** 结构指针，请执行以下转换：</span><span class="sxs-lookup"><span data-stu-id="fac8d-118">To use a pointer to the resulting structure from the **SizedDtblEdit** macro as a **DTBLEDIT** structure pointer, perform the following cast:</span></span> 
  
```cpp
lpDtblEdit = (LPDTBLEDIT) &SizedDtblEdit;

```

## <a name="see-also"></a><span data-ttu-id="fac8d-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fac8d-119">See also</span></span>

- [<span data-ttu-id="fac8d-120">DTBLEDIT</span><span class="sxs-lookup"><span data-stu-id="fac8d-120">DTBLEDIT</span></span>](dtbledit.md)
- [<span data-ttu-id="fac8d-121">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="fac8d-121">Macros Related to Structures</span></span>](macros-related-to-structures.md)

