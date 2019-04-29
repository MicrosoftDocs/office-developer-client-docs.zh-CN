---
title: ExcelCursorProc
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- ExcelCursorProc
keywords:
- excelcursorproc 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 43759617-998d-4030-a17d-c4bbe35ffaf9
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: d3cc41487f0cae31e110249fe148f5370319a39a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33432490"
---
# <a name="excelcursorproc"></a><span data-ttu-id="2441d-104">ExcelCursorProc</span><span class="sxs-lookup"><span data-stu-id="2441d-104">ExcelCursorProc</span></span>

 <span data-ttu-id="2441d-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="2441d-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="2441d-106">当在 Microsoft Excel 窗口上显示模式对话框时, 光标在 Excel 窗口上是一个繁忙的光标。</span><span class="sxs-lookup"><span data-stu-id="2441d-106">When a modal dialog box is displayed over the Microsoft Excel window, the cursor is a busy cursor over the Excel window.</span></span> <span data-ttu-id="2441d-107">此**WndProc**陷阱 WM_SETCURSOR 键入 Windows 消息, 并将光标更改回正常箭头。</span><span class="sxs-lookup"><span data-stu-id="2441d-107">This **WndProc** traps WM_SETCURSOR type Windows messages and changes the cursor back to a normal arrow.</span></span> 
  
```cs
LRESULT CALLBACK ExcelCursorProc(HWND hwnd, UINT wMsg, WPARAM wParam, LPARAM lParam);
```

## <a name="parameters"></a><span data-ttu-id="2441d-108">参数</span><span class="sxs-lookup"><span data-stu-id="2441d-108">Parameters</span></span>

 <span data-ttu-id="2441d-109">_hWndDlg_(**HWND**)</span><span class="sxs-lookup"><span data-stu-id="2441d-109">_hWndDlg_ (**HWND**)</span></span>
  
<span data-ttu-id="2441d-110">包含对话框的 HWND 窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="2441d-110">Contains the HWND Windows handle of the dialog box.</span></span>
  
 <span data-ttu-id="2441d-111">_邮件_(**UINT**)</span><span class="sxs-lookup"><span data-stu-id="2441d-111">_message_ (**UINT**)</span></span>
  
<span data-ttu-id="2441d-112">要响应的邮件。</span><span class="sxs-lookup"><span data-stu-id="2441d-112">The message to respond to.</span></span>
  
 <span data-ttu-id="2441d-113">_wParam_(**WPARAM**)</span><span class="sxs-lookup"><span data-stu-id="2441d-113">_wParam_ (**WPARAM**)</span></span>
  
 <span data-ttu-id="2441d-114">_lParam_(**LPARAM**)</span><span class="sxs-lookup"><span data-stu-id="2441d-114">_lParam_ (**LPARAM**)</span></span>
  
<span data-ttu-id="2441d-115">由 Windows 传递的参数。</span><span class="sxs-lookup"><span data-stu-id="2441d-115">Arguments passed by Windows.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="2441d-116">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="2441d-116">Property value/Return value</span></span>

<span data-ttu-id="2441d-117">LRESULT: 0 如果已处理邮件, 否则由默认**WndProc**返回的结果。</span><span class="sxs-lookup"><span data-stu-id="2441d-117">LRESULT: 0 if the message was handled, otherwise the result returned by the default **WndProc**.</span></span>
  
### <a name="example"></a><span data-ttu-id="2441d-118">示例</span><span class="sxs-lookup"><span data-stu-id="2441d-118">Example</span></span>

<span data-ttu-id="2441d-119">有关`\SAMPLES\GENERIC\GENERIC.C`此函数的源代码, 请参阅。</span><span class="sxs-lookup"><span data-stu-id="2441d-119">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2441d-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2441d-120">See also</span></span>



[<span data-ttu-id="2441d-121">通用 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="2441d-121">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

