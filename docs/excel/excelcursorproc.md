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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 07be8da4a07b988d5e848048a088859b58ea3a14
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773741"
---
# <a name="excelcursorproc"></a><span data-ttu-id="9fa9f-104">ExcelCursorProc</span><span class="sxs-lookup"><span data-stu-id="9fa9f-104">ExcelCursorProc</span></span>

 <span data-ttu-id="9fa9f-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9fa9f-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="9fa9f-106">通过 Microsoft Excel 窗口显示一个模式对话框时，光标通过 Excel 窗口是忙游标。</span><span class="sxs-lookup"><span data-stu-id="9fa9f-106">When a modal dialog box is displayed over the Microsoft Excel window, the cursor is a busy cursor over the Excel window.</span></span> <span data-ttu-id="9fa9f-107">此**WndProc**陷阱 WM_SETCURSOR 键入 Windows 消息和更改光标回正常的箭头。</span><span class="sxs-lookup"><span data-stu-id="9fa9f-107">This **WndProc** traps WM_SETCURSOR type Windows messages and changes the cursor back to a normal arrow.</span></span> 
  
```cs
LRESULT CALLBACK ExcelCursorProc(HWND hwnd, UINT wMsg, WPARAM wParam, LPARAM lParam);
```

## <a name="parameters"></a><span data-ttu-id="9fa9f-108">参数</span><span class="sxs-lookup"><span data-stu-id="9fa9f-108">Parameters</span></span>

 <span data-ttu-id="9fa9f-109">_hWndDlg_(**HWND**)</span><span class="sxs-lookup"><span data-stu-id="9fa9f-109">_hWndDlg_ (**HWND**)</span></span>
  
<span data-ttu-id="9fa9f-110">包含对话框的 HWND Windows 句柄。</span><span class="sxs-lookup"><span data-stu-id="9fa9f-110">Contains the HWND Windows handle of the dialog box.</span></span>
  
 <span data-ttu-id="9fa9f-111">_消息_(**UINT**)</span><span class="sxs-lookup"><span data-stu-id="9fa9f-111">_message_ (**UINT**)</span></span>
  
<span data-ttu-id="9fa9f-112">要回复的消息。</span><span class="sxs-lookup"><span data-stu-id="9fa9f-112">The message to respond to.</span></span>
  
 <span data-ttu-id="9fa9f-113">_wParam_(**WPARAM**)</span><span class="sxs-lookup"><span data-stu-id="9fa9f-113">_wParam_ (**WPARAM**)</span></span>
  
 <span data-ttu-id="9fa9f-114">_lParam_(**LPARAM**)</span><span class="sxs-lookup"><span data-stu-id="9fa9f-114">_lParam_ (**LPARAM**)</span></span>
  
<span data-ttu-id="9fa9f-115">通过 Windows 传递的参数。</span><span class="sxs-lookup"><span data-stu-id="9fa9f-115">Arguments passed by Windows.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="9fa9f-116">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="9fa9f-116">Property value/Return value</span></span>

<span data-ttu-id="9fa9f-117">Lresult 替换： 如果消息处理 0，否则返回的结果由默认**WndProc**。</span><span class="sxs-lookup"><span data-stu-id="9fa9f-117">LRESULT: 0 if the message was handled, otherwise the result returned by the default **WndProc**.</span></span>
  
### <a name="example"></a><span data-ttu-id="9fa9f-118">示例</span><span class="sxs-lookup"><span data-stu-id="9fa9f-118">Example</span></span>

<span data-ttu-id="9fa9f-119">请参阅`\SAMPLES\GENERIC\GENERIC.C`的此函数的源代码。</span><span class="sxs-lookup"><span data-stu-id="9fa9f-119">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="9fa9f-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9fa9f-120">See also</span></span>



[<span data-ttu-id="9fa9f-121">通用 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="9fa9f-121">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

