---
title: 通过 "函数向导" 或 "替换" 对话框调用 XLL 函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- xll 函数 [excel 2007], 从 "替换" 对话框中调用 "替换" 对话框 [excel 2007], 调用 xll 函数, 函数向导 [excel 2007], 调用 xll 函数, XLL 函数 [excel 2007], 从函数向导调用
localization_priority: Normal
ms.assetid: dc7e840e-6d1d-427b-97f9-7912e60ec954
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 11189beed13e2ceb99ef04b7a2f966cb4171915c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304016"
---
# <a name="call-xll-functions-from-the-function-wizard-or-replace-dialog-boxes"></a>通过 "函数向导" 或 "替换" 对话框调用 XLL 函数

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
在工作簿的正常重新计算过程中, 如果计算受宏的控制, Microsoft Excel 通常会在正常的工作簿重新计算过程中调用 XLL 函数。 请记住, 函数可能不驻留在单元格公式中, 但可能是命名区域定义的一部分, 或者是条件格式表达式的一部分。
  
在以下两种情况下, 可以从 Excel 对话框中调用函数。 一个是 "**粘贴函数参数**" 对话框, 用户可以在其中一次构造一个参数的函数调用。 另一种情况是在修改公式时, Excel 在 "**替换**" 对话框中 reentered。 对于 "**粘贴函数参数**" 对话框, 您可能不希望您的函数正常执行。 这可能是因为执行时间较长, 而您不希望减慢对话框的使用。 
  
"**粘贴函数**" 对话框和 "**替换**" 对话框都具有 Windows 类名**bosa_sdm_XL**n, 其中 n 是一个数字。 windows 提供了 API 函数**GetClassName**, 该函数可从 Windows 句柄 (HWND 变量类型) 中获取此名称。 它还提供了另一个函数**EnumWindows**, 它为当前打开的每个顶级窗口调用一次提供的回调函数 (在 DLL 中)。
  
回调函数需要执行以下步骤:
  
1. 检查此窗口的父级是否为 Excel 的当前实例 (如果有多个实例正在运行)。
    
2. 从 Windows 传入的句柄中获取类名称。
    
3. 检查类名的格式是否为**bosa_sdm_XL**n。
    
4. 如果需要区分这两个对话框, 请检查对话框标题中是否包含一些标识文本。 窗口标题是使用 Windows API 调用**GetWindowText**获取的。
    
下面的 c + + 代码显示了要传递到执行这些步骤的 Windows 的类和回调。 这由针对相关对话框中的任一对话框调用 test 的函数调用。 
  
> [!NOTE]
> 将来的 Excel 版本的窗口标题可能会更改, 并使此代码无效。 另请注意, 将**window_title_text**设置为**NULL**会对回调搜索中忽略窗口标题产生的影响。 
  
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

"**粘贴函数**" 对话框没有标题, 因此下面的函数将 "" 的搜索标题字符串 (即空字符串) 传递给回调, 以指示匹配条件是窗口不应具有标题。 
  
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

## <a name="see-also"></a>另请参阅



[在 Excel 中访问 XLL 代码](accessing-xll-code-in-excel.md)
  
[从 DLL 或 XLL 调用 Excel](calling-into-excel-from-the-dll-or-xll.md)
  
[开发 Excel XLL](developing-excel-xlls.md)

