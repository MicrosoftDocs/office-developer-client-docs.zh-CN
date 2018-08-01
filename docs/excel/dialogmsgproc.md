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
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 3a69d192babbcf0419850e203f51d8cfd81cdef6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773642"
---
# <a name="dialogmsgproc"></a><span data-ttu-id="35d83-104">DIALOGMsgProc</span><span class="sxs-lookup"><span data-stu-id="35d83-104">DIALOGMsgProc</span></span>

<span data-ttu-id="35d83-105">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="35d83-105">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="35d83-106">此过程相关联的[fShowDialog](fshowdialog.md)本机 Windows 对话框显示。</span><span class="sxs-lookup"><span data-stu-id="35d83-106">This procedure is associated with the native Windows dialog box that [fShowDialog](fshowdialog.md) displays.</span></span> <span data-ttu-id="35d83-107">它提供了 Windows 用户运行对话框的按钮，输入字段或控件之一时，会发生的事件 （邮件） 调用服务例程。</span><span class="sxs-lookup"><span data-stu-id="35d83-107">It provides the service routines called by Windows for the events (messages) that occur when the user operates one of the dialog box's buttons, entry fields, or controls.</span></span> 
  
```cs
BOOL CALLBACK DIALOGMsgProc(HWND hWndDlg, UINT message, WPARAM wParam, LPARAM lParam);
```

## <a name="parameters"></a><span data-ttu-id="35d83-108">参数</span><span class="sxs-lookup"><span data-stu-id="35d83-108">Parameters</span></span>

 <span data-ttu-id="35d83-109">_hWndDlg_(**HWND**)</span><span class="sxs-lookup"><span data-stu-id="35d83-109">_hWndDlg_ (**HWND**)</span></span>
  
<span data-ttu-id="35d83-110">包含对话框的 HWND Windows 句柄。</span><span class="sxs-lookup"><span data-stu-id="35d83-110">Contains the HWND Windows handle of the dialog box.</span></span>
  
 <span data-ttu-id="35d83-111">_消息_(**UINT**)</span><span class="sxs-lookup"><span data-stu-id="35d83-111">_message_ (**UINT**)</span></span>
  
<span data-ttu-id="35d83-112">要回复的消息。</span><span class="sxs-lookup"><span data-stu-id="35d83-112">The message to respond to.</span></span>
  
 <span data-ttu-id="35d83-113">_wParam_(**WPARAM**)</span><span class="sxs-lookup"><span data-stu-id="35d83-113">_wParam_ (**WPARAM**)</span></span>
  
 <span data-ttu-id="35d83-114">_lParam_(**LPARAM**)</span><span class="sxs-lookup"><span data-stu-id="35d83-114">_lParam_ (**LPARAM**)</span></span>
  
<span data-ttu-id="35d83-115">通过 Windows 传递的参数。</span><span class="sxs-lookup"><span data-stu-id="35d83-115">Arguments passed by Windows.</span></span>
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="35d83-116">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="35d83-116">Property value/Return value</span></span>

 <span data-ttu-id="35d83-117">**TRUE**如果消息处理， **FALSE**如果不需要。</span><span class="sxs-lookup"><span data-stu-id="35d83-117">**TRUE** if message processed, **FALSE** if not.</span></span> 
  
### <a name="example"></a><span data-ttu-id="35d83-118">示例</span><span class="sxs-lookup"><span data-stu-id="35d83-118">Example</span></span>

<span data-ttu-id="35d83-119">请参阅`\SAMPLES\GENERIC\GENERIC.C`的此函数的源代码。</span><span class="sxs-lookup"><span data-stu-id="35d83-119">See  `\SAMPLES\GENERIC\GENERIC.C` for the source code for this function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="35d83-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="35d83-120">See also</span></span>



[<span data-ttu-id="35d83-121">通用 DLL 中的函数</span><span class="sxs-lookup"><span data-stu-id="35d83-121">Functions in the Generic DLL</span></span>](functions-in-the-generic-dll.md)

