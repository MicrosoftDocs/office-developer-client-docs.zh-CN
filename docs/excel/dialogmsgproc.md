---
title: DIALOGMsgProc
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
f1_keywords:
- DIALOGMsgProc
keywords:
- dialogmsgproc 函数 [excel 2007]
localization_priority: Normal
ms.assetid: 9a538e83-ba34-4806-bb8c-7cda3beb6b66
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 1de1b73f5672067f07518ef3367d77349395a1c3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406512"
---
# <a name="dialogmsgproc"></a><span data-ttu-id="a7f88-104">DIALOGMsgProc</span><span class="sxs-lookup"><span data-stu-id="a7f88-104">DIALOGMsgProc</span></span>

<span data-ttu-id="a7f88-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a7f88-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="a7f88-106">此过程与[fShowDialog](fshowdialog.md)显示的本机 Windows 对话框相关联。</span><span class="sxs-lookup"><span data-stu-id="a7f88-106">This procedure is associated with the native Windows dialog box that [fShowDialog](fshowdialog.md) displays.</span></span> <span data-ttu-id="a7f88-107">它提供 Windows 针对事件 (消息) 调用的服务例程, 这些事件在用户操作对话框的按钮、条目字段或控件之一时发生。</span><span class="sxs-lookup"><span data-stu-id="a7f88-107">It provides the service routines called by Windows for the events (messages) that occur when the user operates one of the dialog box's buttons, entry fields, or controls.</span></span> 
  
```cs
BOOL CALLBACK DIALOGMsgProc(HWND hWndDlg, UINT message, WPARAM wParam, LPARAM lParam);
```

## <a name="parameters"></a><span data-ttu-id="a7f88-108">参数</span><span class="sxs-lookup"><span data-stu-id="a7f88-108">Parameters</span></span>

 <span data-ttu-id="a7f88-109">_hWndDlg_(**HWND**)</span><span class="sxs-lookup"><span data-stu-id="a7f88-109">_hWndDlg_ (**HWND**)</span></span>
  
<span data-ttu-id="a7f88-110">包含对话框的 HWND 窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="a7f88-110">Contains the HWND Windows handle of the dialog box.</span></span>
  
 <span data-ttu-id="a7f88-111">_邮件_(**UINT**)</span><span class="sxs-lookup"><span data-stu-id="a7f88-111">_message_ (**UINT**)</span></span>
  
<span data-ttu-id="a7f88-112">要响应的邮件。</span><span class="sxs-lookup"><span data-stu-id="a7f88-112">The message to respond to.</span></span>
  
 <span data-ttu-id="a7f88-113">_wParam_(**WPARAM**)</span><span class="sxs-lookup"><span data-stu-id="a7f88-113">_wParam_ (**WPARAM**)</span></span>
  
 <span data-ttu-id="a7f88-114">_lParam_(**LPARAM**)</span><span class="sxs-lookup"><span data-stu-id="a7f88-114">_lParam_ (**LPARAM**)</span></span>
  
<span data-ttu-id="a7f88-115">由 Windows 传递的参数。</span><span class="sxs-lookup"><span data-stu-id="a7f88-115">Arguments passed by Windows.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="a7f88-116">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="a7f88-116">Property value/Return value</span></span>

 <span data-ttu-id="a7f88-117">如果已处理邮件,**则为 TRUE** , 否则为**FALSE** 。</span><span class="sxs-lookup"><span data-stu-id="a7f88-117">**TRUE** if message processed, **FALSE** if not.</span></span> 
  
### <a name="example"></a><span data-ttu-id="a7f88-118">示例</span><span class="sxs-lookup"><span data-stu-id="a7f88-118">Example</span></span>

<span data-ttu-id="a7f88-119">有关`\SAMPLES\GENERIC\GENERIC.C`此函数的源代码, 请参阅。</span><span class="sxs-lookup"><span data-stu-id="a7f88-119">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="a7f88-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a7f88-120">See also</span></span>



[<span data-ttu-id="a7f88-121">通用 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="a7f88-121">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

