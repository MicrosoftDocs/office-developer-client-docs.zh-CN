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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8861c8f86eaab6defb270b673e0ee200446aedb3
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282822"
---
# <a name="sizeddtblcombobox"></a><span data-ttu-id="d9b45-103">SizedDtblComboBox</span><span class="sxs-lookup"><span data-stu-id="d9b45-103">SizedDtblComboBox</span></span>
 
<span data-ttu-id="d9b45-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d9b45-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d9b45-105">创建一个命名的结构, 其中包含用于描述组合框控件的[DTBLCOMBOBOX](dtblcombobox.md)结构, 以及可在关联的编辑控件中输入的最大字符数。</span><span class="sxs-lookup"><span data-stu-id="d9b45-105">Creates a named structure that includes a [DTBLCOMBOBOX](dtblcombobox.md) structure for describing a combo box control and the maximum number of characters that can be entered in the associated edit control.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d9b45-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="d9b45-106">Header file:</span></span>  <br/> |<span data-ttu-id="d9b45-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="d9b45-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="d9b45-108">相关结构:</span><span class="sxs-lookup"><span data-stu-id="d9b45-108">Related structure:</span></span>  <br/> |<span data-ttu-id="d9b45-109">**DTBLCOMBOBOX**</span><span class="sxs-lookup"><span data-stu-id="d9b45-109">**DTBLCOMBOBOX**</span></span> <br/> |
   
```cpp
SizedDtblComboBox (n, u)
```

## <a name="parameters"></a><span data-ttu-id="d9b45-110">参数</span><span class="sxs-lookup"><span data-stu-id="d9b45-110">Parameters</span></span>

<span data-ttu-id="d9b45-111">_n_</span><span class="sxs-lookup"><span data-stu-id="d9b45-111">_n_</span></span>
  
> <span data-ttu-id="d9b45-112">可在组合框的编辑控件中输入的字符数。</span><span class="sxs-lookup"><span data-stu-id="d9b45-112">Number of characters that can be entered in the combo box's edit control.</span></span> 
    
<span data-ttu-id="d9b45-113">_u_</span><span class="sxs-lookup"><span data-stu-id="d9b45-113">_u_</span></span>
  
> <span data-ttu-id="d9b45-114">新结构的名称。</span><span class="sxs-lookup"><span data-stu-id="d9b45-114">Name for the new structure.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d9b45-115">注解</span><span class="sxs-lookup"><span data-stu-id="d9b45-115">Remarks</span></span>

<span data-ttu-id="d9b45-116">**SizedDtblComboBox**宏允许您在已知启用的字符字符串的长度时定义组合框。</span><span class="sxs-lookup"><span data-stu-id="d9b45-116">The **SizedDtblComboBox** macro lets you define a combo box when the length of the enabled character string is known.</span></span> <span data-ttu-id="d9b45-117">新结构是使用以下成员创建的:</span><span class="sxs-lookup"><span data-stu-id="d9b45-117">The new structure is created with the following members:</span></span> 
  
```cpp
DTBLCOMBOBOX dtblcombobox;
TCHAR lpszCharsAllowed[n];

```

<span data-ttu-id="d9b45-118">若要将指向**SizedDtblComboBox**宏的结果结构的指针用作**DTBLCOMBOBOX**结构指针, 请执行以下转换:</span><span class="sxs-lookup"><span data-stu-id="d9b45-118">To use a pointer to the resulting structure from the **SizedDtblComboBox** macro as a **DTBLCOMBOBOX** structure pointer, perform the following cast:</span></span> 
  
```cpp
lpDtblComboBox = (LPDTBLCOMBOBOX) &SizedDtblComboBox;

```

## <a name="see-also"></a><span data-ttu-id="d9b45-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9b45-119">See also</span></span>

- [<span data-ttu-id="d9b45-120">DTBLCOMBOBOX</span><span class="sxs-lookup"><span data-stu-id="d9b45-120">DTBLCOMBOBOX</span></span>](dtblcombobox.md)
- [<span data-ttu-id="d9b45-121">与结构相关的宏</span><span class="sxs-lookup"><span data-stu-id="d9b45-121">Macros Related to Structures</span></span>](macros-related-to-structures.md)

