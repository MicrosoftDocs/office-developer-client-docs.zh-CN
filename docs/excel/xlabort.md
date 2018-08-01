---
title: xlAbort
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- xlAbort
keywords:
- xlabort 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 0fe71454-6b00-464b-8abf-afb209d57754
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: e90cbe496404b4cc602dee1ad21c91c8f5f91bfd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773834"
---
# <a name="xlabort"></a><span data-ttu-id="1712d-104">xlAbort</span><span class="sxs-lookup"><span data-stu-id="1712d-104">xlAbort</span></span>

 <span data-ttu-id="1712d-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="1712d-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="1712d-106">在系统中生成处理器到其他任务，并检查用户是否已按**ESC**键取消宏。</span><span class="sxs-lookup"><span data-stu-id="1712d-106">Yields the processor to other tasks in the system and checks whether the user has pressed **ESC** to cancel a macro.</span></span> <span data-ttu-id="1712d-107">如果用户已工作簿重新计算过程中按**ESC** ，它可以还通过检测到从工作表函数中调用此函数。</span><span class="sxs-lookup"><span data-stu-id="1712d-107">If the user has pressed **ESC** during a workbook recalculation, it can also be detected from within a worksheet function by calling this function.</span></span> 
  
```cs
Excel12(xlAbort, LPXLOPER12 pxRes, 1, LPXLOPER12 pxRetain);
```

## <a name="parameters"></a><span data-ttu-id="1712d-108">参数</span><span class="sxs-lookup"><span data-stu-id="1712d-108">Parameters</span></span>

 <span data-ttu-id="1712d-109">_pxRetain_(**xltypeBool**)</span><span class="sxs-lookup"><span data-stu-id="1712d-109">_pxRetain_ (**xltypeBool**)</span></span>
  
<span data-ttu-id="1712d-110">（可选）。</span><span class="sxs-lookup"><span data-stu-id="1712d-110">(Optional).</span></span> <span data-ttu-id="1712d-111">如果**FALSE**，此函数，检查中断条件，并清除任何待定的中断。</span><span class="sxs-lookup"><span data-stu-id="1712d-111">If **FALSE**, this function checks for the break condition and clears any pending break.</span></span> <span data-ttu-id="1712d-112">这就使用户得以继续中断条件。</span><span class="sxs-lookup"><span data-stu-id="1712d-112">This enables the user to continue despite the break condition.</span></span> <span data-ttu-id="1712d-113">如果此参数被省略，或为**TRUE**，则函数检查用户中止而不清除。</span><span class="sxs-lookup"><span data-stu-id="1712d-113">If this argument is omitted or is **TRUE**, the function checks for a user abort without clearing it.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="1712d-114">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="1712d-114">Property value/Return value</span></span>

<span data-ttu-id="1712d-115">如果用户已按**ESC**，则返回**TRUE** (**xltypeBool**)。</span><span class="sxs-lookup"><span data-stu-id="1712d-115">Returns **TRUE** (**xltypeBool**) if the user has pressed **ESC**.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="1712d-116">说明</span><span class="sxs-lookup"><span data-stu-id="1712d-116">Remarks</span></span>

### 

#### <a name="frequent-calls-may-be-needed"></a><span data-ttu-id="1712d-117">可能需要常用的呼叫</span><span class="sxs-lookup"><span data-stu-id="1712d-117">Frequent Calls May Be Needed</span></span>

<span data-ttu-id="1712d-118">功能和可能需要很长时间的命令应调用此函数经常以在系统中产生向其他任务处理器。</span><span class="sxs-lookup"><span data-stu-id="1712d-118">Functions and commands that could take a long time should call this function frequently to yield the processor to other tasks in the system.</span></span>
  
#### <a name="avoid-sensitive-language"></a><span data-ttu-id="1712d-119">避免敏感的语言</span><span class="sxs-lookup"><span data-stu-id="1712d-119">Avoid Sensitive Language</span></span>

