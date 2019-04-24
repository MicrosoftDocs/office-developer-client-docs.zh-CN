---
title: SERVICEWIZARDDLGPROC
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.SERVICEWIZARDDLGPROC
api_type:
- COM
ms.assetid: 3e2d5190-e67a-470d-8177-0f0ba20c7b82
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e43a1d7c57668ba930b4c4af7194bd298971e6ba
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356411"
---
# <a name="servicewizarddlgproc"></a><span data-ttu-id="1019a-103">SERVICEWIZARDDLGPROC</span><span class="sxs-lookup"><span data-stu-id="1019a-103">SERVICEWIZARDDLGPROC</span></span>
 
<span data-ttu-id="1019a-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1019a-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1019a-105">定义由配置文件向导调用的回调函数, 以允许服务提供程序在显示提供程序的属性表或页面时对用户事件做出响应。</span><span class="sxs-lookup"><span data-stu-id="1019a-105">Defines a callback function invoked by the Profile Wizard to allow a service provider to react to user events when the provider's property sheets or pages are being shown.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1019a-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="1019a-106">Header file:</span></span>  <br/> |<span data-ttu-id="1019a-107">Mapiwz</span><span class="sxs-lookup"><span data-stu-id="1019a-107">Mapiwz.h</span></span>  <br/> |
|<span data-ttu-id="1019a-108">定义的函数实现者:</span><span class="sxs-lookup"><span data-stu-id="1019a-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="1019a-109">服务提供程序</span><span class="sxs-lookup"><span data-stu-id="1019a-109">Service providers</span></span>  <br/> |
|<span data-ttu-id="1019a-110">定义的函数调用者:</span><span class="sxs-lookup"><span data-stu-id="1019a-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="1019a-111">MAPI 配置文件向导</span><span class="sxs-lookup"><span data-stu-id="1019a-111">MAPI Profile Wizard</span></span>  <br/> |
   
```cpp
BOOL SERVICEWIZARDDLGPROC(
  HWND hDlg,
  UINT wMsgID,
  WPARAM wParam,
  LPARAM lParam
);
```

## <a name="parameters"></a><span data-ttu-id="1019a-112">参数</span><span class="sxs-lookup"><span data-stu-id="1019a-112">Parameters</span></span>

<span data-ttu-id="1019a-113">_hDlg_</span><span class="sxs-lookup"><span data-stu-id="1019a-113">_hDlg_</span></span>
  
> <span data-ttu-id="1019a-114">实时"配置文件向导" 对话框的窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="1019a-114">[in] Window handle to the Profile Wizard dialog box.</span></span> 
    
<span data-ttu-id="1019a-115">_wMsgID_</span><span class="sxs-lookup"><span data-stu-id="1019a-115">_wMsgID_</span></span>
  
> <span data-ttu-id="1019a-116">实时要处理的窗口消息。</span><span class="sxs-lookup"><span data-stu-id="1019a-116">[in] The window message to be processed.</span></span> <span data-ttu-id="1019a-117">除了模式对话框预期的常规窗口消息之外, 还可以接收以下消息:</span><span class="sxs-lookup"><span data-stu-id="1019a-117">In addition to the regular window messages expected by a modal dialog box, the following messages can be received:</span></span>
    
<span data-ttu-id="1019a-118">WM_CLOSE</span><span class="sxs-lookup"><span data-stu-id="1019a-118">WM_CLOSE</span></span> 
  
> <span data-ttu-id="1019a-119">配置文件向导已完成。</span><span class="sxs-lookup"><span data-stu-id="1019a-119">The Profile Wizard has completed.</span></span> <span data-ttu-id="1019a-120">服务提供程序应执行所有必要的清理操作, 如释放任何动态分配的内存。</span><span class="sxs-lookup"><span data-stu-id="1019a-120">The service provider should do all required cleanup such as deallocating any dynamically allocated memory.</span></span> 
    
<span data-ttu-id="1019a-121">WM_COMMAND</span><span class="sxs-lookup"><span data-stu-id="1019a-121">WM_COMMAND</span></span> 
  
