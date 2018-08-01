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
ms.openlocfilehash: dc830665f425b747d2fdb05641dc037a2e84f695
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774810"
---
# <a name="dismissmodeless"></a><span data-ttu-id="b73ca-103">DISMISSMODELESS</span><span class="sxs-lookup"><span data-stu-id="b73ca-103">DISMISSMODELESS</span></span>

  
  
<span data-ttu-id="b73ca-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="b73ca-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="b73ca-105">定义一个时它解除了无模式的通讯簿对话框 MAPI 调用的回调函数。</span><span class="sxs-lookup"><span data-stu-id="b73ca-105">Defines a callback function that MAPI calls when it has dismissed a modeless address book dialog box.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b73ca-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="b73ca-106">Header file:</span></span>  <br/> |<span data-ttu-id="b73ca-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="b73ca-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="b73ca-108">通过实施定义的函数：</span><span class="sxs-lookup"><span data-stu-id="b73ca-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="b73ca-109">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="b73ca-109">Client applications</span></span>  <br/> |
|<span data-ttu-id="b73ca-110">定义的函数调用：</span><span class="sxs-lookup"><span data-stu-id="b73ca-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="b73ca-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="b73ca-111">MAPI</span></span>  <br/> |
   
```cpp
void (STDMETHODCALLTYPE DISMISSMODELESS)(
  ULONG_PTR ulUIParam,
  LPVOID lpvContext
);
```

## <a name="parameters"></a><span data-ttu-id="b73ca-112">参数</span><span class="sxs-lookup"><span data-stu-id="b73ca-112">Parameters</span></span>

 <span data-ttu-id="b73ca-113">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="b73ca-113">_ulUIParam_</span></span>
  
> <span data-ttu-id="b73ca-114">[in]通常用于将用户界面的信息传递给函数的特定于实现的值。</span><span class="sxs-lookup"><span data-stu-id="b73ca-114">[in] An implementation-specific value typically used for passing user interface information to a function.</span></span> <span data-ttu-id="b73ca-115">例如，Microsoft Windows 中此参数是对话框中的父窗口句柄的类型 HWND，强制转换为**ULONG_PTR**。</span><span class="sxs-lookup"><span data-stu-id="b73ca-115">For example, in Microsoft Windows this parameter is the parent window handle for the dialog box and is of type HWND, cast to a **ULONG_PTR**.</span></span> <span data-ttu-id="b73ca-116">值为零表示没有父窗口。</span><span class="sxs-lookup"><span data-stu-id="b73ca-116">A value of zero indicates there is no parent window.</span></span> 
    
 <span data-ttu-id="b73ca-117">_lpvContext_</span><span class="sxs-lookup"><span data-stu-id="b73ca-117">_lpvContext_</span></span>
  
> <span data-ttu-id="b73ca-118">[in]MAPI 调用它时，为任意值的指针传递给回调函数。</span><span class="sxs-lookup"><span data-stu-id="b73ca-118">[in] Pointer to an arbitrary value passed to the callback function when MAPI calls it.</span></span> <span data-ttu-id="b73ca-119">此值可表示的客户端应用程序的有效位倍数的地址。</span><span class="sxs-lookup"><span data-stu-id="b73ca-119">This value can represent an address of significance to the client application.</span></span> <span data-ttu-id="b73ca-120">通常，c + + 代码_lpvContext_是一个指向 c + + 对象实例的地址。</span><span class="sxs-lookup"><span data-stu-id="b73ca-120">Typically, for C++ code,  _lpvContext_ is a pointer to the address of a C++ object instance.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="b73ca-121">返回值</span><span class="sxs-lookup"><span data-stu-id="b73ca-121">Return value</span></span>

<span data-ttu-id="b73ca-122">无</span><span class="sxs-lookup"><span data-stu-id="b73ca-122">None</span></span>
  
## <a name="remarks"></a><span data-ttu-id="b73ca-123">说明</span><span class="sxs-lookup"><span data-stu-id="b73ca-123">Remarks</span></span>

<span data-ttu-id="b73ca-124">当客户端应用程序调用无模式的通讯簿对话框时，它在其 Windows 消息循环中包括对基于[ACCELERATEABSDI](accelerateabsdi.md)原型，其检查和处理快捷键函数的调用。</span><span class="sxs-lookup"><span data-stu-id="b73ca-124">When the client application invokes a modeless address book dialog box, it includes in its Windows message loop a call to a function based on the [ACCELERATEABSDI](accelerateabsdi.md) prototype, which checks for and processes accelerator keys.</span></span> <span data-ttu-id="b73ca-125">当关闭对话框时，MAPI 调用**DISMISSMODELESS**基于函数，以便客户端应用程序将停止调用**ACCELERATEABSDI**基于函数。</span><span class="sxs-lookup"><span data-stu-id="b73ca-125">When the dialog box is closed, MAPI calls the **DISMISSMODELESS** based function so that the client application will stop calling the **ACCELERATEABSDI** based function.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="b73ca-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b73ca-126">See also</span></span>



[<span data-ttu-id="b73ca-127">ADRPARM</span><span class="sxs-lookup"><span data-stu-id="b73ca-127">ADRPARM</span></span>](adrparm.md)

