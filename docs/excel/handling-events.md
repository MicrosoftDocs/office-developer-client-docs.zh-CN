---
title: 处理事件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: b67fcb83-a0e2-4349-88f5-bcc181306eac
description: ���÷�Χ�� Excel 2013?| Office 2013?| Visual Studio
ms.openlocfilehash: c5508df8466932b6fb5c7e04164aa00a5ea31a8d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773746"
---
# <a name="handling-events"></a><span data-ttu-id="857f3-103">处理事件</span><span class="sxs-lookup"><span data-stu-id="857f3-103">Handling Events</span></span>

 <span data-ttu-id="857f3-104">**适用于**： Excel 2013 |Office 2013 |Visual Studio</span><span class="sxs-lookup"><span data-stu-id="857f3-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="857f3-105">启动在 Excel 2010 xll 可以接收旨在管理的异步函数生命周期的事件。</span><span class="sxs-lookup"><span data-stu-id="857f3-105">Starting in Excel 2010, XLLs can receive events designed to manage the asynchronous function life cycle.</span></span> <span data-ttu-id="857f3-106">事件如下所示：</span><span class="sxs-lookup"><span data-stu-id="857f3-106">The events are as follows:</span></span>
  
- <span data-ttu-id="857f3-107">**CalculationEnded**： 引发完成 Excel 计算。</span><span class="sxs-lookup"><span data-stu-id="857f3-107">**CalculationEnded**: Raised when Excel is finished calculating.</span></span> <span data-ttu-id="857f3-108">此事件之后，您可以释放计算过程中分配资源。</span><span class="sxs-lookup"><span data-stu-id="857f3-108">After this event, you can free resources allocated during the calculation.</span></span>
    
- <span data-ttu-id="857f3-109">**CalculationCanceled**： 用户中断计算时引发。</span><span class="sxs-lookup"><span data-stu-id="857f3-109">**CalculationCanceled**: Raised when the user interrupts the calculation.</span></span> <span data-ttu-id="857f3-110">XLL 停止任何异步活动。</span><span class="sxs-lookup"><span data-stu-id="857f3-110">The XLL stops any asynchronous activities.</span></span> <span data-ttu-id="857f3-111">紧接此事件， **CalculationEnded**引发该事件。</span><span class="sxs-lookup"><span data-stu-id="857f3-111">Immediately following this event, the **CalculationEnded** event is raised.</span></span> 
    
<span data-ttu-id="857f3-112">若要处理这些事件，XLL，请使用 C API 函数[xlEventRegister](xleventregister.md)。</span><span class="sxs-lookup"><span data-stu-id="857f3-112">To handle these events, the XLL uses the C API function [xlEventRegister](xleventregister.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="857f3-113">**CalculationEnded**和**CalculationCanceled**不会引发编程重新计算过程中。</span><span class="sxs-lookup"><span data-stu-id="857f3-113">**CalculationEnded** and **CalculationCanceled** are not raised during programmatic recalculation.</span></span> 
  

