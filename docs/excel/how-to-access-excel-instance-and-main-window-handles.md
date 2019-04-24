---
title: 访问 Excel 实例和主窗口句柄
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 访问 excel 句柄、句柄 [excel 2007]、访问、excel 实例、访问、窗口句柄 [excel 2007]、访问
localization_priority: Normal
ms.assetid: 21e1dbdc-06fa-4514-9437-c4cffc3b4621
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 4b71ccd428e60c9ba2e59fea0e56eb2fc61390db
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310757"
---
# <a name="access-excel-instance-and-main-window-handles"></a><span data-ttu-id="d26db-104">访问 Excel 实例和主窗口句柄</span><span class="sxs-lookup"><span data-stu-id="d26db-104">Access Excel Instance and Main Window Handles</span></span>

 <span data-ttu-id="d26db-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d26db-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="d26db-106">若要在 Windows 环境中进行编程, 有时必须知道 Microsoft Excel 实例句柄或主窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="d26db-106">To program in the Windows environment, sometimes you must know the Microsoft Excel instance handle or main window handle.</span></span> <span data-ttu-id="d26db-107">例如, 在创建和显示自定义 Windows 对话框时, 这些句柄很有用。</span><span class="sxs-lookup"><span data-stu-id="d26db-107">For example, these handles are useful when you are creating and displaying custom Windows dialog boxes.</span></span>
  
<span data-ttu-id="d26db-108">有两种仅 XLL C API 函数, 它们分别提供对这些句柄的访问: [xlGetInst](xlgetinst.md)函数和[xlGetHwnd](xlgethwnd.md)函数。</span><span class="sxs-lookup"><span data-stu-id="d26db-108">There are two XLL-only C API functions that provide access to these handles: the [xlGetInst](xlgetinst.md) function and the [xlGetHwnd](xlgethwnd.md) function respectively.</span></span> <span data-ttu-id="d26db-109">在 Win32 中, 所有句柄均为32位整数。</span><span class="sxs-lookup"><span data-stu-id="d26db-109">In Win32, all handles are 32-bit integers.</span></span> <span data-ttu-id="d26db-110">但是, 在设计**XLOPER**时, Windows 是16位系统。</span><span class="sxs-lookup"><span data-stu-id="d26db-110">However, when the **XLOPER** was designed, Windows was a 16-bit system.</span></span> <span data-ttu-id="d26db-111">因此, 仅允许16位句柄的结构。</span><span class="sxs-lookup"><span data-stu-id="d26db-111">Therefore, the structure only allowed for 16-bit handles.</span></span> <span data-ttu-id="d26db-112">在 Win32 中, 当使用**Excel4**或**Excel4v**调用时, **xlGetInst**函数和**xlGetHwnd**函数仅返回完整的32位句柄的低部分。</span><span class="sxs-lookup"><span data-stu-id="d26db-112">In Win32, when called with **Excel4** or **Excel4v**, the **xlGetInst** function and the **xlGetHwnd** function return only the low part of the full 32-bit handle.</span></span> 
  
<span data-ttu-id="d26db-113">在 Excel 2007 及更高版本中, 当使用[Excel12](excel4-excel12.md)或[Excel12v](excel4v-excel12v.md)调用这些函数时, 返回的**XLOPER12**将包含完整的32位句柄。</span><span class="sxs-lookup"><span data-stu-id="d26db-113">In Excel 2007 and later versions, when these functions are called with [Excel12](excel4-excel12.md) or [Excel12v](excel4v-excel12v.md), the returned **XLOPER12** contains the full 32-bit handle.</span></span> 
  
<span data-ttu-id="d26db-114">在 Excel 的任何版本中, 获取完整实例句柄很简单, 因为它会传递给 Windows 回调**DllMain**(在加载 DLL 时调用)。</span><span class="sxs-lookup"><span data-stu-id="d26db-114">Obtaining the full instance handle is simple in any version of Excel, as it is passed to the Windows callback **DllMain**, which is called when the DLL is loaded.</span></span> <span data-ttu-id="d26db-115">如果在全局变量中记录此实例句柄, 则永远不需要调用**xlGetInst**函数。</span><span class="sxs-lookup"><span data-stu-id="d26db-115">If you record this instance handle in a global variable, you never need to call the **xlGetInst** function.</span></span> 
  
