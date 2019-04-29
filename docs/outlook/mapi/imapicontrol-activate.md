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
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d3b47e423daf428c67761d13deef1ae0858c91c0
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33418013"
---
# <a name="imapicontrolactivate"></a><span data-ttu-id="bafd3-103">IMAPIControl::Activate</span><span class="sxs-lookup"><span data-stu-id="bafd3-103">IMAPIControl::Activate</span></span>

  
  
<span data-ttu-id="bafd3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bafd3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bafd3-105">在客户端应用程序用户单击 "按钮" 控件时执行一种任务, 如显示对话框或启动编程操作。</span><span class="sxs-lookup"><span data-stu-id="bafd3-105">Performs a task such as displaying a dialog box or starting a programmatic operation when a client application user clicks the button control.</span></span>
  
```cpp
HRESULT Activate(
  ULONG ulFlags,
  ULONG_PTR ulUIParam
);
```

## <a name="parameters"></a><span data-ttu-id="bafd3-106">参数</span><span class="sxs-lookup"><span data-stu-id="bafd3-106">Parameters</span></span>

 <span data-ttu-id="bafd3-107">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="bafd3-107">_ulFlags_</span></span>
  
> <span data-ttu-id="bafd3-108">实时保留必须为零。</span><span class="sxs-lookup"><span data-stu-id="bafd3-108">[in] Reserved; must be zero.</span></span>
    
 <span data-ttu-id="bafd3-109">_ulUIParam_</span><span class="sxs-lookup"><span data-stu-id="bafd3-109">_ulUIParam_</span></span>
  
> <span data-ttu-id="bafd3-110">实时显示按钮控件的对话框的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="bafd3-110">[in] A handle to the parent window of the dialog box on which the button control appears.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="bafd3-111">返回值</span><span class="sxs-lookup"><span data-stu-id="bafd3-111">Return value</span></span>

<span data-ttu-id="bafd3-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="bafd3-112">S_OK</span></span> 
  
> <span data-ttu-id="bafd3-113">按钮控件已成功激活。</span><span class="sxs-lookup"><span data-stu-id="bafd3-113">The button control was successfully activated.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="bafd3-114">说明</span><span class="sxs-lookup"><span data-stu-id="bafd3-114">Remarks</span></span>

<span data-ttu-id="bafd3-115">**IMAPIControl:: Activate**方法在用户单击按钮控件后执行任务。</span><span class="sxs-lookup"><span data-stu-id="bafd3-115">The **IMAPIControl::Activate** method performs tasks following a user's click of the button control.</span></span> <span data-ttu-id="bafd3-116">在显示表的处理过程中, MAPI 在第一次调用[IMAPIControl:: GetState](imapicontrol-getstate.md)以确定按钮是否已启用之后, 会调用**激活**。</span><span class="sxs-lookup"><span data-stu-id="bafd3-116">After the click occurs, as part of the processing of the display table, MAPI makes a call to **Activate** after first calling [IMAPIControl::GetState](imapicontrol-getstate.md) to determine whether the button is enabled.</span></span> 
  
<span data-ttu-id="bafd3-117">有关如何实现**Activate**和其他[IMAPIControl: IUnknown](imapicontroliunknown.md)方法的详细信息, 请参阅[Control Object 实现](control-object-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="bafd3-117">For more information about how to implement **Activate** and the other [IMAPIControl : IUnknown](imapicontroliunknown.md) methods, see [Control Object Implementation](control-object-implementation.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bafd3-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bafd3-118">See also</span></span>



[<span data-ttu-id="bafd3-119">IMAPIControl::GetState</span><span class="sxs-lookup"><span data-stu-id="bafd3-119">IMAPIControl::GetState</span></span>](imapicontrol-getstate.md)
  
[<span data-ttu-id="bafd3-120">IMAPIControl : IUnknown</span><span class="sxs-lookup"><span data-stu-id="bafd3-120">IMAPIControl : IUnknown</span></span>](imapicontroliunknown.md)

