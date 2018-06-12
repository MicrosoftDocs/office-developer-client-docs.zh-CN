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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 9a30554253bc11c8905273079429e4b41c20583a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778784"
---
# <a name="sizeddtblcheckbox"></a><span data-ttu-id="ff2e2-103">SizedDtblCheckBox</span><span class="sxs-lookup"><span data-stu-id="ff2e2-103">SizedDtblCheckBox</span></span>
 
<span data-ttu-id="ff2e2-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="ff2e2-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="ff2e2-105">创建一个名为的结构包含用于描述复选框控件和一个指定长度的标签[DTBLCHECKBOX](dtblcheckbox.md)结构。</span><span class="sxs-lookup"><span data-stu-id="ff2e2-105">Creates a named structure that includes a [DTBLCHECKBOX](dtblcheckbox.md) structure for describing a check box control and a label of a specified length.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="ff2e2-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="ff2e2-106">Header file:</span></span>  <br/> |<span data-ttu-id="ff2e2-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="ff2e2-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="ff2e2-108">相关的结构：</span><span class="sxs-lookup"><span data-stu-id="ff2e2-108">Related structure:</span></span>  <br/> |<span data-ttu-id="ff2e2-109">**DTBLCHECKBOX**</span><span class="sxs-lookup"><span data-stu-id="ff2e2-109">**DTBLCHECKBOX**</span></span> <br/> |
   
```cpp
SizedDtblCheckBox (n, u)
```

## <a name="parameters"></a><span data-ttu-id="ff2e2-110">参数</span><span class="sxs-lookup"><span data-stu-id="ff2e2-110">Parameters</span></span>

<span data-ttu-id="ff2e2-111">_n_</span><span class="sxs-lookup"><span data-stu-id="ff2e2-111">_n_</span></span>
  
> <span data-ttu-id="ff2e2-112">标签的新结构中包含的长度。</span><span class="sxs-lookup"><span data-stu-id="ff2e2-112">Length of the label to be included in the new structure.</span></span>
    
<span data-ttu-id="ff2e2-113">_u_</span><span class="sxs-lookup"><span data-stu-id="ff2e2-113">_u_</span></span>
  
> <span data-ttu-id="ff2e2-114">新结构的的名称。</span><span class="sxs-lookup"><span data-stu-id="ff2e2-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="ff2e2-115">备注</span><span class="sxs-lookup"><span data-stu-id="ff2e2-115">Remarks</span></span>

<span data-ttu-id="ff2e2-116">**SizedDtblCheckBox**宏可以定义一个复选框，当已知的标签字符数。</span><span class="sxs-lookup"><span data-stu-id="ff2e2-116">The **SizedDtblCheckBox** macro lets you define a check box when the number of label characters is known.</span></span> <span data-ttu-id="ff2e2-117">使用下列成员来创建新的结构：</span><span class="sxs-lookup"><span data-stu-id="ff2e2-117">The new structure is created with the following members:</span></span> 
  
```cpp
DTBLCHECKBOX dtblcheckbox;
TCHAR lpszLabel[n];
```

<span data-ttu-id="ff2e2-118">若要将指针生成结构从**SizedDtblCheckBox**宏作为**DTBLCHECKBOX**结构指针，执行以下的强制转换：</span><span class="sxs-lookup"><span data-stu-id="ff2e2-118">To use a pointer to the resulting structure from the **SizedDtblCheckBox** macro as a **DTBLCHECKBOX** structure pointer, perform the following cast:</span></span> 
  
```cpp
lpDtblCheckBox = (LPDTBLCHECKBOX) &SizedDtblCheckBox;
```

## <a name="see-also"></a><span data-ttu-id="ff2e2-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ff2e2-119">See also</span></span>

- [<span data-ttu-id="ff2e2-120">DTBLCHECKBOX</span><span class="sxs-lookup"><span data-stu-id="ff2e2-120">DTBLCHECKBOX</span></span>](dtblcheckbox.md)
- [<span data-ttu-id="ff2e2-121">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="ff2e2-121">Macros Related to Structures</span></span>](macros-related-to-structures.md)

