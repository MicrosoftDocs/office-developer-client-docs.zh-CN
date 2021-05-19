---
title: 从函数向导或替换对话框调用 XLL 函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- xll functions [excel 2007]， calling from replace dialog box，Replace dialog box [Excel 2007]， calling XLL functions，Function Wizard [Excel 2007]， calling XLL functions，XLL functions [Excel 2007]， calling from Function Wizard
localization_priority: Normal
ms.assetid: dc7e840e-6d1d-427b-97f9-7912e60ec954
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 11189beed13e2ceb99ef04b7a2f966cb4171915c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410747"
---
# <a name="call-xll-functions-from-the-function-wizard-or-replace-dialog-boxes"></a><span data-ttu-id="f857a-104">从函数向导或替换对话框调用 XLL 函数</span><span class="sxs-lookup"><span data-stu-id="f857a-104">Call XLL Functions from the Function Wizard or Replace Dialog Boxes</span></span>

 <span data-ttu-id="f857a-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="f857a-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="f857a-106">Microsoft Excel 通常在工作簿的正常重新计算过程中调用 XLL 函数，如果计算在宏的控制之下，则调用它的一部分。</span><span class="sxs-lookup"><span data-stu-id="f857a-106">Microsoft Excel usually calls XLL functions during the normal recalculation of the workbook, or a part of it if the calculation is under the control of a macro.</span></span> <span data-ttu-id="f857a-107">请记住，该函数可能未驻留在单元格公式中，但可能是命名区域定义或条件格式表达式的一部分。</span><span class="sxs-lookup"><span data-stu-id="f857a-107">Remember that the function might not reside in a cell formula but might be part of a named range definition, or a conditional formatting expression.</span></span>
  
<span data-ttu-id="f857a-108">有两种从 Excel 对话框中调用函数的情况。</span><span class="sxs-lookup"><span data-stu-id="f857a-108">There are two circumstances where a function can be called from an Excel dialog box.</span></span> <span data-ttu-id="f857a-109">一种 **是"粘贴函数参数** "对话框，用户可以在对话框中构造一个函数，一次调用一个参数。</span><span class="sxs-lookup"><span data-stu-id="f857a-109">One is the **Paste Function Arguments** dialog box, where users are able to construct a function call one argument at a time.</span></span> <span data-ttu-id="f857a-110">另一种是 Excel 在"替换"对话框中修改和重新 **输入公式。**</span><span class="sxs-lookup"><span data-stu-id="f857a-110">The other is when formulas are being modified and reentered by Excel in the **Replace** dialog box.</span></span> <span data-ttu-id="f857a-111">对于 **"粘贴函数参数** "对话框，您可能不希望函数正常执行。</span><span class="sxs-lookup"><span data-stu-id="f857a-111">For the **Paste Function Arguments** dialog box, you might not want your function to execute normally.</span></span> <span data-ttu-id="f857a-112">这可能是因为执行需要很长时间，并且您不想减慢对话框的使用速度。</span><span class="sxs-lookup"><span data-stu-id="f857a-112">This may be because it takes a long time to execute and you do not want to slow down the use of the dialog box.</span></span> 
  
<span data-ttu-id="f857a-113">" **粘贴函数"** 对话框和" **替换** "对话框的 Windows 类名称都bosa_sdm_XL **n，** 其中 n 是数字。</span><span class="sxs-lookup"><span data-stu-id="f857a-113">Both the **Paste Function** dialog box and the **Replace** dialog box have the Windows class name **bosa_sdm_XL** n, where n is a number.</span></span> <span data-ttu-id="f857a-114">Windows 提供了 API 函数 **GetClassName，** 该函数从 Windows 句柄（HWND 变量类型）获取此名称。</span><span class="sxs-lookup"><span data-stu-id="f857a-114">Windows provides an API function, **GetClassName**, that obtains this name from a Windows handle, an HWND variable type.</span></span> <span data-ttu-id="f857a-115">它还提供另一个函数 **EnumWindows，** 它针对当前打开的顶级窗口 (DLL) 一次提供的回调函数。</span><span class="sxs-lookup"><span data-stu-id="f857a-115">It also provides another function, **EnumWindows**, that calls a supplied callback function (within your DLL) once for every top-level window that is currently open.</span></span>
  
<span data-ttu-id="f857a-116">回调函数只需执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="f857a-116">The callback function needs to perform only the following steps:</span></span>
  
1. <span data-ttu-id="f857a-117">检查此窗口的父窗口是否为 Excel (，以防有多个实例在运行) 。</span><span class="sxs-lookup"><span data-stu-id="f857a-117">Check if the parent of this window is the current instance of Excel (in case there are multiple instances running).</span></span>
    
2. <span data-ttu-id="f857a-118">从 Windows 传入的句柄获取类名称。</span><span class="sxs-lookup"><span data-stu-id="f857a-118">Get the class name from the handle passed in by Windows.</span></span>
    
3. <span data-ttu-id="f857a-119">检查类名称是否与 n **bosa_sdm_XL。**</span><span class="sxs-lookup"><span data-stu-id="f857a-119">Check if the class name is of the form **bosa_sdm_XL** n.</span></span>
    
4. <span data-ttu-id="f857a-120">如果需要区分这两个对话框，请检查对话框标题是否包含一些标识文本。</span><span class="sxs-lookup"><span data-stu-id="f857a-120">If you need to distinguish between the two dialog boxes, check if the dialog box title contains some identifying text.</span></span> <span data-ttu-id="f857a-121">窗口标题是使用 Windows API 调用 **GetWindowText 获取的**。</span><span class="sxs-lookup"><span data-stu-id="f857a-121">The window title is obtained using the Windows API call **GetWindowText**.</span></span>
    
