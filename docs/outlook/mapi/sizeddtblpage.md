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
ms.openlocfilehash: f14b8d7a9a73997f797f9cfa26a2e574222e839e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282655"
---
# <a name="sizeddtblpage"></a><span data-ttu-id="74a49-103">SizedDtblPage</span><span class="sxs-lookup"><span data-stu-id="74a49-103">SizedDtblPage</span></span>

<span data-ttu-id="74a49-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="74a49-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="74a49-105">创建一个命名的结构, 其中包含用于描述选项卡式页面控件的标签、指定长度的标签和指定长度的帮助文件条目的[DTBLPAGE](dtblpage.md)结构。</span><span class="sxs-lookup"><span data-stu-id="74a49-105">Creates a named structure that includes a [DTBLPAGE](dtblpage.md) structure for describing a tabbed page control, a label of a specified length, and a Help file entry of a specified length.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="74a49-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="74a49-106">Header file:</span></span>  <br/> |<span data-ttu-id="74a49-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="74a49-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="74a49-108">相关结构:</span><span class="sxs-lookup"><span data-stu-id="74a49-108">Related structure:</span></span>  <br/> |<span data-ttu-id="74a49-109">**DTBLPAGE**</span><span class="sxs-lookup"><span data-stu-id="74a49-109">**DTBLPAGE**</span></span> <br/> |
   
```cpp
SizedDtblPage (n, n1, u)
```

## <a name="parameters"></a><span data-ttu-id="74a49-110">参数</span><span class="sxs-lookup"><span data-stu-id="74a49-110">Parameters</span></span>

<span data-ttu-id="74a49-111">_n_</span><span class="sxs-lookup"><span data-stu-id="74a49-111">_n_</span></span>
  
> <span data-ttu-id="74a49-112">页面选项卡标签的长度。</span><span class="sxs-lookup"><span data-stu-id="74a49-112">Length of the label for the page tab.</span></span>
    
<span data-ttu-id="74a49-113">_n1_</span><span class="sxs-lookup"><span data-stu-id="74a49-113">_n1_</span></span>
  
> <span data-ttu-id="74a49-114">显示在 mapisvc.inf 文件中的条目的长度, 该文件标识将与选项卡式页面控件一起使用的帮助文件。</span><span class="sxs-lookup"><span data-stu-id="74a49-114">Length of the entry appearing in the Mapisvc.inf file identifying the Help file that will be used with the tabbed page control.</span></span>
    
<span data-ttu-id="74a49-115">_u_</span><span class="sxs-lookup"><span data-stu-id="74a49-115">_u_</span></span>
  
> <span data-ttu-id="74a49-116">新结构的名称。</span><span class="sxs-lookup"><span data-stu-id="74a49-116">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="74a49-117">注解</span><span class="sxs-lookup"><span data-stu-id="74a49-117">Remarks</span></span>

<span data-ttu-id="74a49-118">**SizedDtblPage**宏允许您在关联的标签和帮助文件条目中的字符数已知时定义选项卡式页面控件。</span><span class="sxs-lookup"><span data-stu-id="74a49-118">The **SizedDtblPage** macro lets you define a tabbed page control when the number of characters in the associated label and Help file entry is known.</span></span> <span data-ttu-id="74a49-119">新结构是使用以下成员创建的:</span><span class="sxs-lookup"><span data-stu-id="74a49-119">The new structure is created with the following members:</span></span> 
  
```cpp
DTBLPAGE dtblpage;
TCHAR lpszLabel[n];
TCHAR lpszComponent[n1];
```

<span data-ttu-id="74a49-120">若要将指向**SizedDtblPage**宏的结果结构的指针用作**DTBLPAGE**结构指针, 请执行以下转换:</span><span class="sxs-lookup"><span data-stu-id="74a49-120">To use a pointer to the resulting structure from the **SizedDtblPage** macro as a **DTBLPAGE** structure pointer, perform the following cast:</span></span> 
  
```cpp
lpDtblPage = (LPDTBLPAGE) &SizedDtblPage;
```

## <a name="see-also"></a><span data-ttu-id="74a49-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74a49-121">See also</span></span>

- [<span data-ttu-id="74a49-122">DTBLPAGE</span><span class="sxs-lookup"><span data-stu-id="74a49-122">DTBLPAGE</span></span>](dtblpage.md)
- [<span data-ttu-id="74a49-123">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="74a49-123">Macros Related to Structures</span></span>](macros-related-to-structures.md)

