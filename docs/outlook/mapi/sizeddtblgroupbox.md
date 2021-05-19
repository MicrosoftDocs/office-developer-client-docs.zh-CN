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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419315"
---
# <a name="sizeddtblgroupbox"></a><span data-ttu-id="8574d-103">SizedDtblGroupBox</span><span class="sxs-lookup"><span data-stu-id="8574d-103">SizedDtblGroupBox</span></span>

<span data-ttu-id="8574d-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8574d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8574d-105">创建一个命名结构，其中包含用于描述分组框控件和指定长度的标签的 [DTBLGROUPBOX](dtblgroupbox.md) 结构。</span><span class="sxs-lookup"><span data-stu-id="8574d-105">Creates a named structure that includes a [DTBLGROUPBOX](dtblgroupbox.md) structure for describing a group box control and a label of a specified length.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8574d-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="8574d-106">Header file:</span></span>  <br/> |<span data-ttu-id="8574d-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8574d-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="8574d-108">相关结构：</span><span class="sxs-lookup"><span data-stu-id="8574d-108">Related structure:</span></span>  <br/> |<span data-ttu-id="8574d-109">**DTBLGROUPBOX**</span><span class="sxs-lookup"><span data-stu-id="8574d-109">**DTBLGROUPBOX**</span></span> <br/> |
   
```cpp
SizedDtblGroupBox (n, u)
```

## <a name="parameters"></a><span data-ttu-id="8574d-110">参数</span><span class="sxs-lookup"><span data-stu-id="8574d-110">Parameters</span></span>

<span data-ttu-id="8574d-111">_n_</span><span class="sxs-lookup"><span data-stu-id="8574d-111">_n_</span></span>
  
> <span data-ttu-id="8574d-112">分组框标签的长度。</span><span class="sxs-lookup"><span data-stu-id="8574d-112">Length of the group box's label.</span></span> 
    
<span data-ttu-id="8574d-113">_u_</span><span class="sxs-lookup"><span data-stu-id="8574d-113">_u_</span></span>
  
> <span data-ttu-id="8574d-114">新结构的名称。</span><span class="sxs-lookup"><span data-stu-id="8574d-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="8574d-115">备注</span><span class="sxs-lookup"><span data-stu-id="8574d-115">Remarks</span></span>

<span data-ttu-id="8574d-116">**SizedDtblGroupBox** 宏允许你在标签长度已知时定义分组框控件。</span><span class="sxs-lookup"><span data-stu-id="8574d-116">The **SizedDtblGroupBox** macro lets you define a group box control when the length of the label is known.</span></span> <span data-ttu-id="8574d-117">新结构由以下成员创建：</span><span class="sxs-lookup"><span data-stu-id="8574d-117">The new structure is created with the following members:</span></span> 
  
```cpp
DTBLGROUPBOX dtblgroupbox;
TCHAR lpszLabel[n];

```

<span data-ttu-id="8574d-118">若要将指向 **SizedDtblGroupBox** 宏生成的结构的指针用作 **DTBLGROUPBOX** 结构指针，请执行以下转换：</span><span class="sxs-lookup"><span data-stu-id="8574d-118">To use a pointer to the resulting structure from the **SizedDtblGroupBox** macro as a **DTBLGROUPBOX** structure pointer, perform the following cast:</span></span> 
  
```cpp
lpDtblGroupBox = (LPDTBLGROUPBOX) &SizedDtblGroupBox;

```

## <a name="see-also"></a><span data-ttu-id="8574d-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8574d-119">See also</span></span>

- [<span data-ttu-id="8574d-120">DTBLGROUPBOX</span><span class="sxs-lookup"><span data-stu-id="8574d-120">DTBLGROUPBOX</span></span>](dtblgroupbox.md)
- [<span data-ttu-id="8574d-121">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="8574d-121">Macros Related to Structures</span></span>](macros-related-to-structures.md)

