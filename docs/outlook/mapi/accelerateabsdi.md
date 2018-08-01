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
ms.openlocfilehash: b7d4d758f7031c55aa3a23b662ec8727ea1e0719
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774493"
---
# <a name="accelerateabsdi"></a><span data-ttu-id="8aa58-103">ACCELERATEABSDI</span><span class="sxs-lookup"><span data-stu-id="8aa58-103">ACCELERATEABSDI</span></span>
 
<span data-ttu-id="8aa58-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="8aa58-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8aa58-105">定义为无模式的通讯簿对话框中的过程加速键的回调函数。</span><span class="sxs-lookup"><span data-stu-id="8aa58-105">Defines a callback function to process accelerator keys in a modeless address book dialog box.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8aa58-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="8aa58-106">Header file:</span></span>  <br/> |<span data-ttu-id="8aa58-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="8aa58-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="8aa58-108">通过实施定义的函数：</span><span class="sxs-lookup"><span data-stu-id="8aa58-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="8aa58-109">MAPI</span><span class="sxs-lookup"><span data-stu-id="8aa58-109">MAPI</span></span>  <br/> |
|<span data-ttu-id="8aa58-110">定义的函数调用：</span><span class="sxs-lookup"><span data-stu-id="8aa58-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="8aa58-111">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="8aa58-111">Client applications</span></span>  <br/> |
   
```cpp
BOOL (STDMETHODCALLTYPE ACCELERATEABSDI)( 
  ULONG_PTR ulUIParam,
  LPVOID lpvmsg
);
```

## <a name="parameters"></a><span data-ttu-id="8aa58-112">参数</span><span class="sxs-lookup"><span data-stu-id="8aa58-112">Parameters</span></span>

 <span data-ttu-id="8aa58-113">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="8aa58-113">_ulUIParam_</span></span>
  
> <span data-ttu-id="8aa58-114">[in]用于将用户界面的信息传递给函数的特定于实现的值。</span><span class="sxs-lookup"><span data-stu-id="8aa58-114">[in] An implementation-specific value used for passing user interface information to a function.</span></span> <span data-ttu-id="8aa58-115">在 Microsoft Windows 上运行的应用程序， _ulUIParam_是对话框中的父窗口句柄，并且是类型 HWND，强制转换为**ULONG_PTR**。</span><span class="sxs-lookup"><span data-stu-id="8aa58-115">In applications running on Microsoft Windows,  _ulUIParam_ is the parent window handle for a dialog box and is of type HWND, cast to a **ULONG_PTR**.</span></span> <span data-ttu-id="8aa58-116">值为零表示没有父窗口。</span><span class="sxs-lookup"><span data-stu-id="8aa58-116">A value of zero indicates there is no parent window.</span></span> 
    
 <span data-ttu-id="8aa58-117">_lpvmsg_</span><span class="sxs-lookup"><span data-stu-id="8aa58-117">_lpvmsg_</span></span>
  
> <span data-ttu-id="8aa58-118">[in]为 Windows 的消息的指针。</span><span class="sxs-lookup"><span data-stu-id="8aa58-118">[in] Pointer to a Windows message.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="8aa58-119">返回值</span><span class="sxs-lookup"><span data-stu-id="8aa58-119">Return value</span></span>

<span data-ttu-id="8aa58-120">如果它处理的消息，带有**ACCELERATEABSDI**原型的函数将返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="8aa58-120">A function with the **ACCELERATEABSDI** prototype returns TRUE if it handles the message.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="8aa58-121">说明</span><span class="sxs-lookup"><span data-stu-id="8aa58-121">Remarks</span></span>

<span data-ttu-id="8aa58-122">基于**ACCELERATEABSDI**原型函数仅用于无模式对话框，即，只有当客户端应用程序已在[ADRPARM](adrparm.md)结构的_ulFlags_成员设置 DIALOG_SDI 标志。</span><span class="sxs-lookup"><span data-stu-id="8aa58-122">A function based on the **ACCELERATEABSDI** prototype is used only with a modeless dialog, that is, only if the client application has set the DIALOG_SDI flag in the  _ulFlags_ member of the [ADRPARM](adrparm.md) structure.</span></span> 
  
<span data-ttu-id="8aa58-123">无模式对话框共享客户端应用程序的 Windows 消息循环，而不是让其自己的循环。</span><span class="sxs-lookup"><span data-stu-id="8aa58-123">A modeless dialog shares the client application's Windows message loop, instead of having its own loop.</span></span> <span data-ttu-id="8aa58-124">该应用程序，用于控制消息循环，不知道哪些对话框用法，因此它将调用**ACCELERATEABSDI**将函数测试和处理基于快捷键 CTRL + P 如打印的加速键。</span><span class="sxs-lookup"><span data-stu-id="8aa58-124">The application, which controls the message loop, does not know what accelerator keys the dialog uses, so it calls an **ACCELERATEABSDI** based function to test for and act upon accelerator keys such as CTRL+P for printing.</span></span> 
  
<span data-ttu-id="8aa58-125">在客户端使用[IAddrBook::Address](iaddrbook-address.md)方法调用无模式的通讯簿对话框时，客户端的消息循环调用**ACCELERATEABSDI**基于函数。</span><span class="sxs-lookup"><span data-stu-id="8aa58-125">A client's message loop calls the **ACCELERATEABSDI** based function when the client invokes a modeless address book dialog box with the [IAddrBook::Address](iaddrbook-address.md) method.</span></span> <span data-ttu-id="8aa58-126">MAPI 调用基于[DISMISSMODELESS](dismissmodeless.md)函数原型函数时，将终止此呼叫。</span><span class="sxs-lookup"><span data-stu-id="8aa58-126">This call is terminated when MAPI calls a function based on the [DISMISSMODELESS](dismissmodeless.md) function prototype.</span></span> 
  

