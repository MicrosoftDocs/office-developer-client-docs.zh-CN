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
# <a name="xlabort"></a>xlAbort

 **适用于** Excel 2013 | Office 2013 | Visual Studio 
  
在系统中生成处理器到其他任务，并检查用户是否已按**ESC**键取消宏。 如果用户已工作簿重新计算过程中按**ESC** ，它可以还通过检测到从工作表函数中调用此函数。 
  
```cs
Excel12(xlAbort, LPXLOPER12 pxRes, 1, LPXLOPER12 pxRetain);
```

## <a name="parameters"></a>参数

 _pxRetain_(**xltypeBool**)
  
（可选）。 如果**FALSE**，此函数，检查中断条件，并清除任何待定的中断。 这就使用户得以继续中断条件。 如果此参数被省略，或为**TRUE**，则函数检查用户中止而不清除。
  
## <a name="property-valuereturn-value"></a>属性值/返回值

如果用户已按**ESC**，则返回**TRUE** (**xltypeBool**)。
  
## <a name="remarks"></a>说明

### 

#### <a name="frequent-calls-may-be-needed"></a>可能需要常用的呼叫

功能和可能需要很长时间的命令应调用此函数经常以在系统中产生向其他任务处理器。
  
#### <a name="avoid-sensitive-language"></a>避免敏感的语言

避免使用术语"中止"用户界面中。 请考虑使用"取消""停止，""中断"或"Stop"改为。
  
## <a name="example"></a>示例

下面的代码重复发生将活动单元格移动工作表上直到经过一分钟或用户按**ESC**。 有时，它调用函数**xlAbort** 。 这会产生处理器，减轻协作式多任务。 
  
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

