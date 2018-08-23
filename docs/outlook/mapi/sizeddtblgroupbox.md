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
ms.openlocfilehash: 882638d5359154a56fa4438e7a62f213159f916d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581214"
---
# <a name="sizeddtblgroupbox"></a><span data-ttu-id="b458a-103">SizedDtblGroupBox</span><span class="sxs-lookup"><span data-stu-id="b458a-103">SizedDtblGroupBox</span></span>

<span data-ttu-id="b458a-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b458a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b458a-105">创建一个名为的结构包含用于描述组框控件和一个指定长度的标签[DTBLGROUPBOX](dtblgroupbox.md)结构。</span><span class="sxs-lookup"><span data-stu-id="b458a-105">Creates a named structure that includes a [DTBLGROUPBOX](dtblgroupbox.md) structure for describing a group box control and a label of a specified length.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b458a-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="b458a-106">Header file:</span></span>  <br/> |<span data-ttu-id="b458a-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b458a-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="b458a-108">相关的结构：</span><span class="sxs-lookup"><span data-stu-id="b458a-108">Related structure:</span></span>  <br/> |<span data-ttu-id="b458a-109">**DTBLGROUPBOX**</span><span class="sxs-lookup"><span data-stu-id="b458a-109">**DTBLGROUPBOX**</span></span> <br/> |
   
```cpp
SizedDtblGroupBox (n, u)
```

## <a name="parameters"></a><span data-ttu-id="b458a-110">参数</span><span class="sxs-lookup"><span data-stu-id="b458a-110">Parameters</span></span>

<span data-ttu-id="b458a-111">_n_</span><span class="sxs-lookup"><span data-stu-id="b458a-111">_n_</span></span>
  
> <span data-ttu-id="b458a-112">组框标签的长度。</span><span class="sxs-lookup"><span data-stu-id="b458a-112">Length of the group box's label.</span></span> 
    
<span data-ttu-id="b458a-113">_u_</span><span class="sxs-lookup"><span data-stu-id="b458a-113">_u_</span></span>
  
> <span data-ttu-id="b458a-114">新结构的的名称。</span><span class="sxs-lookup"><span data-stu-id="b458a-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="b458a-115">注解</span><span class="sxs-lookup"><span data-stu-id="b458a-115">Remarks</span></span>

<span data-ttu-id="b458a-116">**SizedDtblGroupBox**宏允许您定义一个组框控件时已知标签的长度。</span><span class="sxs-lookup"><span data-stu-id="b458a-116">The **SizedDtblGroupBox** macro lets you define a group box control when the length of the label is known.</span></span> <span data-ttu-id="b458a-117">使用下列成员来创建新的结构：</span><span class="sxs-lookup"><span data-stu-id="b458a-117">The new structure is created with the following members:</span></span> 
  
```cpp
DTBLGROUPBOX dtblgroupbox;
TCHAR lpszLabel[n];

```

<span data-ttu-id="b458a-118">若要将指针生成结构从**SizedDtblGroupBox**宏作为**DTBLGROUPBOX**结构指针，执行以下的强制转换：</span><span class="sxs-lookup"><span data-stu-id="b458a-118">To use a pointer to the resulting structure from the **SizedDtblGroupBox** macro as a **DTBLGROUPBOX** structure pointer, perform the following cast:</span></span> 
  
```cpp
lpDtblGroupBox = (LPDTBLGROUPBOX) &SizedDtblGroupBox;

```

## <a name="see-also"></a><span data-ttu-id="b458a-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b458a-119">See also</span></span>

- [<span data-ttu-id="b458a-120">DTBLGROUPBOX</span><span class="sxs-lookup"><span data-stu-id="b458a-120">DTBLGROUPBOX</span></span>](dtblgroupbox.md)
- [<span data-ttu-id="b458a-121">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="b458a-121">Macros Related to Structures</span></span>](macros-related-to-structures.md)