## <a name="obtaining-the-main-excel-handle-in-excel-2003-and-earlier"></a><span data-ttu-id="d26db-116">在 excel 2003 和早期版本中获取 excel 的主要句柄</span><span class="sxs-lookup"><span data-stu-id="d26db-116">Obtaining the Main Excel Handle in Excel 2003 and Earlier</span></span>

<span data-ttu-id="d26db-117">若要获取 excel 2003 和更早版本的32位版本中的 excel 主句柄, 必须首先调用**xlGetHwnd**函数来获取实际句柄的低位字。</span><span class="sxs-lookup"><span data-stu-id="d26db-117">To obtain the main Excel handle in Excel 2003 and earlier 32-bit versions, you must first call the **xlGetHwnd** function to obtain the low word of the actual handle.</span></span> <span data-ttu-id="d26db-118">然后, 必须循环访问顶级窗口列表, 以搜索与返回的低词匹配的匹配项。</span><span class="sxs-lookup"><span data-stu-id="d26db-118">Then, you must iterate the list of top-level windows to search for a match with the returned low word.</span></span> <span data-ttu-id="d26db-119">下面的代码演示了该技术。</span><span class="sxs-lookup"><span data-stu-id="d26db-119">The following code illustrates the technique.</span></span> 
  
```cs
typedef struct _EnumStruct
{
  HWND hwnd;  // Return value for Excel main hWnd.
  unsigned short wLoword; //Contains LowWord of the Excel main hWnd
} EnumStruct;
#define CLASS_NAME_BUFFER  50
BOOL CALLBACK EnumProc(HWND hwnd, EnumStruct * pEnum)
{
  // First check the class of the window. Must be "XLMAIN".
  char rgsz[CLASS_NAME_BUFFER];
  GetClassName(hwnd, rgsz, CLASS_NAME_BUFFER);
  if (!lstrcmpi(rgsz, "XLMAIN"))
  {
    // If that hits, check the loword of the window handle.
    if (LOWORD((DWORD) hwnd) == pEnum->wLoword)
    {
      // We have a match, return Excel main hWnd.
      pEnum->hwnd = hwnd;
      return FALSE;
    }
  }
  // No match - continue the enumeration.
  return TRUE;
}
BOOL GetHwnd(HWND * pHwnd)
{
  XLOPER x;
  //
  // xlGetHwnd only returns the LoWord of Excel hWnd
  // so all the windows have to be enumerated to see
  // which match the LoWord returned by xlGetHwnd.
  //
  if (Excel4(xlGetHwnd, &x, 0) == xlretSuccess)
  {
    EnumStruct enm;
    enm.hwnd = NULL;
    enm.wLoword = x.val.w;
    EnumWindows((WNDENUMPROC) EnumProc, (LPARAM) &enm);
    if (enm.hwnd != NULL)
    {
      *pHwnd = enm.hwnd;
      return TRUE;
    }
  }
  return FALSE;
}
```

## <a name="see-also"></a><span data-ttu-id="d26db-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d26db-120">See also</span></span>



[<span data-ttu-id="d26db-121">在 DLL 或 XLL 内显示对话框</span><span class="sxs-lookup"><span data-stu-id="d26db-121">Displaying Dialog Boxes from Within a DLL or XLL</span></span>](displaying-dialog-boxes-from-within-a-dll-or-xll.md)
  
[<span data-ttu-id="d26db-122">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="d26db-122">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)
  
[<span data-ttu-id="d26db-123">开发 Excel XLL</span><span class="sxs-lookup"><span data-stu-id="d26db-123">Developing Excel XLLs</span></span>](developing-excel-xlls.md)