<span data-ttu-id="f857a-122">以下 C++ 代码显示要传递给执行这些步骤的 Windows 的类和回调。</span><span class="sxs-lookup"><span data-stu-id="f857a-122">The following C++ code shows a class and callback to be passed to Windows that performs these steps.</span></span> <span data-ttu-id="f857a-123">这由专门为任一相关对话框调用 test 的函数调用。</span><span class="sxs-lookup"><span data-stu-id="f857a-123">This is called by the functions that call test specifically for either of the dialog boxes concerned.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="f857a-124">未来 Excel 版本的窗口标题可能会更改此代码，并会使此代码无效。</span><span class="sxs-lookup"><span data-stu-id="f857a-124">Window titles of future Excel versions might change and invalidate this code.</span></span> <span data-ttu-id="f857a-125">另请注意 **，window_title_text** **NULL 会** 忽略回调搜索中的窗口标题。</span><span class="sxs-lookup"><span data-stu-id="f857a-125">Note also that setting **window_title_text** to **NULL** has the effect of ignoring window title in the callback search.</span></span> 
  
```cs
#define CLASS_NAME_BUFFSIZE  50
#define WINDOW_TEXT_BUFFSIZE  50
// Data structure used as input to xldlg_enum_proc(), called by
// called_from_paste_fn_dlg(), called_from_replace_dlg(), and
// called_from_Excel_dlg(). These functions tell the caller whether
// the current worksheet function was called from one or either of
// these dialog boxes.
typedef struct
{
  bool is_dlg;
  short low_hwnd;
  char *window_title_text; // set to NULL if don't care
}
  xldlg_enum_struct;
// The callback function called by Windows for every top-level window.
BOOL CALLBACK xldlg_enum_proc(HWND hwnd, xldlg_enum_struct *p_enum)
{
// Check if the parent window is Excel.
// Note: Because of the change from MDI (Excel 2010)
// to SDI (Excel 2013), comment out this step in Excel 2013.
  if(LOWORD((DWORD)GetParent(hwnd)) != p_enum->low_hwnd)
    return TRUE; // keep iterating
  char class_name[CLASS_NAME_BUFFSIZE + 1];
//  Ensure that class_name is always null terminated for safety.
  class_name[CLASS_NAME_BUFFSIZE] = 0;
  GetClassName(hwnd, class_name, CLASS_NAME_BUFFSIZE);
//  Do a case-insensitve comparison for the Excel dialog window
//  class name with the Excel version number truncated.
  size_t len; // The length of the window's title text
  if(_strnicmp(class_name, "bosa_sdm_xl", 11) == 0)
  {
// Check if a searching for a specific title string
    if(p_enum->window_title_text) 
    {
// Get the window's title and see if it matches the given text.
      char buffer[WINDOW_TEXT_BUFFSIZE + 1];
      buffer[WINDOW_TEXT_BUFFSIZE] = 0;
      len = GetWindowText(hwnd, buffer, WINDOW_TEXT_BUFFSIZE);
      if(len == 0) // No title
      {
        if(p_enum->window_title_text[0] != 0)
          return TRUE; // No match, so keep iterating
      }
// Window has a title so do a case-insensitive comparison of the
// title and the search text, if provided.
      else if(p_enum->window_title_text[0] != 0
      && _stricmp(buffer, p_enum->window_title_text) != 0)
        return TRUE; // Keep iterating
    }
    p_enum->is_dlg = true;
    return FALSE; // Tells Windows to stop iterating.
  }
  return TRUE; // Tells Windows to continue iterating.
}
```

<span data-ttu-id="f857a-126">" **粘贴** 函数"对话框没有标题，因此以下函数将搜索标题字符串""（即空字符串）传递给回调，以指示匹配条件是窗口不应具有标题。</span><span class="sxs-lookup"><span data-stu-id="f857a-126">The **Paste Function** dialog box does not have a title, so the following function passes a search title string of "", that is, an empty string, to the callback to indicate that the match condition is that the window should not have a title.</span></span> 
  
```cs
bool called_from_paste_fn_dlg(void)
{
    XLOPER xHwnd;
// Calls Excel4, which only returns the low part of the Excel
// main window handle. This is OK for the search however.
    if(Excel4(xlGetHwnd, &xHwnd, 0))
        return false; // Couldn't get it, so assume not
// Search for bosa_sdm_xl* dialog box with no title string.
    xldlg_enum_struct es = {FALSE, xHwnd.val.w, ""};
    EnumWindows((WNDENUMPROC)xldlg_enum_proc, (LPARAM)&es);
    return es.is_dlg;
}
```

## <a name="see-also"></a><span data-ttu-id="f857a-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f857a-127">See also</span></span>



[<span data-ttu-id="f857a-128">在 Excel 中访问 XLL 代码</span><span class="sxs-lookup"><span data-stu-id="f857a-128">Accessing XLL Code in Excel</span></span>](accessing-xll-code-in-excel.md)
  
[<span data-ttu-id="f857a-129">从 DLL 或 XLL 调用 Excel</span><span class="sxs-lookup"><span data-stu-id="f857a-129">Calling into Excel from the DLL or XLL</span></span>](calling-into-excel-from-the-dll-or-xll.md)
  
[<span data-ttu-id="f857a-130">开发 Excel XLL</span><span class="sxs-lookup"><span data-stu-id="f857a-130">Developing Excel XLLs</span></span>](developing-excel-xlls.md)

