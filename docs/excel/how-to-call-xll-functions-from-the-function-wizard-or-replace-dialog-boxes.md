---
title: 从函数向导或替换对话框调用 XLL 函数
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- xll 调用的函数 [excel 2007]，从替换对话框的替换对话框框 [Excel 2007]，调用 XLL 函数，函数向导 [Excel 2007] 中，调用 XLL 函数，XLL 函数 [Excel 2007]，从函数向导调用
localization_priority: Normal
ms.assetid: dc7e840e-6d1d-427b-97f9-7912e60ec954
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 7ebb33a5b98cebedfca7fb5923e62486bfd85696
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773763"
---
# <a name="call-xll-functions-from-the-function-wizard-or-replace-dialog-boxes"></a>从函数向导或替换对话框调用 XLL 函数

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
Microsoft Excel 通常 XLL 函数过程中调用普通重新计算工作簿或其一部分如果计算为宏的控制之下。 请记住此函数可能不驻留在单元格公式，但可能是一个命名的区域定义或条件格式表达式的一部分。
  
有两种情况下从 Excel 的对话框中，其中可以调用函数。 **粘贴函数参数**对话框，其中用户能够一次构造函数调用一个参数之一。 另一个是时禁止公式修改和重新输入由**替换**对话框中的 Excel。 为**粘贴函数参数**对话框中，您可能不希望您通常执行的函数。 这可能是因为它需要很长时间，以执行，并且您不希望慢的对话框中使用。 
  
**粘贴函数**对话框和**替换**对话框中安装了 Windows 类名称**bosa_sdm_XL**n，其中 n 是一个数字。 Windows 提供了一个 API 函数、 **GetClassName**，从 Windows 句柄，HWND 变量类型获取此名称。 它还提供另一个函数， **EnumWindows**，调用 （在您的 DLL) 提供的回调函数一次当前打开每个顶级窗口。
  
回调函数需要执行下面的步骤：
  
1. 检查此窗口的父对象是 Excel 的当前实例 （如果有多个实例正在运行）。
    
2. 类名称获得 windows 中传递的句柄。
    
3. 检查是否的窗体**bosa_sdm_XL**n 类名称。
    
4. 如果您需要区分两个对话框，请检查对话框标题是否包含某些识别的文本。 使用 Windows API 调用**GetWindowText**获得窗口标题。
    
下面的 c + + 代码演示类和回调要传递给 Windows 可执行这些步骤。 这是函数调用的调用测试专门针对任一关注对话框。 
  
> [!NOTE]
> 窗口标题的未来的 Excel 版本可能更改，并使此代码无效。 另请注意， **window_title_text**设置为**NULL**的效果的忽略回调搜索中的窗口标题。 
  
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

**粘贴函数**对话框中不具有一个标题，因此以下函数将传递的搜索标题字符串""，即为空字符串，给回调表示匹配条件为窗口中不应具有一个标题。 
  
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
  
[Developing Excel XLLs](developing-excel-xlls.md)

