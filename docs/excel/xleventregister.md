---
title: xlEventRegister
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b98637d4-02e3-4dbd-8be5-6b46d32980c6
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: d837d87c479f70f0184a7cf1612dea5ab8c99e6d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773844"
---
# <a name="xleventregister"></a><span data-ttu-id="52d92-103">xlEventRegister</span><span class="sxs-lookup"><span data-stu-id="52d92-103">xlEventRegister</span></span>

 <span data-ttu-id="52d92-104">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="52d92-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="52d92-105">用于注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="52d92-105">Used to register an event handler.</span></span> <span data-ttu-id="52d92-106">在 Excel 2010 中引入。</span><span class="sxs-lookup"><span data-stu-id="52d92-106">Introduced in Excel 2010.</span></span>
  
```vb
Excel12(xlEventRegister, LPXLOPER12 pxRes, 2, LPXLOPER12 pxProcedure, LPXLOPER12 pxEvent);
```

## <a name="parameters"></a><span data-ttu-id="52d92-107">参数</span><span class="sxs-lookup"><span data-stu-id="52d92-107">Parameters</span></span>

 <span data-ttu-id="52d92-108">_pxProcedure_(**xltypeStr**)</span><span class="sxs-lookup"><span data-stu-id="52d92-108">_pxProcedure_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="52d92-109">在 DLL 的代码中显示它的事件处理程序函数的名称。</span><span class="sxs-lookup"><span data-stu-id="52d92-109">The name of the event handler function as it appears in the DLL code.</span></span>
  
 <span data-ttu-id="52d92-110">_pxEvent_(**xltypeInt**)</span><span class="sxs-lookup"><span data-stu-id="52d92-110">_pxEvent_ (**xltypeInt**)</span></span>
  
<span data-ttu-id="52d92-111">通过_pxProcedure_参数中指定的函数处理的事件。</span><span class="sxs-lookup"><span data-stu-id="52d92-111">The event handled by the function designated in the  _pxProcedure_ parameter.</span></span> 
  
<span data-ttu-id="52d92-112">Excel 启动 Excel 2010 中支持以下事件：</span><span class="sxs-lookup"><span data-stu-id="52d92-112">Starting in Excel 2010, Excel supports the following events:</span></span>
  
|<span data-ttu-id="52d92-113">"事件"</span><span class="sxs-lookup"><span data-stu-id="52d92-113">**Event**</span></span>|<span data-ttu-id="52d92-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="52d92-114">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="52d92-115">**xleventCalculationEnded**</span><span class="sxs-lookup"><span data-stu-id="52d92-115">**xleventCalculationEnded**</span></span> <br/> |<span data-ttu-id="52d92-116">Excel 完成计算时引发。</span><span class="sxs-lookup"><span data-stu-id="52d92-116">Raised when Excel completes a calculation.</span></span> <span data-ttu-id="52d92-117">您可以释放分配此事件后在计算过程中的任何资源。</span><span class="sxs-lookup"><span data-stu-id="52d92-117">You can free any resources allocated during the calculation after this event.</span></span>  <br/> |
|<span data-ttu-id="52d92-118">**xleventCalculationCanceled**</span><span class="sxs-lookup"><span data-stu-id="52d92-118">**xleventCalculationCanceled**</span></span> <br/> |<span data-ttu-id="52d92-119">当用户中断计算时引发。</span><span class="sxs-lookup"><span data-stu-id="52d92-119">Raised when the user interrupts the calculation.</span></span> <span data-ttu-id="52d92-120">XLL 应停止任何异步活动。</span><span class="sxs-lookup"><span data-stu-id="52d92-120">The XLL should stop any asynchronous activities.</span></span> <span data-ttu-id="52d92-121">紧跟此事件时引发 CalculationEnded 事件。</span><span class="sxs-lookup"><span data-stu-id="52d92-121">The CalculationEnded event is raised immediately following this event.</span></span>  <br/> |
   
## <a name="property-valuereturn-value"></a><span data-ttu-id="52d92-122">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="52d92-122">Property value/Return value</span></span>

<span data-ttu-id="52d92-123">如果成功，则返回**TRUE** (**xltypeBool**)。</span><span class="sxs-lookup"><span data-stu-id="52d92-123">If successful, returns **TRUE** (**xltypeBool**).</span></span> <span data-ttu-id="52d92-124">如果不成功，则返回**FALSE**。</span><span class="sxs-lookup"><span data-stu-id="52d92-124">If unsuccessful, returns **FALSE**.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="52d92-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="52d92-125">See also</span></span>



[<span data-ttu-id="52d92-126">用户定义的异步函数</span><span class="sxs-lookup"><span data-stu-id="52d92-126">Asynchronous User-Defined Functions</span></span>](asynchronous-user-defined-functions.md)

