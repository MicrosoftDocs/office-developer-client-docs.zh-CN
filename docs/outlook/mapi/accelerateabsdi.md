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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32322125"
---
# <a name="accelerateabsdi"></a><span data-ttu-id="daf80-103">ACCELERATEABSDI</span><span class="sxs-lookup"><span data-stu-id="daf80-103">ACCELERATEABSDI</span></span>
 
<span data-ttu-id="daf80-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="daf80-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="daf80-105">定义用于在无模式通讯簿对话框中处理加速键的回调函数。</span><span class="sxs-lookup"><span data-stu-id="daf80-105">Defines a callback function to process accelerator keys in a modeless address book dialog box.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="daf80-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="daf80-106">Header file:</span></span>  <br/> |<span data-ttu-id="daf80-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="daf80-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="daf80-108">定义的函数实现者:</span><span class="sxs-lookup"><span data-stu-id="daf80-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="daf80-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="daf80-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="daf80-110">定义的函数调用者:</span><span class="sxs-lookup"><span data-stu-id="daf80-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="daf80-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="daf80-111">Client applications</span></span>  <br/> |
   
```cpp
BOOL (STDMETHODCALLTYPE ACCELERATEABSDI)( 
  ULONG_PTR ulUIParam,
  LPVOID lpvmsg
);
```

## <a name="parameters"></a><span data-ttu-id="daf80-112">参数</span><span class="sxs-lookup"><span data-stu-id="daf80-112">Parameters</span></span>

 <span data-ttu-id="daf80-113">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="daf80-113">_ulUIParam_</span></span>
  
> <span data-ttu-id="daf80-114">实时用于将用户界面信息传递给函数的特定于实现的值。</span><span class="sxs-lookup"><span data-stu-id="daf80-114">[in] An implementation-specific value used for passing user interface information to a function.</span></span> <span data-ttu-id="daf80-115">在 Microsoft Windows 上运行的应用程序中, _ulUIParam_是对话框的父窗口句柄, 其类型为 HWND, 转换为**ULONG_PTR**。</span><span class="sxs-lookup"><span data-stu-id="daf80-115">In applications running on Microsoft Windows,  _ulUIParam_ is the parent window handle for a dialog box and is of type HWND, cast to a **ULONG_PTR**.</span></span> <span data-ttu-id="daf80-116">如果值为零, 则表示没有父窗口。</span><span class="sxs-lookup"><span data-stu-id="daf80-116">A value of zero indicates there is no parent window.</span></span> 
    
 <span data-ttu-id="daf80-117">_lpvmsg_</span><span class="sxs-lookup"><span data-stu-id="daf80-117">_lpvmsg_</span></span>
  
> <span data-ttu-id="daf80-118">实时指向 Windows 消息的指针。</span><span class="sxs-lookup"><span data-stu-id="daf80-118">[in] Pointer to a Windows message.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="daf80-119">返回值</span><span class="sxs-lookup"><span data-stu-id="daf80-119">Return value</span></span>

<span data-ttu-id="daf80-120">带有**ACCELERATEABSDI**原型的函数将返回 TRUE (如果它处理邮件)。</span><span class="sxs-lookup"><span data-stu-id="daf80-120">A function with the **ACCELERATEABSDI** prototype returns TRUE if it handles the message.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="daf80-121">注解</span><span class="sxs-lookup"><span data-stu-id="daf80-121">Remarks</span></span>

<span data-ttu-id="daf80-122">基于**ACCELERATEABSDI**原型的函数仅用于无模式对话框, 即, 仅当客户端应用程序已在[ADRPARM](adrparm.md)结构的_ulFlags_成员中设置了 DIALOG_SDI 标志时。</span><span class="sxs-lookup"><span data-stu-id="daf80-122">A function based on the **ACCELERATEABSDI** prototype is used only with a modeless dialog, that is, only if the client application has set the DIALOG_SDI flag in the  _ulFlags_ member of the [ADRPARM](adrparm.md) structure.</span></span> 
  
<span data-ttu-id="daf80-123">无模式对话框共享客户端应用程序的 Windows 消息循环, 而不是拥有自己的循环。</span><span class="sxs-lookup"><span data-stu-id="daf80-123">A modeless dialog shares the client application's Windows message loop, instead of having its own loop.</span></span> <span data-ttu-id="daf80-124">控制消息循环的应用程序不知道对话框使用的快捷键, 因此它调用基于**ACCELERATEABSDI**的函数来测试加速器键 (如 CTRL + P) 以进行打印, 并对其进行操作。</span><span class="sxs-lookup"><span data-stu-id="daf80-124">The application, which controls the message loop, does not know what accelerator keys the dialog uses, so it calls an **ACCELERATEABSDI** based function to test for and act upon accelerator keys such as CTRL+P for printing.</span></span> 
  
<span data-ttu-id="daf80-125">当客户端使用[IAddrBook:: address](iaddrbook-address.md)方法调用无模式通讯簿对话框时, 客户端的消息循环会调用基于**ACCELERATEABSDI**的函数。</span><span class="sxs-lookup"><span data-stu-id="daf80-125">A client's message loop calls the **ACCELERATEABSDI** based function when the client invokes a modeless address book dialog box with the [IAddrBook::Address](iaddrbook-address.md) method.</span></span> <span data-ttu-id="daf80-126">当 MAPI 调用基于[DISMISSMODELESS](dismissmodeless.md)函数原型的函数时, 将终止此调用。</span><span class="sxs-lookup"><span data-stu-id="daf80-126">This call is terminated when MAPI calls a function based on the [DISMISSMODELESS](dismissmodeless.md) function prototype.</span></span> 
  

