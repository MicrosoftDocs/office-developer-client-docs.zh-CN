---
title: UnhookExcelWindow
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- UnhookExcelWindow
keywords:
- unhookexcelwindow 函数
localization_priority: Normal
ms.assetid: 6508cb69-0c7c-4d8c-a466-dd79eb13e316
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 7b70bf4ed0ff45921df407605baa692c7621bca4
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773828"
---
# <a name="unhookexcelwindow"></a><span data-ttu-id="d74a4-104">UnhookExcelWindow</span><span class="sxs-lookup"><span data-stu-id="d74a4-104">UnhookExcelWindow</span></span>

 <span data-ttu-id="d74a4-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d74a4-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="d74a4-106">删除以前安装的**HookExcelWindow** **ExcelCursorProc** 。</span><span class="sxs-lookup"><span data-stu-id="d74a4-106">Removes the **ExcelCursorProc** that was previously installed by **HookExcelWindow**.</span></span> <span data-ttu-id="d74a4-107">这将具有已完成，以便**ExcelCursorProc**已在 Microsoft Excel 主**WndProc**之前调用。</span><span class="sxs-lookup"><span data-stu-id="d74a4-107">This would have been done so that **ExcelCursorProc** was called before the Microsoft Excel main **WndProc**.</span></span>
  
```cs
extern void FAR PASCAL UnhookExcelWindow(HANDLE hWndExcel);
```

## <a name="parameters"></a><span data-ttu-id="d74a4-108">参数</span><span class="sxs-lookup"><span data-stu-id="d74a4-108">Parameters</span></span>

 <span data-ttu-id="d74a4-109">_hWndExcel_（**处理**）</span><span class="sxs-lookup"><span data-stu-id="d74a4-109">_hWndExcel_ (**HANDLE**)</span></span>
  
<span data-ttu-id="d74a4-110">Excel 主窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="d74a4-110">The Excel main Windows handle.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="d74a4-111">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="d74a4-111">Property value/Return value</span></span>

<span data-ttu-id="d74a4-112">该函数不返回值。</span><span class="sxs-lookup"><span data-stu-id="d74a4-112">The function does not return a value.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d74a4-113">备注</span><span class="sxs-lookup"><span data-stu-id="d74a4-113">Remarks</span></span>

<span data-ttu-id="d74a4-114">此函数将还原 Excel 默认**WndProc**使用**SetWindowLong()** 还原**HookExcelWindow()** 保存的地址。</span><span class="sxs-lookup"><span data-stu-id="d74a4-114">This function restores the Excel default **WndProc** using **SetWindowLong()** to restore the address that was saved by **HookExcelWindow()**.</span></span>
  
### <a name="example"></a><span data-ttu-id="d74a4-115">示例</span><span class="sxs-lookup"><span data-stu-id="d74a4-115">Example</span></span>

<span data-ttu-id="d74a4-116">请参阅`\SAMPLES\GENERIC\GENERIC.C`的此函数的源代码。</span><span class="sxs-lookup"><span data-stu-id="d74a4-116">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="d74a4-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d74a4-117">See also</span></span>



[<span data-ttu-id="d74a4-118">泛型 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="d74a4-118">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

