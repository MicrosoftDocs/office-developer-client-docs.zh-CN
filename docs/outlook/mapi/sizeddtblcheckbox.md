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
ms.openlocfilehash: 6120439ea0d98ed6b64fe1542a4372265574723a
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567529"
---
# <a name="sizeddtblcheckbox"></a><span data-ttu-id="39548-103">SizedDtblCheckBox</span><span class="sxs-lookup"><span data-stu-id="39548-103">SizedDtblCheckBox</span></span>
 
<span data-ttu-id="39548-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="39548-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="39548-105">创建一个名为的结构包含用于描述复选框控件和一个指定长度的标签[DTBLCHECKBOX](dtblcheckbox.md)结构。</span><span class="sxs-lookup"><span data-stu-id="39548-105">Creates a named structure that includes a [DTBLCHECKBOX](dtblcheckbox.md) structure for describing a check box control and a label of a specified length.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="39548-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="39548-106">Header file:</span></span>  <br/> |<span data-ttu-id="39548-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="39548-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="39548-108">相关的结构：</span><span class="sxs-lookup"><span data-stu-id="39548-108">Related structure:</span></span>  <br/> |<span data-ttu-id="39548-109">**DTBLCHECKBOX**</span><span class="sxs-lookup"><span data-stu-id="39548-109">**DTBLCHECKBOX**</span></span> <br/> |
   
```cpp
SizedDtblCheckBox (n, u)
```

## <a name="parameters"></a><span data-ttu-id="39548-110">参数</span><span class="sxs-lookup"><span data-stu-id="39548-110">Parameters</span></span>

<span data-ttu-id="39548-111">_n_</span><span class="sxs-lookup"><span data-stu-id="39548-111">_n_</span></span>
  
> <span data-ttu-id="39548-112">标签的新结构中包含的长度。</span><span class="sxs-lookup"><span data-stu-id="39548-112">Length of the label to be included in the new structure.</span></span>
    
<span data-ttu-id="39548-113">_u_</span><span class="sxs-lookup"><span data-stu-id="39548-113">_u_</span></span>
  
> <span data-ttu-id="39548-114">新结构的的名称。</span><span class="sxs-lookup"><span data-stu-id="39548-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="39548-115">注解</span><span class="sxs-lookup"><span data-stu-id="39548-115">Remarks</span></span>

<span data-ttu-id="39548-116">**SizedDtblCheckBox**宏可以定义一个复选框，当已知的标签字符数。</span><span class="sxs-lookup"><span data-stu-id="39548-116">The **SizedDtblCheckBox** macro lets you define a check box when the number of label characters is known.</span></span> <span data-ttu-id="39548-117">使用下列成员来创建新的结构：</span><span class="sxs-lookup"><span data-stu-id="39548-117">The new structure is created with the following members:</span></span> 
  
```cpp
DTBLCHECKBOX dtblcheckbox;
TCHAR lpszLabel[n];
```

<span data-ttu-id="39548-118">若要将指针生成结构从**SizedDtblCheckBox**宏作为**DTBLCHECKBOX**结构指针，执行以下的强制转换：</span><span class="sxs-lookup"><span data-stu-id="39548-118">To use a pointer to the resulting structure from the **SizedDtblCheckBox** macro as a **DTBLCHECKBOX** structure pointer, perform the following cast:</span></span> 
  
```cpp
lpDtblCheckBox = (LPDTBLCHECKBOX) &SizedDtblCheckBox;
```

## <a name="see-also"></a><span data-ttu-id="39548-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39548-119">See also</span></span>

- [<span data-ttu-id="39548-120">DTBLCHECKBOX</span><span class="sxs-lookup"><span data-stu-id="39548-120">DTBLCHECKBOX</span></span>](dtblcheckbox.md)
- [<span data-ttu-id="39548-121">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="39548-121">Macros Related to Structures</span></span>](macros-related-to-structures.md)

