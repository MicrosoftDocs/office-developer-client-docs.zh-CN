---
title: 访问Excel实例和主窗口句柄
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
keywords:
- 访问 excel handles，handles [Excel 2007]， accessing，Excel instances， accessing，window handles [Excel 2007]， accessing
localization_priority: Normal
ms.assetid: 21e1dbdc-06fa-4514-9437-c4cffc3b4621
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 4b71ccd428e60c9ba2e59fea0e56eb2fc61390db
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310757"
---
# <a name="access-excel-instance-and-main-window-handles"></a><span data-ttu-id="04e06-104">访问Excel实例和主窗口句柄</span><span class="sxs-lookup"><span data-stu-id="04e06-104">Access Excel Instance and Main Window Handles</span></span>

 <span data-ttu-id="04e06-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="04e06-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="04e06-106">若要在Windows环境中进行编程，有时必须知道Microsoft Excel句柄或主窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="04e06-106">To program in the Windows environment, sometimes you must know the Microsoft Excel instance handle or main window handle.</span></span> <span data-ttu-id="04e06-107">例如，在创建和显示自定义对话框时，这些句柄Windows很有用。</span><span class="sxs-lookup"><span data-stu-id="04e06-107">For example, these handles are useful when you are creating and displaying custom Windows dialog boxes.</span></span>
  
<span data-ttu-id="04e06-108">有两个仅 XLL C API 函数提供对这些句柄的访问权限： [分别为 xlGetInst](xlgetinst.md) 函数和 [xlGetHwnd](xlgethwnd.md) 函数。</span><span class="sxs-lookup"><span data-stu-id="04e06-108">There are two XLL-only C API functions that provide access to these handles: the [xlGetInst](xlgetinst.md) function and the [xlGetHwnd](xlgethwnd.md) function respectively.</span></span> <span data-ttu-id="04e06-109">在 Win32 中，所有句柄都是 32 位整数。</span><span class="sxs-lookup"><span data-stu-id="04e06-109">In Win32, all handles are 32-bit integers.</span></span> <span data-ttu-id="04e06-110">但是，在设计 **XLOPER** 时，Windows是一个 16 位系统。</span><span class="sxs-lookup"><span data-stu-id="04e06-110">However, when the **XLOPER** was designed, Windows was a 16-bit system.</span></span> <span data-ttu-id="04e06-111">因此，仅允许 16 位句柄使用结构。</span><span class="sxs-lookup"><span data-stu-id="04e06-111">Therefore, the structure only allowed for 16-bit handles.</span></span> <span data-ttu-id="04e06-112">在 Win32 中，当使用 **Excel4** 或 **Excel4v** 调用时 **，xlGetInst** 函数和 **xlGetHwnd** 函数仅返回完整 32 位句柄的低部分。</span><span class="sxs-lookup"><span data-stu-id="04e06-112">In Win32, when called with **Excel4** or **Excel4v**, the **xlGetInst** function and the **xlGetHwnd** function return only the low part of the full 32-bit handle.</span></span> 
  
<span data-ttu-id="04e06-113">在 Excel 2007 及更高版本中，当使用 [Excel12 或 Excel12v](excel4-excel12.md)调用这些函数时，返回的 **XLOPER12** 包含完整的 32 位句柄。 [](excel4v-excel12v.md)</span><span class="sxs-lookup"><span data-stu-id="04e06-113">In Excel 2007 and later versions, when these functions are called with [Excel12](excel4-excel12.md) or [Excel12v](excel4v-excel12v.md), the returned **XLOPER12** contains the full 32-bit handle.</span></span> 
  
<span data-ttu-id="04e06-114">获取完整实例句柄在任何版本的 Excel 中都非常简单，因为它将传递给 Windows 回调 **DllMain，** 该回调在 DLL 加载时调用。</span><span class="sxs-lookup"><span data-stu-id="04e06-114">Obtaining the full instance handle is simple in any version of Excel, as it is passed to the Windows callback **DllMain**, which is called when the DLL is loaded.</span></span> <span data-ttu-id="04e06-115">如果在全局变量中记录此实例句柄，则无需调用 **xlGetInst** 函数。</span><span class="sxs-lookup"><span data-stu-id="04e06-115">If you record this instance handle in a global variable, you never need to call the **xlGetInst** function.</span></span> 
  
## <a name="obtaining-the-main-excel-handle-in-excel-2003-and-earlier"></a><span data-ttu-id="04e06-116">获取 Excel 2003 及更早Excel中的 Main Excel Handle</span><span class="sxs-lookup"><span data-stu-id="04e06-116">Obtaining the Main Excel Handle in Excel 2003 and Earlier</span></span>

<span data-ttu-id="04e06-117">若要获取 Excel 2003 和更早 32 位版本中的主 Excel 句柄，必须先调用 **xlGetHwnd** 函数以获取实际句柄的低值字。</span><span class="sxs-lookup"><span data-stu-id="04e06-117">To obtain the main Excel handle in Excel 2003 and earlier 32-bit versions, you must first call the **xlGetHwnd** function to obtain the low word of the actual handle.</span></span> <span data-ttu-id="04e06-118">然后，必须重新访问顶级窗口列表，以搜索与返回的低单词的匹配项。</span><span class="sxs-lookup"><span data-stu-id="04e06-118">Then, you must iterate the list of top-level windows to search for a match with the returned low word.</span></span> <span data-ttu-id="04e06-119">以下代码演示了此技术。</span><span class="sxs-lookup"><span data-stu-id="04e06-119">The following code illustrates the technique.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="04e06-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04e06-120">See also</span></span>



[<span data-ttu-id="04e06-121">在 DLL 或 XLL 内显示对话框</span><span class="sxs-lookup"><span data-stu-id="04e06-121">Displaying Dialog Boxes from Within a DLL or XLL</span></span>](displaying-dialog-boxes-from-within-a-dll-or-xll.md)
  
[<span data-ttu-id="04e06-122">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="04e06-122">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)
  
[<span data-ttu-id="04e06-123">开发 Excel XLL</span><span class="sxs-lookup"><span data-stu-id="04e06-123">Developing Excel XLLs</span></span>](developing-excel-xlls.md)

