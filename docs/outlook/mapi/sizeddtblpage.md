---
title: SizedDtblPage
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedDtblPage
api_type:
- COM
ms.assetid: 47b2a69d-e902-429f-8b31-166b51aeaf7f
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a1530443600df7cb73ff27d5cfbeab46f81bc53c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778792"
---
# <a name="sizeddtblpage"></a><span data-ttu-id="e0ca5-103">SizedDtblPage</span><span class="sxs-lookup"><span data-stu-id="e0ca5-103">SizedDtblPage</span></span>

<span data-ttu-id="e0ca5-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="e0ca5-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="e0ca5-105">创建一个名为的结构包含用于描述的选项卡式的页面控件、 标签指定长度的和具有指定长度的帮助文件项[DTBLPAGE](dtblpage.md)结构。</span><span class="sxs-lookup"><span data-stu-id="e0ca5-105">Creates a named structure that includes a [DTBLPAGE](dtblpage.md) structure for describing a tabbed page control, a label of a specified length, and a Help file entry of a specified length.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e0ca5-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="e0ca5-106">Header file:</span></span>  <br/> |<span data-ttu-id="e0ca5-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="e0ca5-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="e0ca5-108">相关的结构：</span><span class="sxs-lookup"><span data-stu-id="e0ca5-108">Related structure:</span></span>  <br/> |<span data-ttu-id="e0ca5-109">**DTBLPAGE**</span><span class="sxs-lookup"><span data-stu-id="e0ca5-109">**DTBLPAGE**</span></span> <br/> |
   
```cpp
SizedDtblPage (n, n1, u)
```

## <a name="parameters"></a><span data-ttu-id="e0ca5-110">参数</span><span class="sxs-lookup"><span data-stu-id="e0ca5-110">Parameters</span></span>

<span data-ttu-id="e0ca5-111">_n_</span><span class="sxs-lookup"><span data-stu-id="e0ca5-111">_n_</span></span>
  
> <span data-ttu-id="e0ca5-112">页面选项卡的标签的长度。</span><span class="sxs-lookup"><span data-stu-id="e0ca5-112">Length of the label for the page tab.</span></span>
    
<span data-ttu-id="e0ca5-113">_n1_</span><span class="sxs-lookup"><span data-stu-id="e0ca5-113">_n1_</span></span>
  
> <span data-ttu-id="e0ca5-114">确定将用于选项卡式的页面控件的帮助文件的 Mapisvc.inf 文件中显示该词条的长度。</span><span class="sxs-lookup"><span data-stu-id="e0ca5-114">Length of the entry appearing in the Mapisvc.inf file identifying the Help file that will be used with the tabbed page control.</span></span>
    
<span data-ttu-id="e0ca5-115">_u_</span><span class="sxs-lookup"><span data-stu-id="e0ca5-115">_u_</span></span>
  
> <span data-ttu-id="e0ca5-116">新结构的的名称。</span><span class="sxs-lookup"><span data-stu-id="e0ca5-116">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="e0ca5-117">说明</span><span class="sxs-lookup"><span data-stu-id="e0ca5-117">Remarks</span></span>

<span data-ttu-id="e0ca5-118">**SizedDtblPage**宏允许您定义的选项卡式的页面控件时已知的关联的标签名称和帮助文件项中的字符数。</span><span class="sxs-lookup"><span data-stu-id="e0ca5-118">The **SizedDtblPage** macro lets you define a tabbed page control when the number of characters in the associated label and Help file entry is known.</span></span> <span data-ttu-id="e0ca5-119">使用下列成员来创建新的结构：</span><span class="sxs-lookup"><span data-stu-id="e0ca5-119">The new structure is created with the following members:</span></span> 
  
```cpp
DTBLPAGE dtblpage;
TCHAR lpszLabel[n];
TCHAR lpszComponent[n1];
```

<span data-ttu-id="e0ca5-120">若要将指针生成结构从**SizedDtblPage**宏作为**DTBLPAGE**结构指针，执行以下的强制转换：</span><span class="sxs-lookup"><span data-stu-id="e0ca5-120">To use a pointer to the resulting structure from the **SizedDtblPage** macro as a **DTBLPAGE** structure pointer, perform the following cast:</span></span> 
  
```cpp
lpDtblPage = (LPDTBLPAGE) &SizedDtblPage;
```

## <a name="see-also"></a><span data-ttu-id="e0ca5-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e0ca5-121">See also</span></span>

- [<span data-ttu-id="e0ca5-122">DTBLPAGE</span><span class="sxs-lookup"><span data-stu-id="e0ca5-122">DTBLPAGE</span></span>](dtblpage.md)
- [<span data-ttu-id="e0ca5-123">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="e0ca5-123">Macros Related to Structures</span></span>](macros-related-to-structures.md)

