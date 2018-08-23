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
ms.openlocfilehash: 8d960207e05b33efe55886166ff1322f7f4eedce
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586198"
---
# <a name="sizeddtbllabel"></a><span data-ttu-id="2c6b1-103">SizedDtblLabel</span><span class="sxs-lookup"><span data-stu-id="2c6b1-103">SizedDtblLabel</span></span>

<span data-ttu-id="2c6b1-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="2c6b1-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="2c6b1-105">创建一个名为的结构包含用于描述 label 控件和指定长度的关联的标签[DTBLLABEL](dtbllabel.md)结构。</span><span class="sxs-lookup"><span data-stu-id="2c6b1-105">Creates a named structure that includes a [DTBLLABEL](dtbllabel.md) structure for describing a label control and the associated label of a specified length.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="2c6b1-106">头文件中指定：</span><span class="sxs-lookup"><span data-stu-id="2c6b1-106">Specified in header file:</span></span>  <br/> |<span data-ttu-id="2c6b1-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="2c6b1-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="2c6b1-108">相关的结构</span><span class="sxs-lookup"><span data-stu-id="2c6b1-108">Related structure</span></span>  <br/> |<span data-ttu-id="2c6b1-109">**DTBLLABEL**</span><span class="sxs-lookup"><span data-stu-id="2c6b1-109">**DTBLLABEL**</span></span> <br/> |
   
```cpp
SizedDtblLabel (n, u)
```

## <a name="parameters"></a><span data-ttu-id="2c6b1-110">参数</span><span class="sxs-lookup"><span data-stu-id="2c6b1-110">Parameters</span></span>

<span data-ttu-id="2c6b1-111">_n_</span><span class="sxs-lookup"><span data-stu-id="2c6b1-111">_n_</span></span>
  
> <span data-ttu-id="2c6b1-112">标签的长度。</span><span class="sxs-lookup"><span data-stu-id="2c6b1-112">Length of the label.</span></span> <span data-ttu-id="2c6b1-113">这包括结束 NULL 字符。</span><span class="sxs-lookup"><span data-stu-id="2c6b1-113">This includes the ending NULL character.</span></span> 
    
<span data-ttu-id="2c6b1-114">_u_</span><span class="sxs-lookup"><span data-stu-id="2c6b1-114">_u_</span></span>
  
> <span data-ttu-id="2c6b1-115">新结构的的名称。</span><span class="sxs-lookup"><span data-stu-id="2c6b1-115">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="2c6b1-116">注解</span><span class="sxs-lookup"><span data-stu-id="2c6b1-116">Remarks</span></span>

<span data-ttu-id="2c6b1-117">**SizedDtblLabel**宏允许您定义显示表标签时已知的标签中的字符数。</span><span class="sxs-lookup"><span data-stu-id="2c6b1-117">The **SizedDtblLabel** macro lets you define a display table label when the number of characters in the label is known.</span></span> <span data-ttu-id="2c6b1-118">使用下列成员来创建新的结构：</span><span class="sxs-lookup"><span data-stu-id="2c6b1-118">The new structure is created with the following members:</span></span> 
  
```cpp
DTBLLABEL dtbllabel;
TCHAR lpszLabelName[n];
```

<span data-ttu-id="2c6b1-119">若要将指针生成结构从**SizedDtblLabel**宏作为**DTBLLABEL**结构指针，执行以下的强制转换：</span><span class="sxs-lookup"><span data-stu-id="2c6b1-119">To use a pointer to the resulting structure from the **SizedDtblLabel** macro as a **DTBLLABEL** structure pointer, perform the following cast:</span></span> 
  
```cpp
lpDtblLabel = (LPDTBLLABEL) &SizedDtblLabel;
```

## <a name="see-also"></a><span data-ttu-id="2c6b1-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c6b1-120">See also</span></span>

- [<span data-ttu-id="2c6b1-121">DTBLLABEL</span><span class="sxs-lookup"><span data-stu-id="2c6b1-121">DTBLLABEL</span></span>](dtbllabel.md)
- [<span data-ttu-id="2c6b1-122">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="2c6b1-122">Macros Related to Structures</span></span>](macros-related-to-structures.md)

