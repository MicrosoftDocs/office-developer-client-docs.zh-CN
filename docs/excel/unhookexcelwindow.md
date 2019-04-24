---
title: UnhookExcelWindow
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- UnhookExcelWindow
keywords:
- unhookexcelwindow 函数
localization_priority: Normal
ms.assetid: 6508cb69-0c7c-4d8c-a466-dd79eb13e316
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: aef2734aeb4d9cf5df33e3d012cef309e8a1eb6e
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310309"
---
# <a name="unhookexcelwindow"></a><span data-ttu-id="9925d-104">UnhookExcelWindow</span><span class="sxs-lookup"><span data-stu-id="9925d-104">UnhookExcelWindow</span></span>

 <span data-ttu-id="9925d-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9925d-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="9925d-106">删除以前由**HookExcelWindow**安装的**ExcelCursorProc** 。</span><span class="sxs-lookup"><span data-stu-id="9925d-106">Removes the **ExcelCursorProc** that was previously installed by **HookExcelWindow**.</span></span> <span data-ttu-id="9925d-107">这样做的目的是为了在 Microsoft Excel 主**WndProc**之前调用**ExcelCursorProc** 。</span><span class="sxs-lookup"><span data-stu-id="9925d-107">This would have been done so that **ExcelCursorProc** was called before the Microsoft Excel main **WndProc**.</span></span>
  
```cs
extern void FAR PASCAL UnhookExcelWindow(HANDLE hWndExcel);
```

## <a name="parameters"></a><span data-ttu-id="9925d-108">参数</span><span class="sxs-lookup"><span data-stu-id="9925d-108">Parameters</span></span>

 <span data-ttu-id="9925d-109">_hWndExcel_(**句柄**)</span><span class="sxs-lookup"><span data-stu-id="9925d-109">_hWndExcel_ (**HANDLE**)</span></span>
  
<span data-ttu-id="9925d-110">Excel 主窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="9925d-110">The Excel main Windows handle.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="9925d-111">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="9925d-111">Property value/Return value</span></span>

<span data-ttu-id="9925d-112">函数不返回值。</span><span class="sxs-lookup"><span data-stu-id="9925d-112">The function does not return a value.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="9925d-113">注解</span><span class="sxs-lookup"><span data-stu-id="9925d-113">Remarks</span></span>

<span data-ttu-id="9925d-114">此函数使用**SetWindowLong ()** 还原 Excel 的默认**WndProc** , 以还原**HookExcelWindow ()** 保存的地址。</span><span class="sxs-lookup"><span data-stu-id="9925d-114">This function restores the Excel default **WndProc** using **SetWindowLong()** to restore the address that was saved by **HookExcelWindow()**.</span></span>
  
### <a name="example"></a><span data-ttu-id="9925d-115">示例</span><span class="sxs-lookup"><span data-stu-id="9925d-115">Example</span></span>

<span data-ttu-id="9925d-116">有关`\SAMPLES\GENERIC\GENERIC.C`此函数的源代码, 请参阅。</span><span class="sxs-lookup"><span data-stu-id="9925d-116">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9925d-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9925d-117">See also</span></span>



[<span data-ttu-id="9925d-118">通用 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="9925d-118">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

