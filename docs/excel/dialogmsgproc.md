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
# <a name="dialogmsgproc"></a><span data-ttu-id="91f21-104">DIALOGMsgProc</span><span class="sxs-lookup"><span data-stu-id="91f21-104">DIALOGMsgProc</span></span>

<span data-ttu-id="91f21-105">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="91f21-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="91f21-106">此过程与[fShowDialog](fshowdialog.md)显示的本机Windows对话框相关联。</span><span class="sxs-lookup"><span data-stu-id="91f21-106">This procedure is associated with the native Windows dialog box that [fShowDialog](fshowdialog.md) displays.</span></span> <span data-ttu-id="91f21-107">它提供由 Windows 调用的服务例程， (用户) 按钮、输入字段或控件之一时发生的) 消息。</span><span class="sxs-lookup"><span data-stu-id="91f21-107">It provides the service routines called by Windows for the events (messages) that occur when the user operates one of the dialog box's buttons, entry fields, or controls.</span></span> 
  
```cs
BOOL CALLBACK DIALOGMsgProc(HWND hWndDlg, UINT message, WPARAM wParam, LPARAM lParam);
```

## <a name="parameters"></a><span data-ttu-id="91f21-108">参数</span><span class="sxs-lookup"><span data-stu-id="91f21-108">Parameters</span></span>

 <span data-ttu-id="91f21-109">_hWndDlg_ (**HWND**) </span><span class="sxs-lookup"><span data-stu-id="91f21-109">_hWndDlg_ (**HWND**)</span></span>
  
<span data-ttu-id="91f21-110">包含对话框Windows HWND 对象句柄。</span><span class="sxs-lookup"><span data-stu-id="91f21-110">Contains the HWND Windows handle of the dialog box.</span></span>
  
 <span data-ttu-id="91f21-111">_message_ (**UINT**) </span><span class="sxs-lookup"><span data-stu-id="91f21-111">_message_ (**UINT**)</span></span>
  
<span data-ttu-id="91f21-112">要响应的邮件。</span><span class="sxs-lookup"><span data-stu-id="91f21-112">The message to respond to.</span></span>
  
 <span data-ttu-id="91f21-113">_wParam_ (**WPARAM**) </span><span class="sxs-lookup"><span data-stu-id="91f21-113">_wParam_ (**WPARAM**)</span></span>
  
 <span data-ttu-id="91f21-114">_lParam_ (**LPARAM**) </span><span class="sxs-lookup"><span data-stu-id="91f21-114">_lParam_ (**LPARAM**)</span></span>
  
<span data-ttu-id="91f21-115">由 Windows。</span><span class="sxs-lookup"><span data-stu-id="91f21-115">Arguments passed by Windows.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="91f21-116">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="91f21-116">Property value/Return value</span></span>

 <span data-ttu-id="91f21-117">如果邮件已处理，则其为 **TRUE;** 如果未处理，则为 **FALSE。**</span><span class="sxs-lookup"><span data-stu-id="91f21-117">**TRUE** if message processed, **FALSE** if not.</span></span> 
  
### <a name="example"></a><span data-ttu-id="91f21-118">示例</span><span class="sxs-lookup"><span data-stu-id="91f21-118">Example</span></span>

<span data-ttu-id="91f21-119">有关  `\SAMPLES\GENERIC\GENERIC.C` 此函数的源代码，请参阅 。</span><span class="sxs-lookup"><span data-stu-id="91f21-119">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="91f21-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91f21-120">See also</span></span>



[<span data-ttu-id="91f21-121">通用 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="91f21-121">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