<span data-ttu-id="1712d-120">避免使用术语"中止"用户界面中。</span><span class="sxs-lookup"><span data-stu-id="1712d-120">Avoid using the term "Abort" in your user interface.</span></span> <span data-ttu-id="1712d-121">请考虑使用"取消""停止，""中断"或"Stop"改为。</span><span class="sxs-lookup"><span data-stu-id="1712d-121">Consider using "Cancel," "Halt," "Break," or "Stop" instead.</span></span>
  
## <a name="example"></a><span data-ttu-id="1712d-122">示例</span><span class="sxs-lookup"><span data-stu-id="1712d-122">Example</span></span>

<span data-ttu-id="1712d-123">下面的代码重复发生将活动单元格移动工作表上直到经过一分钟或用户按**ESC**。</span><span class="sxs-lookup"><span data-stu-id="1712d-123">The following code repeatedly moves the active cell on a sheet until one minute has elapsed or until the user presses **ESC**.</span></span> <span data-ttu-id="1712d-124">有时，它调用函数**xlAbort** 。</span><span class="sxs-lookup"><span data-stu-id="1712d-124">It calls the function **xlAbort** occasionally.</span></span> <span data-ttu-id="1712d-125">这会产生处理器，减轻协作式多任务。</span><span class="sxs-lookup"><span data-stu-id="1712d-125">This yields the processor, easing cooperative multitasking.</span></span> 
  
 `\SAMPLES\GENERIC\GENERIC.C`
  
```cs
int WINAPI fDance(void)
{
   DWORD dtickStart;
   XLOPER12 xAbort, xConfirm;
   int boolSheet;
   int col=0;
   XCHAR rgch[32];
//
// Check what kind of sheet is active. If it is a worksheet or macro
// sheet, this function will move the selection in a loop to show
// activity. In any case, it will update the status bar with a countdown.
//
// Call xlSheetId; if that fails the current sheet is not a macro sheet or
// worksheet. Next, get the time at which to start. Then start a while
// loop that will run for one minute. During the while loop, check if the
// user has pressed ESC. If true, confirm the abort. If the abort is
// confirmed, clear the message bar and return; if the abort is not
// confirmed, clear the abort state and continue. After checking for an
// abort, move the active cell if on a worksheet or macro. Then
// update the status bar with the time remaining.
//
// This block uses TempActiveCell12(), which creates a temporary XLOPER12.
// The XLOPER12 contains a reference to a single cell on the active sheet.
// This function is part of the framework library.
//
   boolSheet = (Excel12f(xlSheetId, 0, 0) == xlretSuccess);
   dtickStart = GetTickCount();
   while (GetTickCount() < dtickStart + 60000L)
   {
      Excel12f(xlAbort, &xAbort, 0);
      if (xAbort.val.xbool)
      {
         Excel12f(xlcAlert, &xConfirm, 2,
           TempStr12(L"Are you sure you want to cancel this operation?"),
              TempNum12(1));
         if (xConfirm.val.xbool)
         {
            Excel12f(xlcMessage, 0, 1, TempBool12(0));
            return 1;
         }
         else
         {
            Excel12f(xlAbort, 0, 1, TempBool12(0));
         }
      }
      if (boolSheet)
      {
         Excel12f(xlcSelect, 0, 1,
            TempActiveCell12(0,(BYTE)col));
         col = (col + 1) & 3;
      }
      wsprintfW(rgch,L"0:%lu",
         (60000 + dtickStart - GetTickCount()) / 1000L);
      Excel12f(xlcMessage, 0, 2, TempBool12(1), TempStr12(rgch));
   }
   Excel12f(xlcMessage, 0, 1, TempBool12(0));
   return 1;
}
```

## <a name="see-also"></a><span data-ttu-id="1712d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1712d-126">See also</span></span>



[<span data-ttu-id="1712d-127">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="1712d-127">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

