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
# <a name="xlabort"></a>xlAbort

 **适用于**：Excel 2013 | Office 2013 | Visual Studio 
  
将处理器生成到系统中的其他任务, 并检查用户是否已按**ESC**取消宏。 如果用户在重新计算工作簿期间按下了**ESC** , 也可以通过调用此函数从工作表函数中检测到。 
  
```cs
Excel12(xlAbort, LPXLOPER12 pxRes, 1, LPXLOPER12 pxRetain);
```

## <a name="parameters"></a>参数

 _pxRetain_(**xltypeBool**)
  
(可选)。 如果**为 FALSE**, 则此函数将检查中断条件并清除任何挂起的中断。 这使用户可以在中断条件的情况继续进行。 如果此参数被省略或为**TRUE**, 则函数将检查用户中止而不清除它。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果用户按**ESC 键**,**则返回 TRUE** (**xltypeBool**)。
  
## <a name="remarks"></a>说明

### 

#### <a name="frequent-calls-may-be-needed"></a>可能需要频繁的呼叫

可能需要很长时间的函数和命令应经常调用此函数, 以使处理器进入系统中的其他任务。
  
#### <a name="avoid-sensitive-language"></a>避免敏感语言

避免在用户界面中使用 "Abort" 一词。 请考虑改为使用 "取消"、"暂停"、"中断" 或 "停止"。
  
## <a name="example"></a>示例

以下代码将重复移动工作表上的活动单元格, 直到一分钟之后或用户按**ESC**。 它偶尔调用函数**xlAbort** 。 这将生成处理器, 从而简化合作多任务。 
  
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

## <a name="see-also"></a>另请参阅



[只能从 DLL 或 XLL 调用的 C API 函数](c-api-functions-that-can-be-called-only-from-a-dll-or-xll.md)