> <span data-ttu-id="1019a-122">已选择某个提供程序的控件, 或单击了 "**下一步**" 或 "**后退**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="1019a-122">One of the provider's controls has been selected, or the **Next** or **Back** button has been clicked.</span></span> <span data-ttu-id="1019a-123">_wParam_参数中的值指示发生了哪些用户事件。</span><span class="sxs-lookup"><span data-stu-id="1019a-123">The value in the  _wParam_ parameter indicates which of these user events has occurred.</span></span> 
    
<span data-ttu-id="1019a-124">WM_INITDIALOG</span><span class="sxs-lookup"><span data-stu-id="1019a-124">WM_INITDIALOG</span></span> 
  
> <span data-ttu-id="1019a-125">用户已移动到另一个属性页, 该属性页必须为其初始化对话框。</span><span class="sxs-lookup"><span data-stu-id="1019a-125">The user has moved to another property page, for which the dialog box must be initialized.</span></span> <span data-ttu-id="1019a-126">提供程序应初始化 "配置文件向导" 已添加到对话框中的控件。</span><span class="sxs-lookup"><span data-stu-id="1019a-126">The provider should initialize the controls that the Profile Wizard has added to the dialog box.</span></span> 
    
<span data-ttu-id="1019a-127">WIZ_QUERYNUMPAGES</span><span class="sxs-lookup"><span data-stu-id="1019a-127">WIZ_QUERYNUMPAGES</span></span> 
  
> <span data-ttu-id="1019a-128">[! 注意] 配置文件向导提示输入提供程序需要显示的页面数。</span><span class="sxs-lookup"><span data-stu-id="1019a-128">The Profile Wizard is prompting for the number of pages that the provider needs to display.</span></span> <span data-ttu-id="1019a-129">提供程序应返回页面的数目, 而不是 TRUE 或 FALSE。</span><span class="sxs-lookup"><span data-stu-id="1019a-129">The provider should return the number of pages instead of TRUE or FALSE.</span></span> <span data-ttu-id="1019a-130">例如, 使用以下 return 语句指示应显示三个页面:</span><span class="sxs-lookup"><span data-stu-id="1019a-130">For example, use the following return statement to indicate that three pages should to be displayed:</span></span>
    
   ```cpp
return (BOOL)3;

   ```

<span data-ttu-id="1019a-131">_wParam_</span><span class="sxs-lookup"><span data-stu-id="1019a-131">_wParam_</span></span>
  
> <span data-ttu-id="1019a-132">实时与窗口消息相关联的32位参数。</span><span class="sxs-lookup"><span data-stu-id="1019a-132">[in] A 32-bit parameter associated with window messages.</span></span> <span data-ttu-id="1019a-133">可能的值取决于在_wMsgID_参数中指定的消息。</span><span class="sxs-lookup"><span data-stu-id="1019a-133">Possible values depend on the message specified in the  _wMsgID_ parameter.</span></span> <span data-ttu-id="1019a-134">除了针对模式对话框的常规窗口消息的预期值外, 还可以接收以下值:</span><span class="sxs-lookup"><span data-stu-id="1019a-134">In addition to the values expected with the regular window messages for a modal dialog box, the following values can be received:</span></span> 
    
<span data-ttu-id="1019a-135">WIZ_NEXT</span><span class="sxs-lookup"><span data-stu-id="1019a-135">WIZ_NEXT</span></span> 
  
> <span data-ttu-id="1019a-136">当_wMsgID_包含 WM_COMMAND 时, 用户单击了 "**下一步**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="1019a-136">When  _wMsgID_ contains WM_COMMAND, the user has clicked the **Next** button.</span></span> 
    
<span data-ttu-id="1019a-137">WIZ_PREV</span><span class="sxs-lookup"><span data-stu-id="1019a-137">WIZ_PREV</span></span> 
  
> <span data-ttu-id="1019a-138">当_wMsgID_包含 WM_COMMAND 时, 用户已单击 "**后退**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="1019a-138">When  _wMsgID_ contains WM_COMMAND, the user has clicked the **Back** button.</span></span> 
    
<span data-ttu-id="1019a-139">_lParam_</span><span class="sxs-lookup"><span data-stu-id="1019a-139">_lParam_</span></span>
  
