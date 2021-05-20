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
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 08ab69252520e76a5631c5e32a3970d2d95b1ff4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436655"
---
# <a name="xlabort"></a><span data-ttu-id="c225d-104">xlAbort</span><span class="sxs-lookup"><span data-stu-id="c225d-104">xlAbort</span></span>

 <span data-ttu-id="c225d-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="c225d-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="c225d-106">将处理器处理到系统中的其他任务，并检查用户是否已按 **Esc** 取消宏。</span><span class="sxs-lookup"><span data-stu-id="c225d-106">Yields the processor to other tasks in the system and checks whether the user has pressed **ESC** to cancel a macro.</span></span> <span data-ttu-id="c225d-107">如果用户在工作簿重新计算过程中按下 **了 ESC，** 则通过调用此函数还可以从工作表函数中检测到它。</span><span class="sxs-lookup"><span data-stu-id="c225d-107">If the user has pressed **ESC** during a workbook recalculation, it can also be detected from within a worksheet function by calling this function.</span></span> 
  
```cs
Excel12(xlAbort, LPXLOPER12 pxRes, 1, LPXLOPER12 pxRetain);
```

## <a name="parameters"></a><span data-ttu-id="c225d-108">参数</span><span class="sxs-lookup"><span data-stu-id="c225d-108">Parameters</span></span>

 <span data-ttu-id="c225d-109">_pxRetain_ (**xltypeBool)**</span><span class="sxs-lookup"><span data-stu-id="c225d-109">_pxRetain_ (**xltypeBool**)</span></span>
  
<span data-ttu-id="c225d-110"> (可选) 。</span><span class="sxs-lookup"><span data-stu-id="c225d-110">(Optional).</span></span> <span data-ttu-id="c225d-111">如果 **为 FALSE，** 则此函数将检查中断条件并清除任何挂起的中断。</span><span class="sxs-lookup"><span data-stu-id="c225d-111">If **FALSE**, this function checks for the break condition and clears any pending break.</span></span> <span data-ttu-id="c225d-112">这使用户可以继续，而不管中断条件如何。</span><span class="sxs-lookup"><span data-stu-id="c225d-112">This enables the user to continue despite the break condition.</span></span> <span data-ttu-id="c225d-113">如果省略此参数或为 **TRUE，** 则函数会检查用户中止，而不清除它。</span><span class="sxs-lookup"><span data-stu-id="c225d-113">If this argument is omitted or is **TRUE**, the function checks for a user abort without clearing it.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c225d-114">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="c225d-114">Property value/Return value</span></span>

<span data-ttu-id="c225d-115">返回 **TRUE** (**xltypeBool**) 如果用户已按下 **ESC**。</span><span class="sxs-lookup"><span data-stu-id="c225d-115">Returns **TRUE** (**xltypeBool**) if the user has pressed **ESC**.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="c225d-116">备注</span><span class="sxs-lookup"><span data-stu-id="c225d-116">Remarks</span></span>

### 

#### <a name="frequent-calls-may-be-needed"></a><span data-ttu-id="c225d-117">可能需要频繁呼叫</span><span class="sxs-lookup"><span data-stu-id="c225d-117">Frequent Calls May Be Needed</span></span>

<span data-ttu-id="c225d-118">可能需要很长时间的函数和命令应频繁调用此函数，以将处理器分配给系统中的其他任务。</span><span class="sxs-lookup"><span data-stu-id="c225d-118">Functions and commands that could take a long time should call this function frequently to yield the processor to other tasks in the system.</span></span>
  
#### <a name="avoid-sensitive-language"></a><span data-ttu-id="c225d-119">避免使用敏感语言</span><span class="sxs-lookup"><span data-stu-id="c225d-119">Avoid Sensitive Language</span></span>

<span data-ttu-id="c225d-120">避免在用户界面中使用术语"Abort"。</span><span class="sxs-lookup"><span data-stu-id="c225d-120">Avoid using the term "Abort" in your user interface.</span></span> <span data-ttu-id="c225d-121">请考虑使用"取消"、"终止"、"中断"或"停止"。</span><span class="sxs-lookup"><span data-stu-id="c225d-121">Consider using "Cancel," "Halt," "Break," or "Stop" instead.</span></span>
  
## <a name="example"></a><span data-ttu-id="c225d-122">示例</span><span class="sxs-lookup"><span data-stu-id="c225d-122">Example</span></span>

<span data-ttu-id="c225d-123">下面的代码重复移动工作表上的活动单元格，直到一分钟过去或直到用户按 **ESC。**</span><span class="sxs-lookup"><span data-stu-id="c225d-123">The following code repeatedly moves the active cell on a sheet until one minute has elapsed or until the user presses **ESC**.</span></span> <span data-ttu-id="c225d-124">它偶尔调用 **函数 xlAbort。**</span><span class="sxs-lookup"><span data-stu-id="c225d-124">It calls the function **xlAbort** occasionally.</span></span> <span data-ttu-id="c225d-125">这将生成处理器，并缓动协作多任务。</span><span class="sxs-lookup"><span data-stu-id="c225d-125">This yields the processor, easing cooperative multitasking.</span></span> 
  
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

## <a name="see-also"></a><span data-ttu-id="c225d-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c225d-126">See also</span></span>



[<span data-ttu-id="c225d-127">只能从 DLL 或 XLL 调用的 C API 函数</span><span class="sxs-lookup"><span data-stu-id="c225d-127">C API Functions That Can Be Called Only from a DLL or XLL</span></span>](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

