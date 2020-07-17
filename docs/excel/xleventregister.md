---
title: xlEventRegister
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: b98637d4-02e3-4dbd-8be5-6b46d32980c6
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 00c222efce6925c3f691eb2b799adf687c22082c
ms.sourcegitcommit: 41f2ee16badd6009bab642d68a61eaaccb91c3ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/17/2020
ms.locfileid: "45160277"
---
# <a name="xleventregister"></a><span data-ttu-id="42976-103">xlEventRegister</span><span class="sxs-lookup"><span data-stu-id="42976-103">xlEventRegister</span></span>

 <span data-ttu-id="42976-104">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="42976-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="42976-105">用于注册事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="42976-105">Used to register an event handler.</span></span> <span data-ttu-id="42976-106">在 Excel 2010 中引入。</span><span class="sxs-lookup"><span data-stu-id="42976-106">Introduced in Excel 2010.</span></span>
  
```vb
Excel12(xlEventRegister, LPXLOPER12 pxRes, 2, LPXLOPER12 pxProcedure, LPXLOPER12 pxEvent);
```

## <a name="parameters"></a><span data-ttu-id="42976-107">参数</span><span class="sxs-lookup"><span data-stu-id="42976-107">Parameters</span></span>

 <span data-ttu-id="42976-108">_pxProcedure_ （**xltypeStr**）</span><span class="sxs-lookup"><span data-stu-id="42976-108">_pxProcedure_ (**xltypeStr**)</span></span>
  
<span data-ttu-id="42976-109">在 DLL 代码中显示的事件处理程序函数的名称。</span><span class="sxs-lookup"><span data-stu-id="42976-109">The name of the event handler function as it appears in the DLL code.</span></span>
  
 <span data-ttu-id="42976-110">_pxEvent_ （**xltypeInt**）</span><span class="sxs-lookup"><span data-stu-id="42976-110">_pxEvent_ (**xltypeInt**)</span></span>
  
<span data-ttu-id="42976-111">由_pxProcedure_参数中指定的函数处理的事件。</span><span class="sxs-lookup"><span data-stu-id="42976-111">The event handled by the function designated in the  _pxProcedure_ parameter.</span></span> 
  
<span data-ttu-id="42976-112">从 Excel 2010 开始，Excel 支持以下事件：</span><span class="sxs-lookup"><span data-stu-id="42976-112">Starting in Excel 2010, Excel supports the following events:</span></span>
  
|<span data-ttu-id="42976-113">**Event**</span><span class="sxs-lookup"><span data-stu-id="42976-113">**Event**</span></span>|<span data-ttu-id="42976-114">**说明**</span><span class="sxs-lookup"><span data-stu-id="42976-114">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="42976-115">**xleventCalculationEnded**</span><span class="sxs-lookup"><span data-stu-id="42976-115">**xleventCalculationEnded**</span></span> <br/> |<span data-ttu-id="42976-116">在 Excel 完成计算时引发。</span><span class="sxs-lookup"><span data-stu-id="42976-116">Raised when Excel completes a calculation.</span></span> <span data-ttu-id="42976-117">在此事件发生之后，您可以释放在计算过程中分配的任何资源。</span><span class="sxs-lookup"><span data-stu-id="42976-117">You can free any resources allocated during the calculation after this event.</span></span>  <br/> |
|<span data-ttu-id="42976-118">**xleventCalculationCanceled**</span><span class="sxs-lookup"><span data-stu-id="42976-118">**xleventCalculationCanceled**</span></span> <br/> |<span data-ttu-id="42976-119">当用户中断计算时引发。</span><span class="sxs-lookup"><span data-stu-id="42976-119">Raised when the user interrupts the calculation.</span></span> <span data-ttu-id="42976-120">XLL 应停止任何异步活动。</span><span class="sxs-lookup"><span data-stu-id="42976-120">The XLL should stop any asynchronous activities.</span></span> <span data-ttu-id="42976-121">在此事件之后立即引发 CalculationEnded 事件。</span><span class="sxs-lookup"><span data-stu-id="42976-121">The CalculationEnded event is raised immediately following this event.</span></span>  <br/> |
   
## <a name="property-valuereturn-value"></a><span data-ttu-id="42976-122">属性值/返回值</span><span class="sxs-lookup"><span data-stu-id="42976-122">Property value/Return value</span></span>

<span data-ttu-id="42976-123">如果成功，pxRes （**xltypeInt**）的值 > 为0。</span><span class="sxs-lookup"><span data-stu-id="42976-123">If successful, pxRes (**xltypeInt**) has a value > 0.</span></span> <span data-ttu-id="42976-124">如果不成功，pxRes = = 0。</span><span class="sxs-lookup"><span data-stu-id="42976-124">If unsuccessful, pxRes ==0.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="42976-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42976-125">See also</span></span>



[<span data-ttu-id="42976-126">用户定义异步函数</span><span class="sxs-lookup"><span data-stu-id="42976-126">Asynchronous User-Defined Functions</span></span>](asynchronous-user-defined-functions.md)