> <span data-ttu-id="1019a-140">实时与窗口消息相关联的32位参数。</span><span class="sxs-lookup"><span data-stu-id="1019a-140">[in] A 32-bit parameter associated with window messages.</span></span> <span data-ttu-id="1019a-141">可能的值取决于在_wMsgID_参数中指定的消息。</span><span class="sxs-lookup"><span data-stu-id="1019a-141">Possible values depend on the message specified in the  _wMsgID_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="1019a-142">返回值</span><span class="sxs-lookup"><span data-stu-id="1019a-142">Return value</span></span>

<span data-ttu-id="1019a-143">基于**SERVICEWIZARDDLGPROC**的函数返回的值取决于收到的窗口消息。</span><span class="sxs-lookup"><span data-stu-id="1019a-143">The value returned by a **SERVICEWIZARDDLGPROC** based function is dependent on the window message received.</span></span> <span data-ttu-id="1019a-144">具体来说, 请注意 WIZ_QUERYNUMPAGES 消息的异常返回值。</span><span class="sxs-lookup"><span data-stu-id="1019a-144">Note in particular the exceptional return value for the WIZ_QUERYNUMPAGES message.</span></span> <span data-ttu-id="1019a-145">正常的返回值为:</span><span class="sxs-lookup"><span data-stu-id="1019a-145">The normal return values are:</span></span> 
  
<span data-ttu-id="1019a-146">TRUE</span><span class="sxs-lookup"><span data-stu-id="1019a-146">TRUE</span></span> 
  
> <span data-ttu-id="1019a-147">服务提供程序已处理收到的窗口消息。</span><span class="sxs-lookup"><span data-stu-id="1019a-147">The service provider has processed the received window message.</span></span> 
    
<span data-ttu-id="1019a-148">FALSE</span><span class="sxs-lookup"><span data-stu-id="1019a-148">FALSE</span></span> 
  
> <span data-ttu-id="1019a-149">服务提供程序尚未处理收到的窗口消息。</span><span class="sxs-lookup"><span data-stu-id="1019a-149">The service provider has not processed the received window message.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="1019a-150">注解</span><span class="sxs-lookup"><span data-stu-id="1019a-150">Remarks</span></span>

<span data-ttu-id="1019a-151">当用户从一个属性页移到另一个时, 提供程序负责隐藏旧页面的控件, 并显示下一页或上一页的控件。</span><span class="sxs-lookup"><span data-stu-id="1019a-151">When the user moves from one property page to another, the provider is responsible for hiding the old page's controls and showing the controls for the next or previous page.</span></span> <span data-ttu-id="1019a-152">当用户单击 "**下一步**" 按钮时, 将在_wParam_参数中使用 WM_COMMAND 消息和 WIZ_NEXT 调用基于**SERVICEWIZARDDLGPROC**的函数。</span><span class="sxs-lookup"><span data-stu-id="1019a-152">When the user clicks the **Next** button, the **SERVICEWIZARDDLGPROC** based function is called with the WM_COMMAND message and WIZ_NEXT in the  _wParam_ parameter.</span></span> <span data-ttu-id="1019a-153">以下步骤描述了用户单击 "**下一步**" 和第一个提供程序的配置页面呈现时间之间发生的情况。</span><span class="sxs-lookup"><span data-stu-id="1019a-153">The following steps describe what occurs between the time the user clicks **Next** and the time the first provider's configuration pages are rendered.</span></span> 
  
1. <span data-ttu-id="1019a-154">"配置文件向导" 将隐藏窗口上的所有控件。</span><span class="sxs-lookup"><span data-stu-id="1019a-154">The Profile Wizard hides any controls that are on the window.</span></span> 
    
2. <span data-ttu-id="1019a-155">"配置文件向导" 将提供程序的隐藏控件添加到页面中。</span><span class="sxs-lookup"><span data-stu-id="1019a-155">The Profile Wizard adds the provider's hidden controls to the page.</span></span> 
    
3. <span data-ttu-id="1019a-156">[! 注意] 配置文件向导调用**SERVICEWIZARDDLGPROC**, 发送 WM_INITDIALOG 消息, 以便提供程序可以初始化控件。</span><span class="sxs-lookup"><span data-stu-id="1019a-156">The Profile Wizard calls **SERVICEWIZARDDLGPROC**, sending the WM_INITDIALOG message, so that the provider can initialize the controls.</span></span> 
    
