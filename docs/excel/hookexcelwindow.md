---
title: HookExcelWindow
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- HookExcelWindow
keywords:
- hookexcelwindow 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 13f0ae5e-9951-4e89-a245-7cf68c6f6724
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: 8965cc6b1e3d24001c42744f2ee7d447aa4c79b5
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773760"
---
# <a name="hookexcelwindow"></a><span data-ttu-id="45f93-104">HookExcelWindow</span><span class="sxs-lookup"><span data-stu-id="45f93-104">HookExcelWindow</span></span>

 <span data-ttu-id="45f93-105">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="45f93-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="45f93-106">安装**ExcelCursorProc** ，以便在 Microsoft Excel 主**WndProc**之前调用。</span><span class="sxs-lookup"><span data-stu-id="45f93-106">Installs **ExcelCursorProc** so that it is called before the Microsoft Excel main **WndProc**.</span></span>
  
```cs
extern void FAR PASCAL HookExcelWindow(HANDLE hWndExcel);
```

## <a name="parameters"></a><span data-ttu-id="45f93-107">参数</span><span class="sxs-lookup"><span data-stu-id="45f93-107">Parameters</span></span>

 <span data-ttu-id="45f93-108">_hWndExcel_（**处理**）</span><span class="sxs-lookup"><span data-stu-id="45f93-108">_hWndExcel_ (**HANDLE**)</span></span>
  
<span data-ttu-id="45f93-109">Excel 主窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="45f93-109">The Excel main Windows handle.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="45f93-110">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="45f93-110">Property value/Return value</span></span>

<span data-ttu-id="45f93-111">该函数不返回值。</span><span class="sxs-lookup"><span data-stu-id="45f93-111">The function does not return a value.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="45f93-112">备注</span><span class="sxs-lookup"><span data-stu-id="45f93-112">Remarks</span></span>

<span data-ttu-id="45f93-113">该函数获取 Excel **WndProc** **GetWindowLong()** 使用的地址。</span><span class="sxs-lookup"><span data-stu-id="45f93-113">The function obtains the address of the Excel **WndProc** through the use of **GetWindowLong()**.</span></span> <span data-ttu-id="45f93-114">它将此值存储在全局可用于调用默认**WndProc**和还将其还原。</span><span class="sxs-lookup"><span data-stu-id="45f93-114">It stores this value in a global that can be used to call the default **WndProc** and also to restore it.</span></span> <span data-ttu-id="45f93-115">最后，它会替换此地址**ExcelCursorProc**使用**SetWindowLong()** 的地址。</span><span class="sxs-lookup"><span data-stu-id="45f93-115">Finally, it replaces this address with the address of **ExcelCursorProc** using **SetWindowLong()**.</span></span>
  
### <a name="example"></a><span data-ttu-id="45f93-116">示例</span><span class="sxs-lookup"><span data-stu-id="45f93-116">Example</span></span>

<span data-ttu-id="45f93-117">请参阅`\SAMPLES\GENERIC\GENERIC.C`的此函数的源代码。</span><span class="sxs-lookup"><span data-stu-id="45f93-117">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="45f93-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="45f93-118">See also</span></span>



[<span data-ttu-id="45f93-119">泛型 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="45f93-119">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

