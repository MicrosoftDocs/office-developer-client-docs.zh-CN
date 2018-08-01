---
title: IMAPIControlActivate
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIControl.Activate
api_type:
- COM
ms.assetid: 2b641030-2429-4217-a648-0a9f3d1a1b29
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fb6cd23acdb81af250e7e6dfe6facf7226850363
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775315"
---
# <a name="imapicontrolactivate"></a><span data-ttu-id="f646c-103">IMAPIControl::Activate</span><span class="sxs-lookup"><span data-stu-id="f646c-103">IMAPIControl::Activate</span></span>

  
  
<span data-ttu-id="f646c-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="f646c-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="f646c-105">执行显示一个对话框，或在客户端应用程序用户单击按钮控件时启动编程操作等任务。</span><span class="sxs-lookup"><span data-stu-id="f646c-105">Performs a task such as displaying a dialog box or starting a programmatic operation when a client application user clicks the button control.</span></span>
  
```cpp
HRESULT Activate(
  ULONG ulFlags,
  ULONG_PTR ulUIParam
);
```

## <a name="parameters"></a><span data-ttu-id="f646c-106">参数</span><span class="sxs-lookup"><span data-stu-id="f646c-106">Parameters</span></span>

 <span data-ttu-id="f646c-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="f646c-107">_ulFlags_</span></span>
  
> <span data-ttu-id="f646c-108">[in]保留;必须为零。</span><span class="sxs-lookup"><span data-stu-id="f646c-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="f646c-109">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="f646c-109">_ulUIParam_</span></span>
  
> <span data-ttu-id="f646c-110">[in]按钮控件将显示的对话框中的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="f646c-110">[in] A handle to the parent window of the dialog box on which the button control appears.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="f646c-111">返回值</span><span class="sxs-lookup"><span data-stu-id="f646c-111">Return value</span></span>

<span data-ttu-id="f646c-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="f646c-112">S_OK</span></span> 
  
> <span data-ttu-id="f646c-113">已成功激活按钮控件。</span><span class="sxs-lookup"><span data-stu-id="f646c-113">The button control was successfully activated.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="f646c-114">说明</span><span class="sxs-lookup"><span data-stu-id="f646c-114">Remarks</span></span>

<span data-ttu-id="f646c-115">**IMAPIControl::Activate**方法执行关注的用户单击按钮控件的任务。</span><span class="sxs-lookup"><span data-stu-id="f646c-115">The **IMAPIControl::Activate** method performs tasks following a user's click of the button control.</span></span> <span data-ttu-id="f646c-116">单击显示表中，处理的一部分发生后 MAPI 调用**激活**后第一个调用[IMAPIControl::GetState](imapicontrol-getstate.md)以确定能否启用按钮。</span><span class="sxs-lookup"><span data-stu-id="f646c-116">After the click occurs, as part of the processing of the display table, MAPI makes a call to **Activate** after first calling [IMAPIControl::GetState](imapicontrol-getstate.md) to determine whether the button is enabled.</span></span> 
  
<span data-ttu-id="f646c-117">有关如何实施**激活**和其他详细信息[IMAPIControl: IUnknown](imapicontroliunknown.md)方法，请参阅[控件对象实现](control-object-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="f646c-117">For more information about how to implement **Activate** and the other [IMAPIControl : IUnknown](imapicontroliunknown.md) methods, see [Control Object Implementation](control-object-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f646c-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f646c-118">See also</span></span>



[<span data-ttu-id="f646c-119">IMAPIControl::GetState</span><span class="sxs-lookup"><span data-stu-id="f646c-119">IMAPIControl::GetState</span></span>](imapicontrol-getstate.md)
  
[<span data-ttu-id="f646c-120">IMAPIControl : IUnknown</span><span class="sxs-lookup"><span data-stu-id="f646c-120">IMAPIControl : IUnknown</span></span>](imapicontroliunknown.md)