4. <span data-ttu-id="1019a-157">配置文件向导调用**SERVICEWIZARDDLGPROC**, 同时发送 WIZ_QUERYNUMPAGES 消息。</span><span class="sxs-lookup"><span data-stu-id="1019a-157">The Profile Wizard calls **SERVICEWIZARDDLGPROC**, sending the WIZ_QUERYNUMPAGES message.</span></span> <span data-ttu-id="1019a-158">提供程序返回要显示的页面的数量。</span><span class="sxs-lookup"><span data-stu-id="1019a-158">The provider returns the number of pages that are to be shown.</span></span> 
    
5. <span data-ttu-id="1019a-159">配置文件向导调用**SERVICEWIZARDDLGPROC**, 并将 WM_COMMAND 消息的_wParam_参数设置为 WIZ_NEXT 或 WIZ_PREV。</span><span class="sxs-lookup"><span data-stu-id="1019a-159">The Profile Wizard calls **SERVICEWIZARDDLGPROC**, sending the WM_COMMAND message with the  _wParam_ parameter set to either WIZ_NEXT or WIZ_PREV.</span></span> <span data-ttu-id="1019a-160">在这种情况下, 提供程序要么返回 FALSE {error}, 要么显示它的控件, 并返回 TRUE {success}。</span><span class="sxs-lookup"><span data-stu-id="1019a-160">At this point, the provider either returns FALSE {error} or reveals its controls and returns TRUE {success}.</span></span> <span data-ttu-id="1019a-161">如果配置文件向导在 ID_NEXT 中传递, 则显示提供程序的第一个页面。</span><span class="sxs-lookup"><span data-stu-id="1019a-161">If the Profile Wizard passes in ID_NEXT, the provider's first page is displayed.</span></span> <span data-ttu-id="1019a-162">如果传入 ID_PREV, 则显示最后一页。</span><span class="sxs-lookup"><span data-stu-id="1019a-162">If ID_PREV is passed in, the last page is displayed.</span></span> 
    
6. <span data-ttu-id="1019a-163">配置文件向导调用提供程序的**SERVICEWIZARDDLGPROC**函数, 并将_wParam_参数设置为 WIZ_NEXT 或 WIZ_PREV (具体取决于用户单击的按钮) 的 WM_COMMAND 消息。</span><span class="sxs-lookup"><span data-stu-id="1019a-163">The Profile Wizard calls the provider's **SERVICEWIZARDDLGPROC** function, sending the WM_COMMAND message with the  _wParam_ parameter set to either WIZ_NEXT or WIZ_PREV (depending on which button the user clicked).</span></span> <span data-ttu-id="1019a-164">提供程序负责显示或隐藏其控件, 并将其数据写入到传递给配置文件向导的**IMAPIProp**中, 以遍历其页面序列。</span><span class="sxs-lookup"><span data-stu-id="1019a-164">The provider is responsible for showing or hiding its controls and writing its data to the **IMAPIProp** passed to the Profile Wizard to step through its sequence of pages.</span></span> <span data-ttu-id="1019a-165">如果成功显示下一个或上一个页面, 提供程序应返回 TRUE; 如果下一个或上一个页面都不能显示, 则返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="1019a-165">The provider should return TRUE if the next or previous page was successfully shown, and FALSE if neither the next nor previous page could be shown.</span></span> <span data-ttu-id="1019a-166">提供程序需要知道何时在其页面序列之外进行跟踪, 并通过隐藏其控件并将其数据写入配置文件进行适当的响应。</span><span class="sxs-lookup"><span data-stu-id="1019a-166">The provider needs to be aware of when it is stepping outside of its sequence of pages, and respond appropriately by hiding its controls and writing its data to the profile.</span></span> 
    
7. <span data-ttu-id="1019a-167">如果用户步骤不在提供程序的页面范围之外, 则配置文件向导会从对话框中删除提供程序的隐藏控件, 并调用下一个提供程序, 如果是最后一个提供程序, 则将显示其下一个页面。</span><span class="sxs-lookup"><span data-stu-id="1019a-167">If the user steps outside the provider's range of pages, the Profile Wizard deletes the provider's hidden controls from the dialog box and calls the next provider or displays its next page if that was the last provider.</span></span> 
    

