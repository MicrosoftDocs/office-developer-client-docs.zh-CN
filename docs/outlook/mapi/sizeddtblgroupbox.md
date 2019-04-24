---
title: SizedDtblGroupBox
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedDtblGroupBox
api_type:
- COM
ms.assetid: 7ca01bf7-5185-41cc-907e-01f256345997
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 0a9bda8831f4a38b62d71a54115c40bb3374d97d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282731"
---
# <a name="sizeddtblgroupbox"></a><span data-ttu-id="580dc-103">SizedDtblGroupBox</span><span class="sxs-lookup"><span data-stu-id="580dc-103">SizedDtblGroupBox</span></span>

<span data-ttu-id="580dc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="580dc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="580dc-105">创建一个命名结构, 其中包含一个用于描述分组框控件和一个指定长度的标签的[DTBLGROUPBOX](dtblgroupbox.md)结构。</span><span class="sxs-lookup"><span data-stu-id="580dc-105">Creates a named structure that includes a [DTBLGROUPBOX](dtblgroupbox.md) structure for describing a group box control and a label of a specified length.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="580dc-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="580dc-106">Header file:</span></span>  <br/> |<span data-ttu-id="580dc-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="580dc-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="580dc-108">相关结构:</span><span class="sxs-lookup"><span data-stu-id="580dc-108">Related structure:</span></span>  <br/> |<span data-ttu-id="580dc-109">**DTBLGROUPBOX**</span><span class="sxs-lookup"><span data-stu-id="580dc-109">**DTBLGROUPBOX**</span></span> <br/> |
   
```cpp
SizedDtblGroupBox (n, u)
```

## <a name="parameters"></a><span data-ttu-id="580dc-110">参数</span><span class="sxs-lookup"><span data-stu-id="580dc-110">Parameters</span></span>

<span data-ttu-id="580dc-111">_n_</span><span class="sxs-lookup"><span data-stu-id="580dc-111">_n_</span></span>
  
> <span data-ttu-id="580dc-112">分组框标签的长度。</span><span class="sxs-lookup"><span data-stu-id="580dc-112">Length of the group box's label.</span></span> 
    
<span data-ttu-id="580dc-113">_u_</span><span class="sxs-lookup"><span data-stu-id="580dc-113">_u_</span></span>
  
> <span data-ttu-id="580dc-114">新结构的名称。</span><span class="sxs-lookup"><span data-stu-id="580dc-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="580dc-115">注解</span><span class="sxs-lookup"><span data-stu-id="580dc-115">Remarks</span></span>

<span data-ttu-id="580dc-116">**SizedDtblGroupBox**宏允许您在标签的长度已知时定义一个分组框控件。</span><span class="sxs-lookup"><span data-stu-id="580dc-116">The **SizedDtblGroupBox** macro lets you define a group box control when the length of the label is known.</span></span> <span data-ttu-id="580dc-117">新结构是使用以下成员创建的:</span><span class="sxs-lookup"><span data-stu-id="580dc-117">The new structure is created with the following members:</span></span> 
  
```cpp
DTBLGROUPBOX dtblgroupbox;
TCHAR lpszLabel[n];

```

<span data-ttu-id="580dc-118">若要将指向**SizedDtblGroupBox**宏的结果结构的指针用作**DTBLGROUPBOX**结构指针, 请执行以下转换:</span><span class="sxs-lookup"><span data-stu-id="580dc-118">To use a pointer to the resulting structure from the **SizedDtblGroupBox** macro as a **DTBLGROUPBOX** structure pointer, perform the following cast:</span></span> 
  
```cpp
lpDtblGroupBox = (LPDTBLGROUPBOX) &SizedDtblGroupBox;

```

## <a name="see-also"></a><span data-ttu-id="580dc-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="580dc-119">See also</span></span>

- [<span data-ttu-id="580dc-120">DTBLGROUPBOX</span><span class="sxs-lookup"><span data-stu-id="580dc-120">DTBLGROUPBOX</span></span>](dtblgroupbox.md)
- [<span data-ttu-id="580dc-121">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="580dc-121">Macros Related to Structures</span></span>](macros-related-to-structures.md)

