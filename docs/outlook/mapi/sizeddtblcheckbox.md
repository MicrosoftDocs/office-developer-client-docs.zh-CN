---
title: SizedDtblCheckBox
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedDtblCheckBox
api_type:
- COM
ms.assetid: 9d04a124-54d4-43ac-967f-ea8e7a09b1d0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6d23d56a27095497aedc64d7bbf5ffda266d0c97
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282752"
---
# <a name="sizeddtblcheckbox"></a><span data-ttu-id="4c7f3-103">SizedDtblCheckBox</span><span class="sxs-lookup"><span data-stu-id="4c7f3-103">SizedDtblCheckBox</span></span>
 
<span data-ttu-id="4c7f3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4c7f3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4c7f3-105">创建一个命名的结构, 其中包含用于描述复选框控件和标签指定长度的[DTBLCHECKBOX](dtblcheckbox.md)结构。</span><span class="sxs-lookup"><span data-stu-id="4c7f3-105">Creates a named structure that includes a [DTBLCHECKBOX](dtblcheckbox.md) structure for describing a check box control and a label of a specified length.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4c7f3-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="4c7f3-106">Header file:</span></span>  <br/> |<span data-ttu-id="4c7f3-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="4c7f3-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="4c7f3-108">相关结构:</span><span class="sxs-lookup"><span data-stu-id="4c7f3-108">Related structure:</span></span>  <br/> |<span data-ttu-id="4c7f3-109">**DTBLCHECKBOX**</span><span class="sxs-lookup"><span data-stu-id="4c7f3-109">**DTBLCHECKBOX**</span></span> <br/> |
   
```cpp
SizedDtblCheckBox (n, u)
```

## <a name="parameters"></a><span data-ttu-id="4c7f3-110">参数</span><span class="sxs-lookup"><span data-stu-id="4c7f3-110">Parameters</span></span>

<span data-ttu-id="4c7f3-111">_n_</span><span class="sxs-lookup"><span data-stu-id="4c7f3-111">_n_</span></span>
  
> <span data-ttu-id="4c7f3-112">要包含在新结构中的标签的长度。</span><span class="sxs-lookup"><span data-stu-id="4c7f3-112">Length of the label to be included in the new structure.</span></span>
    
<span data-ttu-id="4c7f3-113">_u_</span><span class="sxs-lookup"><span data-stu-id="4c7f3-113">_u_</span></span>
  
> <span data-ttu-id="4c7f3-114">新结构的名称。</span><span class="sxs-lookup"><span data-stu-id="4c7f3-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="4c7f3-115">注解</span><span class="sxs-lookup"><span data-stu-id="4c7f3-115">Remarks</span></span>

<span data-ttu-id="4c7f3-116">**SizedDtblCheckBox**宏允许您在标签字符的数目已知时定义复选框。</span><span class="sxs-lookup"><span data-stu-id="4c7f3-116">The **SizedDtblCheckBox** macro lets you define a check box when the number of label characters is known.</span></span> <span data-ttu-id="4c7f3-117">新结构是使用以下成员创建的:</span><span class="sxs-lookup"><span data-stu-id="4c7f3-117">The new structure is created with the following members:</span></span> 
  
```cpp
DTBLCHECKBOX dtblcheckbox;
TCHAR lpszLabel[n];
```

<span data-ttu-id="4c7f3-118">若要将指向**SizedDtblCheckBox**宏的结果结构的指针用作**DTBLCHECKBOX**结构指针, 请执行以下转换:</span><span class="sxs-lookup"><span data-stu-id="4c7f3-118">To use a pointer to the resulting structure from the **SizedDtblCheckBox** macro as a **DTBLCHECKBOX** structure pointer, perform the following cast:</span></span> 
  
```cpp
lpDtblCheckBox = (LPDTBLCHECKBOX) &SizedDtblCheckBox;
```

## <a name="see-also"></a><span data-ttu-id="4c7f3-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4c7f3-119">See also</span></span>

- [<span data-ttu-id="4c7f3-120">DTBLCHECKBOX</span><span class="sxs-lookup"><span data-stu-id="4c7f3-120">DTBLCHECKBOX</span></span>](dtblcheckbox.md)
- [<span data-ttu-id="4c7f3-121">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="4c7f3-121">Macros Related to Structures</span></span>](macros-related-to-structures.md)

