---
title: 处理事件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: b67fcb83-a0e2-4349-88f5-bcc181306eac
description: 适用于：Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: c989bc39c22f4e566c18feb4fdeaa8582c5525f2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33438265"
---
# <a name="handling-events"></a><span data-ttu-id="9233f-103">处理事件</span><span class="sxs-lookup"><span data-stu-id="9233f-103">Handling Events</span></span>

 <span data-ttu-id="9233f-104">**适用于**：Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="9233f-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="9233f-105">从 Excel 2010 开始，XLL 可以接收旨在管理异步函数生命周期的事件。</span><span class="sxs-lookup"><span data-stu-id="9233f-105">Starting in Excel 2010, XLLs can receive events designed to manage the asynchronous function life cycle.</span></span> <span data-ttu-id="9233f-106">事件如下所示：</span><span class="sxs-lookup"><span data-stu-id="9233f-106">The events are as follows:</span></span>
  
- <span data-ttu-id="9233f-107">**CalculationEnded：** 在计算Excel时引发。</span><span class="sxs-lookup"><span data-stu-id="9233f-107">**CalculationEnded**: Raised when Excel is finished calculating.</span></span> <span data-ttu-id="9233f-108">在此事件之后，可以释放在计算期间分配的资源。</span><span class="sxs-lookup"><span data-stu-id="9233f-108">After this event, you can free resources allocated during the calculation.</span></span>
    
- <span data-ttu-id="9233f-109">**CalculationCanceled**：在用户中断计算时引发。</span><span class="sxs-lookup"><span data-stu-id="9233f-109">**CalculationCanceled**: Raised when the user interrupts the calculation.</span></span> <span data-ttu-id="9233f-110">XLL 将停止任何异步活动。</span><span class="sxs-lookup"><span data-stu-id="9233f-110">The XLL stops any asynchronous activities.</span></span> <span data-ttu-id="9233f-111">紧接此事件后， **将引发 CalculationEnded** 事件。</span><span class="sxs-lookup"><span data-stu-id="9233f-111">Immediately following this event, the **CalculationEnded** event is raised.</span></span> 
    
<span data-ttu-id="9233f-112">为了处理这些事件，XLL 使用 C API 函数 [xlEventRegister](xleventregister.md)。</span><span class="sxs-lookup"><span data-stu-id="9233f-112">To handle these events, the XLL uses the C API function [xlEventRegister](xleventregister.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="9233f-113">在编程重新计算过程中不会引发 **CalculationEnded** 和 **CalculationCanceled。**</span><span class="sxs-lookup"><span data-stu-id="9233f-113">**CalculationEnded** and **CalculationCanceled** are not raised during programmatic recalculation.</span></span> 
  

