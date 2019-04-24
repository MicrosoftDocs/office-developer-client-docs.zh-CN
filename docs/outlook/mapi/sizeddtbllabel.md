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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1ae675d1d4adf841e18bbfc8990913136afe8b4b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282703"
---
# <a name="sizeddtbllabel"></a><span data-ttu-id="e2243-103">SizedDtblLabel</span><span class="sxs-lookup"><span data-stu-id="e2243-103">SizedDtblLabel</span></span>

<span data-ttu-id="e2243-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e2243-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e2243-105">创建一个命名的结构, 其中包含用于描述标签控件和指定长度的关联标签的[DTBLLABEL](dtbllabel.md)结构。</span><span class="sxs-lookup"><span data-stu-id="e2243-105">Creates a named structure that includes a [DTBLLABEL](dtbllabel.md) structure for describing a label control and the associated label of a specified length.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e2243-106">在头文件中指定:</span><span class="sxs-lookup"><span data-stu-id="e2243-106">Specified in header file:</span></span>  <br/> |<span data-ttu-id="e2243-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="e2243-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="e2243-108">相关结构</span><span class="sxs-lookup"><span data-stu-id="e2243-108">Related structure</span></span>  <br/> |<span data-ttu-id="e2243-109">**DTBLLABEL**</span><span class="sxs-lookup"><span data-stu-id="e2243-109">**DTBLLABEL**</span></span> <br/> |
   
```cpp
SizedDtblLabel (n, u)
```

## <a name="parameters"></a><span data-ttu-id="e2243-110">参数</span><span class="sxs-lookup"><span data-stu-id="e2243-110">Parameters</span></span>

<span data-ttu-id="e2243-111">_n_</span><span class="sxs-lookup"><span data-stu-id="e2243-111">_n_</span></span>
  
> <span data-ttu-id="e2243-112">标签的长度。</span><span class="sxs-lookup"><span data-stu-id="e2243-112">Length of the label.</span></span> <span data-ttu-id="e2243-113">这包括结尾的 NULL 字符。</span><span class="sxs-lookup"><span data-stu-id="e2243-113">This includes the ending NULL character.</span></span> 
    
<span data-ttu-id="e2243-114">_u_</span><span class="sxs-lookup"><span data-stu-id="e2243-114">_u_</span></span>
  
> <span data-ttu-id="e2243-115">新结构的名称。</span><span class="sxs-lookup"><span data-stu-id="e2243-115">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e2243-116">注解</span><span class="sxs-lookup"><span data-stu-id="e2243-116">Remarks</span></span>

<span data-ttu-id="e2243-117">**SizedDtblLabel**宏允许您在标签中的字符数已知时定义显示表标签。</span><span class="sxs-lookup"><span data-stu-id="e2243-117">The **SizedDtblLabel** macro lets you define a display table label when the number of characters in the label is known.</span></span> <span data-ttu-id="e2243-118">新结构是使用以下成员创建的:</span><span class="sxs-lookup"><span data-stu-id="e2243-118">The new structure is created with the following members:</span></span> 
  
```cpp
DTBLLABEL dtbllabel;
TCHAR lpszLabelName[n];
```

<span data-ttu-id="e2243-119">若要将指向**SizedDtblLabel**宏的结果结构的指针用作**DTBLLABEL**结构指针, 请执行以下转换:</span><span class="sxs-lookup"><span data-stu-id="e2243-119">To use a pointer to the resulting structure from the **SizedDtblLabel** macro as a **DTBLLABEL** structure pointer, perform the following cast:</span></span> 
  
```cpp
lpDtblLabel = (LPDTBLLABEL) &SizedDtblLabel;
```

## <a name="see-also"></a><span data-ttu-id="e2243-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e2243-120">See also</span></span>

- [<span data-ttu-id="e2243-121">DTBLLABEL</span><span class="sxs-lookup"><span data-stu-id="e2243-121">DTBLLABEL</span></span>](dtbllabel.md)
- [<span data-ttu-id="e2243-122">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="e2243-122">Macros Related to Structures</span></span>](macros-related-to-structures.md)

