---
title: DISMISSMODELESS
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.DISMISSMODELESS
api_type:
- COM
ms.assetid: ef93ef3d-c159-40ae-9b8d-0af8a0567565
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: dd962515a85cb6a4b8661a0fd5294cea55cd6e96
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32339772"
---
# <a name="dismissmodeless"></a><span data-ttu-id="62e2f-103">DISMISSMODELESS</span><span class="sxs-lookup"><span data-stu-id="62e2f-103">DISMISSMODELESS</span></span>

  
  
<span data-ttu-id="62e2f-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="62e2f-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="62e2f-105">定义在其消除无模式通讯簿对话框时 MAPI 调用的回调函数。</span><span class="sxs-lookup"><span data-stu-id="62e2f-105">Defines a callback function that MAPI calls when it has dismissed a modeless address book dialog box.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="62e2f-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="62e2f-106">Header file:</span></span>  <br/> |<span data-ttu-id="62e2f-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="62e2f-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="62e2f-108">定义的函数实现者:</span><span class="sxs-lookup"><span data-stu-id="62e2f-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="62e2f-109">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="62e2f-109">Client applications</span></span>  <br/> |
|<span data-ttu-id="62e2f-110">定义的函数调用者:</span><span class="sxs-lookup"><span data-stu-id="62e2f-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="62e2f-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="62e2f-111">MAPI</span></span>  <br/> |
   
```cpp
void (STDMETHODCALLTYPE DISMISSMODELESS)(
  ULONG_PTR ulUIParam,
  LPVOID lpvContext
);
```

## <a name="parameters"></a><span data-ttu-id="62e2f-112">参数</span><span class="sxs-lookup"><span data-stu-id="62e2f-112">Parameters</span></span>

 <span data-ttu-id="62e2f-113">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="62e2f-113">_ulUIParam_</span></span>
  
> <span data-ttu-id="62e2f-114">实时一个特定于实现的值, 通常用于将用户界面信息传递给函数。</span><span class="sxs-lookup"><span data-stu-id="62e2f-114">[in] An implementation-specific value typically used for passing user interface information to a function.</span></span> <span data-ttu-id="62e2f-115">例如, 在 Microsoft Windows 中, 此参数是对话框的父窗口句柄, 其类型为 HWND, 转换为**ULONG_PTR**。</span><span class="sxs-lookup"><span data-stu-id="62e2f-115">For example, in Microsoft Windows this parameter is the parent window handle for the dialog box and is of type HWND, cast to a **ULONG_PTR**.</span></span> <span data-ttu-id="62e2f-116">如果值为零, 则表示没有父窗口。</span><span class="sxs-lookup"><span data-stu-id="62e2f-116">A value of zero indicates there is no parent window.</span></span> 
    
 <span data-ttu-id="62e2f-117">_lpvContext_</span><span class="sxs-lookup"><span data-stu-id="62e2f-117">_lpvContext_</span></span>
  
> <span data-ttu-id="62e2f-118">实时指向在 MAPI 调用回调函数时传递给该函数的任意值的指针。</span><span class="sxs-lookup"><span data-stu-id="62e2f-118">[in] Pointer to an arbitrary value passed to the callback function when MAPI calls it.</span></span> <span data-ttu-id="62e2f-119">此值可以表示对客户端应用程序的重要性的地址。</span><span class="sxs-lookup"><span data-stu-id="62e2f-119">This value can represent an address of significance to the client application.</span></span> <span data-ttu-id="62e2f-120">通常, 对于 c + + 代码, _lpvContext_是指向 c + + 对象实例的地址的指针。</span><span class="sxs-lookup"><span data-stu-id="62e2f-120">Typically, for C++ code,  _lpvContext_ is a pointer to the address of a C++ object instance.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="62e2f-121">返回值</span><span class="sxs-lookup"><span data-stu-id="62e2f-121">Return value</span></span>

<span data-ttu-id="62e2f-122">无</span><span class="sxs-lookup"><span data-stu-id="62e2f-122">None</span></span>
  
## <a name="remarks"></a><span data-ttu-id="62e2f-123">注解</span><span class="sxs-lookup"><span data-stu-id="62e2f-123">Remarks</span></span>

<span data-ttu-id="62e2f-124">当客户端应用程序调用无模式通讯簿对话框时, 它将在其 Windows 消息循环中包含对基于[ACCELERATEABSDI](accelerateabsdi.md)原型 (检查和处理加速键) 的函数的调用。</span><span class="sxs-lookup"><span data-stu-id="62e2f-124">When the client application invokes a modeless address book dialog box, it includes in its Windows message loop a call to a function based on the [ACCELERATEABSDI](accelerateabsdi.md) prototype, which checks for and processes accelerator keys.</span></span> <span data-ttu-id="62e2f-125">当对话框关闭时, MAPI 将调用基于**DISMISSMODELESS**的函数, 以便客户端应用程序将停止调用基于**ACCELERATEABSDI**的函数。</span><span class="sxs-lookup"><span data-stu-id="62e2f-125">When the dialog box is closed, MAPI calls the **DISMISSMODELESS** based function so that the client application will stop calling the **ACCELERATEABSDI** based function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="62e2f-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="62e2f-126">See also</span></span>



[<span data-ttu-id="62e2f-127">ADRPARM</span><span class="sxs-lookup"><span data-stu-id="62e2f-127">ADRPARM</span></span>](adrparm.md)

