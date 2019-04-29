---
title: HookExcelWindow
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- HookExcelWindow
keywords:
- hookexcelwindow 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 13f0ae5e-9951-4e89-a245-7cf68c6f6724
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 4103bf3a95388d20efeb74fcd736aeb5520d0845
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33413505"
---
# <a name="hookexcelwindow"></a><span data-ttu-id="cc75a-104">HookExcelWindow</span><span class="sxs-lookup"><span data-stu-id="cc75a-104">HookExcelWindow</span></span>

 <span data-ttu-id="cc75a-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="cc75a-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="cc75a-106">安装**ExcelCursorProc** , 以便在 Microsoft Excel 主**WndProc**之前调用它。</span><span class="sxs-lookup"><span data-stu-id="cc75a-106">Installs **ExcelCursorProc** so that it is called before the Microsoft Excel main **WndProc**.</span></span>
  
```cs
extern void FAR PASCAL HookExcelWindow(HANDLE hWndExcel);
```

## <a name="parameters"></a><span data-ttu-id="cc75a-107">参数</span><span class="sxs-lookup"><span data-stu-id="cc75a-107">Parameters</span></span>

 <span data-ttu-id="cc75a-108">_hWndExcel_(**句柄**)</span><span class="sxs-lookup"><span data-stu-id="cc75a-108">_hWndExcel_ (**HANDLE**)</span></span>
  
<span data-ttu-id="cc75a-109">Excel 主窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="cc75a-109">The Excel main Windows handle.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="cc75a-110">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="cc75a-110">Property value/Return value</span></span>

<span data-ttu-id="cc75a-111">函数不返回值。</span><span class="sxs-lookup"><span data-stu-id="cc75a-111">The function does not return a value.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="cc75a-112">说明</span><span class="sxs-lookup"><span data-stu-id="cc75a-112">Remarks</span></span>

<span data-ttu-id="cc75a-113">函数通过使用**GetWindowLong ()** 获取 Excel **WndProc**的地址。</span><span class="sxs-lookup"><span data-stu-id="cc75a-113">The function obtains the address of the Excel **WndProc** through the use of **GetWindowLong()**.</span></span> <span data-ttu-id="cc75a-114">它将此值存储在全局中, 可用于调用默认**WndProc** , 还可以将其还原。</span><span class="sxs-lookup"><span data-stu-id="cc75a-114">It stores this value in a global that can be used to call the default **WndProc** and also to restore it.</span></span> <span data-ttu-id="cc75a-115">最后, 它使用**SetWindowLong ()** 将此地址替换为**ExcelCursorProc**的地址。</span><span class="sxs-lookup"><span data-stu-id="cc75a-115">Finally, it replaces this address with the address of **ExcelCursorProc** using **SetWindowLong()**.</span></span>
  
### <a name="example"></a><span data-ttu-id="cc75a-116">示例</span><span class="sxs-lookup"><span data-stu-id="cc75a-116">Example</span></span>

<span data-ttu-id="cc75a-117">有关`\SAMPLES\GENERIC\GENERIC.C`此函数的源代码, 请参阅。</span><span class="sxs-lookup"><span data-stu-id="cc75a-117">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="cc75a-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cc75a-118">See also</span></span>



[<span data-ttu-id="cc75a-119">通用 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="cc75a-119">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

