---
title: SizedDtblComboBox
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SizedDtblComboBox
api_type:
- COM
ms.assetid: 1e5ea9f2-1029-4584-845a-890d3e956036
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: fea2b496a34d7aa7f9469158fae14daf6a770608
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778801"
---
# <a name="sizeddtblcombobox"></a><span data-ttu-id="f5e1b-103">SizedDtblComboBox</span><span class="sxs-lookup"><span data-stu-id="f5e1b-103">SizedDtblComboBox</span></span>
 
<span data-ttu-id="f5e1b-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f5e1b-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f5e1b-105">创建一个名为的结构包含用于描述组合框控件和最大可以关联的编辑控件中输入的字符数[DTBLCOMBOBOX](dtblcombobox.md)结构。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-105">Creates a named structure that includes a [DTBLCOMBOBOX](dtblcombobox.md) structure for describing a combo box control and the maximum number of characters that can be entered in the associated edit control.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="f5e1b-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="f5e1b-106">Header file:</span></span>  <br/> |<span data-ttu-id="f5e1b-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="f5e1b-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="f5e1b-108">相关的结构：</span><span class="sxs-lookup"><span data-stu-id="f5e1b-108">Related structure:</span></span>  <br/> |<span data-ttu-id="f5e1b-109">**DTBLCOMBOBOX**</span><span class="sxs-lookup"><span data-stu-id="f5e1b-109">**DTBLCOMBOBOX**</span></span> <br/> |
   
```cpp
SizedDtblComboBox (n, u)
```

## <a name="parameters"></a><span data-ttu-id="f5e1b-110">参数</span><span class="sxs-lookup"><span data-stu-id="f5e1b-110">Parameters</span></span>

<span data-ttu-id="f5e1b-111">_n_</span><span class="sxs-lookup"><span data-stu-id="f5e1b-111">_n_</span></span>
  
> <span data-ttu-id="f5e1b-112">可以在组合框中输入的字符数编辑控件。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-112">Number of characters that can be entered in the combo box's edit control.</span></span> 
    
<span data-ttu-id="f5e1b-113">_u_</span><span class="sxs-lookup"><span data-stu-id="f5e1b-113">_u_</span></span>
  
> <span data-ttu-id="f5e1b-114">新结构的的名称。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f5e1b-115">备注</span><span class="sxs-lookup"><span data-stu-id="f5e1b-115">Remarks</span></span>

<span data-ttu-id="f5e1b-116">**SizedDtblComboBox**宏允许您定义组合框时已知启用的字符串的长度。</span><span class="sxs-lookup"><span data-stu-id="f5e1b-116">The **SizedDtblComboBox** macro lets you define a combo box when the length of the enabled character string is known.</span></span> <span data-ttu-id="f5e1b-117">使用下列成员来创建新的结构：</span><span class="sxs-lookup"><span data-stu-id="f5e1b-117">The new structure is created with the following members:</span></span> 
  
```cpp
DTBLCOMBOBOX dtblcombobox;
TCHAR lpszCharsAllowed[n];

```

<span data-ttu-id="f5e1b-118">若要将指针生成结构从**SizedDtblComboBox**宏作为**DTBLCOMBOBOX**结构指针，执行以下的强制转换：</span><span class="sxs-lookup"><span data-stu-id="f5e1b-118">To use a pointer to the resulting structure from the **SizedDtblComboBox** macro as a **DTBLCOMBOBOX** structure pointer, perform the following cast:</span></span> 
  
```cpp
lpDtblComboBox = (LPDTBLCOMBOBOX) &SizedDtblComboBox;

```

## <a name="see-also"></a><span data-ttu-id="f5e1b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f5e1b-119">See also</span></span>

- [<span data-ttu-id="f5e1b-120">DTBLCOMBOBOX</span><span class="sxs-lookup"><span data-stu-id="f5e1b-120">DTBLCOMBOBOX</span></span>](dtblcombobox.md)
- [<span data-ttu-id="f5e1b-121">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="f5e1b-121">Macros Related to Structures</span></span>](macros-related-to-structures.md)

