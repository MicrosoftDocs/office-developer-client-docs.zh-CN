---
title: ACCELERATEABSDI
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ACCELERATEABSDI
api_type:
- HeaderDef
ms.assetid: da67dcf4-1411-4fc9-992c-115485019bd3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 46e87caa68a45a188272340db408c52546f02a57
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33420372"
---
# <a name="accelerateabsdi"></a><span data-ttu-id="df52c-103">ACCELERATEABSDI</span><span class="sxs-lookup"><span data-stu-id="df52c-103">ACCELERATEABSDI</span></span>
 
<span data-ttu-id="df52c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="df52c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="df52c-105">定义回调函数以在无模式通讯簿对话框中处理加速键。</span><span class="sxs-lookup"><span data-stu-id="df52c-105">Defines a callback function to process accelerator keys in a modeless address book dialog box.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="df52c-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="df52c-106">Header file:</span></span>  <br/> |<span data-ttu-id="df52c-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="df52c-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="df52c-108">定义的函数实现方：</span><span class="sxs-lookup"><span data-stu-id="df52c-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="df52c-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="df52c-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="df52c-110">由调用的已定义函数：</span><span class="sxs-lookup"><span data-stu-id="df52c-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="df52c-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="df52c-111">Client applications</span></span>  <br/> |
   
```cpp
BOOL (STDMETHODCALLTYPE ACCELERATEABSDI)( 
  ULONG_PTR ulUIParam,
  LPVOID lpvmsg
);
```

## <a name="parameters"></a><span data-ttu-id="df52c-112">参数</span><span class="sxs-lookup"><span data-stu-id="df52c-112">Parameters</span></span>

 <span data-ttu-id="df52c-113">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="df52c-113">_ulUIParam_</span></span>
  
> <span data-ttu-id="df52c-114">[in]用于将用户界面信息传递给函数的特定于实现的值。</span><span class="sxs-lookup"><span data-stu-id="df52c-114">[in] An implementation-specific value used for passing user interface information to a function.</span></span> <span data-ttu-id="df52c-115">在 Microsoft Windows 上运行的应用程序中 _，ulUIParam_ 是对话框的父窗口句柄，并且类型为 HWND，请强制转换到ULONG_PTR **。**</span><span class="sxs-lookup"><span data-stu-id="df52c-115">In applications running on Microsoft Windows,  _ulUIParam_ is the parent window handle for a dialog box and is of type HWND, cast to a **ULONG_PTR**.</span></span> <span data-ttu-id="df52c-116">值为零表示没有父窗口。</span><span class="sxs-lookup"><span data-stu-id="df52c-116">A value of zero indicates there is no parent window.</span></span> 
    
 <span data-ttu-id="df52c-117">_lpvmsg_</span><span class="sxs-lookup"><span data-stu-id="df52c-117">_lpvmsg_</span></span>
  
> <span data-ttu-id="df52c-118">[in]指向邮件Windows指针。</span><span class="sxs-lookup"><span data-stu-id="df52c-118">[in] Pointer to a Windows message.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="df52c-119">返回值</span><span class="sxs-lookup"><span data-stu-id="df52c-119">Return value</span></span>

<span data-ttu-id="df52c-120">如果具有 **ACCELERATEABSDI** 原型的函数处理消息，则返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="df52c-120">A function with the **ACCELERATEABSDI** prototype returns TRUE if it handles the message.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="df52c-121">备注</span><span class="sxs-lookup"><span data-stu-id="df52c-121">Remarks</span></span>

<span data-ttu-id="df52c-122">基于 **ACCELERATEABSDI** 原型的函数仅用于无模式对话框，即，只有当客户端应用程序在 [ADRPARM](adrparm.md)结构的 _ulFlags_ 成员中设置了 DIALOG_SDI 标志时。</span><span class="sxs-lookup"><span data-stu-id="df52c-122">A function based on the **ACCELERATEABSDI** prototype is used only with a modeless dialog, that is, only if the client application has set the DIALOG_SDI flag in the  _ulFlags_ member of the [ADRPARM](adrparm.md) structure.</span></span> 
  
<span data-ttu-id="df52c-123">无模式对话框共享客户端应用程序的Windows消息循环，而不是有自己的循环。</span><span class="sxs-lookup"><span data-stu-id="df52c-123">A modeless dialog shares the client application's Windows message loop, instead of having its own loop.</span></span> <span data-ttu-id="df52c-124">应用程序控制消息循环，它不知道对话框使用哪些加速键，因此它调用基于 **ACCELERATEABSDI** 的函数来测试加速键（如 Ctrl+P）并针对打印操作。</span><span class="sxs-lookup"><span data-stu-id="df52c-124">The application, which controls the message loop, does not know what accelerator keys the dialog uses, so it calls an **ACCELERATEABSDI** based function to test for and act upon accelerator keys such as CTRL+P for printing.</span></span> 
  
<span data-ttu-id="df52c-125">当客户端使用 [IAddrBook：：Address](iaddrbook-address.md)方法调用无模式通讯簿对话框时，客户端的邮件循环将调用基于 **ACCELERATEABSDI** 的函数。</span><span class="sxs-lookup"><span data-stu-id="df52c-125">A client's message loop calls the **ACCELERATEABSDI** based function when the client invokes a modeless address book dialog box with the [IAddrBook::Address](iaddrbook-address.md) method.</span></span> <span data-ttu-id="df52c-126">当 MAPI 调用基于 [DISMISSMODELESS](dismissmodeless.md) 函数原型的函数时，此调用将终止。</span><span class="sxs-lookup"><span data-stu-id="df52c-126">This call is terminated when MAPI calls a function based on the [DISMISSMODELESS](dismissmodeless.md) function prototype.</span></span> 
  

