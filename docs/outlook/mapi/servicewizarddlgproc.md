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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 649046aa48f293caa5bd71cc670481b5c205459a
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19778760"
---
# <a name="servicewizarddlgproc"></a><span data-ttu-id="96d6a-103">SERVICEWIZARDDLGPROC</span><span class="sxs-lookup"><span data-stu-id="96d6a-103">SERVICEWIZARDDLGPROC</span></span>
 
<span data-ttu-id="96d6a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="96d6a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="96d6a-105">定义由配置文件向导以允许服务提供程序响应用户事件提供程序的属性表或页面显示时调用的回调函数。</span><span class="sxs-lookup"><span data-stu-id="96d6a-105">Defines a callback function invoked by the Profile Wizard to allow a service provider to react to user events when the provider's property sheets or pages are being shown.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="96d6a-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="96d6a-106">Header file:</span></span>  <br/> |<span data-ttu-id="96d6a-107">Mapiwz.h</span><span class="sxs-lookup"><span data-stu-id="96d6a-107">Mapiwz.h</span></span>  <br/> |
|<span data-ttu-id="96d6a-108">通过实施定义的函数：</span><span class="sxs-lookup"><span data-stu-id="96d6a-108">Defined function implemented by:</span></span>  <br/> |<span data-ttu-id="96d6a-109">服务提供商</span><span class="sxs-lookup"><span data-stu-id="96d6a-109">Service providers</span></span>  <br/> |
|<span data-ttu-id="96d6a-110">定义的函数调用：</span><span class="sxs-lookup"><span data-stu-id="96d6a-110">Defined function called by:</span></span>  <br/> |<span data-ttu-id="96d6a-111">MAPI 配置文件向导</span><span class="sxs-lookup"><span data-stu-id="96d6a-111">MAPI Profile Wizard</span></span>  <br/> |
   
```cpp
BOOL SERVICEWIZARDDLGPROC(
  HWND hDlg,
  UINT wMsgID,
  WPARAM wParam,
  LPARAM lParam
);
```

## <a name="parameters"></a><span data-ttu-id="96d6a-112">参数</span><span class="sxs-lookup"><span data-stu-id="96d6a-112">Parameters</span></span>

<span data-ttu-id="96d6a-113">_hDlg_</span><span class="sxs-lookup"><span data-stu-id="96d6a-113">_hDlg_</span></span>
  
> <span data-ttu-id="96d6a-114">[in]配置文件向导对话框窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="96d6a-114">[in] Window handle to the Profile Wizard dialog box.</span></span> 
    
<span data-ttu-id="96d6a-115">_wMsgID_</span><span class="sxs-lookup"><span data-stu-id="96d6a-115">_wMsgID_</span></span>
  
> <span data-ttu-id="96d6a-116">[in]要处理的窗口消息。</span><span class="sxs-lookup"><span data-stu-id="96d6a-116">[in] The window message to be processed.</span></span> <span data-ttu-id="96d6a-117">除了所需的一个模式对话框的正则窗口消息，就会收到以下消息：</span><span class="sxs-lookup"><span data-stu-id="96d6a-117">In addition to the regular window messages expected by a modal dialog box, the following messages can be received:</span></span>
    
<span data-ttu-id="96d6a-118">WM_CLOSE</span><span class="sxs-lookup"><span data-stu-id="96d6a-118">WM_CLOSE</span></span> 
  
> <span data-ttu-id="96d6a-119">配置文件向导已完成。</span><span class="sxs-lookup"><span data-stu-id="96d6a-119">The Profile Wizard has completed.</span></span> <span data-ttu-id="96d6a-120">服务提供商办所有所需的清理，如取消任何动态分配分配内存。</span><span class="sxs-lookup"><span data-stu-id="96d6a-120">The service provider should do all required cleanup such as deallocating any dynamically allocated memory.</span></span> 
    
<span data-ttu-id="96d6a-121">WM_COMMAND</span><span class="sxs-lookup"><span data-stu-id="96d6a-121">WM_COMMAND</span></span> 
  
> <span data-ttu-id="96d6a-122">一个提供程序的控件已被选中，或单击**下一步**或**返回**按钮。</span><span class="sxs-lookup"><span data-stu-id="96d6a-122">One of the provider's controls has been selected, or the **Next** or **Back** button has been clicked.</span></span> <span data-ttu-id="96d6a-123">_WParam_参数中的值指示其这些用户事件发生。</span><span class="sxs-lookup"><span data-stu-id="96d6a-123">The value in the  _wParam_ parameter indicates which of these user events has occurred.</span></span> 
    
<span data-ttu-id="96d6a-124">WM_INITDIALOG</span><span class="sxs-lookup"><span data-stu-id="96d6a-124">WM_INITDIALOG</span></span> 
  
> <span data-ttu-id="96d6a-125">用户已移动到另一个属性页上，必须为其初始化的对话框。</span><span class="sxs-lookup"><span data-stu-id="96d6a-125">The user has moved to another property page, for which the dialog box must be initialized.</span></span> <span data-ttu-id="96d6a-126">提供程序应初始化配置文件向导已添加到对话框中的控件。</span><span class="sxs-lookup"><span data-stu-id="96d6a-126">The provider should initialize the controls that the Profile Wizard has added to the dialog box.</span></span> 
    
<span data-ttu-id="96d6a-127">WIZ_QUERYNUMPAGES</span><span class="sxs-lookup"><span data-stu-id="96d6a-127">WIZ_QUERYNUMPAGES</span></span> 
  
> <span data-ttu-id="96d6a-128">配置文件向导为提示提供程序需要显示的页面的数量。</span><span class="sxs-lookup"><span data-stu-id="96d6a-128">The Profile Wizard is prompting for the number of pages that the provider needs to display.</span></span> <span data-ttu-id="96d6a-129">提供程序应返回的而不是 TRUE 或 FALSE 的页数。</span><span class="sxs-lookup"><span data-stu-id="96d6a-129">The provider should return the number of pages instead of TRUE or FALSE.</span></span> <span data-ttu-id="96d6a-130">例如，使用以下返回语句以指明应显示三个页面：</span><span class="sxs-lookup"><span data-stu-id="96d6a-130">For example, use the following return statement to indicate that three pages should to be displayed:</span></span>
    
   ```cpp
return (BOOL)3;

   ```

<span data-ttu-id="96d6a-131">_wParam_</span><span class="sxs-lookup"><span data-stu-id="96d6a-131">_wParam_</span></span>
  
> <span data-ttu-id="96d6a-132">[in]与窗口消息关联的 32 位参数。</span><span class="sxs-lookup"><span data-stu-id="96d6a-132">[in] A 32-bit parameter associated with window messages.</span></span> <span data-ttu-id="96d6a-133">可能的值取决于_wMsgID_参数中指定的消息。</span><span class="sxs-lookup"><span data-stu-id="96d6a-133">Possible values depend on the message specified in the  _wMsgID_ parameter.</span></span> <span data-ttu-id="96d6a-134">除了能够为一个模式对话框的正则窗口消息的值，就会收到以下值：</span><span class="sxs-lookup"><span data-stu-id="96d6a-134">In addition to the values expected with the regular window messages for a modal dialog box, the following values can be received:</span></span> 
    
<span data-ttu-id="96d6a-135">WIZ_NEXT</span><span class="sxs-lookup"><span data-stu-id="96d6a-135">WIZ_NEXT</span></span> 
  
> <span data-ttu-id="96d6a-136">当_wMsgID_包含 WM_COMMAND 时，用户单击**下一步**按钮。</span><span class="sxs-lookup"><span data-stu-id="96d6a-136">When  _wMsgID_ contains WM_COMMAND, the user has clicked the **Next** button.</span></span> 
    
<span data-ttu-id="96d6a-137">WIZ_PREV</span><span class="sxs-lookup"><span data-stu-id="96d6a-137">WIZ_PREV</span></span> 
  
> <span data-ttu-id="96d6a-138">当_wMsgID_包含 WM_COMMAND 时，用户单击**后退**按钮。</span><span class="sxs-lookup"><span data-stu-id="96d6a-138">When  _wMsgID_ contains WM_COMMAND, the user has clicked the **Back** button.</span></span> 
    
<span data-ttu-id="96d6a-139">_lParam_</span><span class="sxs-lookup"><span data-stu-id="96d6a-139">_lParam_</span></span>
  
> <span data-ttu-id="96d6a-140">[in]与窗口消息关联的 32 位参数。</span><span class="sxs-lookup"><span data-stu-id="96d6a-140">[in] A 32-bit parameter associated with window messages.</span></span> <span data-ttu-id="96d6a-141">可能的值取决于_wMsgID_参数中指定的消息。</span><span class="sxs-lookup"><span data-stu-id="96d6a-141">Possible values depend on the message specified in the  _wMsgID_ parameter.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="96d6a-142">返回值</span><span class="sxs-lookup"><span data-stu-id="96d6a-142">Return value</span></span>

<span data-ttu-id="96d6a-143">取决于所接收的窗口消息**SERVICEWIZARDDLGPROC**基于函数返回的值。</span><span class="sxs-lookup"><span data-stu-id="96d6a-143">The value returned by a **SERVICEWIZARDDLGPROC** based function is dependent on the window message received.</span></span> <span data-ttu-id="96d6a-144">特别注意特殊的返回值为 WIZ_QUERYNUMPAGES 消息。</span><span class="sxs-lookup"><span data-stu-id="96d6a-144">Note in particular the exceptional return value for the WIZ_QUERYNUMPAGES message.</span></span> <span data-ttu-id="96d6a-145">普通的返回值为：</span><span class="sxs-lookup"><span data-stu-id="96d6a-145">The normal return values are:</span></span> 
  
<span data-ttu-id="96d6a-146">TRUE</span><span class="sxs-lookup"><span data-stu-id="96d6a-146">TRUE</span></span> 
  
> <span data-ttu-id="96d6a-147">服务提供商已处理的收到的窗口消息。</span><span class="sxs-lookup"><span data-stu-id="96d6a-147">The service provider has processed the received window message.</span></span> 
    
<span data-ttu-id="96d6a-148">FALSE</span><span class="sxs-lookup"><span data-stu-id="96d6a-148">FALSE</span></span> 
  
> <span data-ttu-id="96d6a-149">服务提供商尚未处理的收到的窗口消息。</span><span class="sxs-lookup"><span data-stu-id="96d6a-149">The service provider has not processed the received window message.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="96d6a-150">备注</span><span class="sxs-lookup"><span data-stu-id="96d6a-150">Remarks</span></span>

<span data-ttu-id="96d6a-151">当用户从一个属性页面移动到另一个时，提供程序负责为隐藏旧页上的控件和显示下一页或上一页页上的控件。</span><span class="sxs-lookup"><span data-stu-id="96d6a-151">When the user moves from one property page to another, the provider is responsible for hiding the old page's controls and showing the controls for the next or previous page.</span></span> <span data-ttu-id="96d6a-152">当用户单击**下一步**按钮时， **SERVICEWIZARDDLGPROC**基于函数使用的 WM_COMMAND 消息和 WIZ_NEXT 调用_wParam_参数中。</span><span class="sxs-lookup"><span data-stu-id="96d6a-152">When the user clicks the **Next** button, the **SERVICEWIZARDDLGPROC** based function is called with the WM_COMMAND message and WIZ_NEXT in the  _wParam_ parameter.</span></span> <span data-ttu-id="96d6a-153">下面的步骤介绍之间用户单击**下一步**和第一个提供程序的配置页面呈现时间时发生的情形。</span><span class="sxs-lookup"><span data-stu-id="96d6a-153">The following steps describe what occurs between the time the user clicks **Next** and the time the first provider's configuration pages are rendered.</span></span> 
  
1. <span data-ttu-id="96d6a-154">配置文件向导隐藏在窗口中的任何控件。</span><span class="sxs-lookup"><span data-stu-id="96d6a-154">The Profile Wizard hides any controls that are on the window.</span></span> 
    
2. <span data-ttu-id="96d6a-155">配置文件向导将提供程序的隐藏的控件添加到页。</span><span class="sxs-lookup"><span data-stu-id="96d6a-155">The Profile Wizard adds the provider's hidden controls to the page.</span></span> 
    
3. <span data-ttu-id="96d6a-156">配置文件向导调用**SERVICEWIZARDDLGPROC**，发送 WM_INITDIALOG 邮件，以便提供程序可以初始化控件。</span><span class="sxs-lookup"><span data-stu-id="96d6a-156">The Profile Wizard calls **SERVICEWIZARDDLGPROC**, sending the WM_INITDIALOG message, so that the provider can initialize the controls.</span></span> 
    
4. <span data-ttu-id="96d6a-157">配置文件向导调用**SERVICEWIZARDDLGPROC**，发送 WIZ_QUERYNUMPAGES 消息。</span><span class="sxs-lookup"><span data-stu-id="96d6a-157">The Profile Wizard calls **SERVICEWIZARDDLGPROC**, sending the WIZ_QUERYNUMPAGES message.</span></span> <span data-ttu-id="96d6a-158">提供程序返回要显示的页面的数量。</span><span class="sxs-lookup"><span data-stu-id="96d6a-158">The provider returns the number of pages that are to be shown.</span></span> 
    
5. <span data-ttu-id="96d6a-159">配置文件向导调用**SERVICEWIZARDDLGPROC**， _wParam_参数设置为 WIZ_NEXT 或 WIZ_PREV 发送 WM_COMMAND 消息。</span><span class="sxs-lookup"><span data-stu-id="96d6a-159">The Profile Wizard calls **SERVICEWIZARDDLGPROC**, sending the WM_COMMAND message with the  _wParam_ parameter set to either WIZ_NEXT or WIZ_PREV.</span></span> <span data-ttu-id="96d6a-160">此时，提供程序是返回 FALSE {错误} 或显示其控件并返回 TRUE {成功}。</span><span class="sxs-lookup"><span data-stu-id="96d6a-160">At this point, the provider either returns FALSE {error} or reveals its controls and returns TRUE {success}.</span></span> <span data-ttu-id="96d6a-161">如果 ID_NEXT 传入配置文件向导，将显示提供程序的第一页。</span><span class="sxs-lookup"><span data-stu-id="96d6a-161">If the Profile Wizard passes in ID_NEXT, the provider's first page is displayed.</span></span> <span data-ttu-id="96d6a-162">如果传入 ID_PREV，将显示的最后一页。</span><span class="sxs-lookup"><span data-stu-id="96d6a-162">If ID_PREV is passed in, the last page is displayed.</span></span> 
    
6. <span data-ttu-id="96d6a-163">配置文件向导调用提供程序的**SERVICEWIZARDDLGPROC**函数，WM_COMMAND 消息发送带有_wParam_参数设置为 WIZ_NEXT 或 WIZ_PREV （具体取决于哪个按钮用户单击）。</span><span class="sxs-lookup"><span data-stu-id="96d6a-163">The Profile Wizard calls the provider's **SERVICEWIZARDDLGPROC** function, sending the WM_COMMAND message with the  _wParam_ parameter set to either WIZ_NEXT or WIZ_PREV (depending on which button the user clicked).</span></span> <span data-ttu-id="96d6a-164">提供程序负责为显示或隐藏及其控件并且其数据写入**IMAPIProp**传递给配置文件向导以通过其序列页面的步骤。</span><span class="sxs-lookup"><span data-stu-id="96d6a-164">The provider is responsible for showing or hiding its controls and writing its data to the **IMAPIProp** passed to the Profile Wizard to step through its sequence of pages.</span></span> <span data-ttu-id="96d6a-165">如果已成功显示下一页或上一页页上，并且无法显示 FALSE 如果既未下一步，也不是以前页上，提供程序应返回 TRUE。</span><span class="sxs-lookup"><span data-stu-id="96d6a-165">The provider should return TRUE if the next or previous page was successfully shown, and FALSE if neither the next nor previous page could be shown.</span></span> <span data-ttu-id="96d6a-166">提供程序需要注意的逐步之外的页面，其序列时并通过隐藏及其控件并将其数据写到配置文件的相应做出响应。</span><span class="sxs-lookup"><span data-stu-id="96d6a-166">The provider needs to be aware of when it is stepping outside of its sequence of pages, and respond appropriately by hiding its controls and writing its data to the profile.</span></span> 
    
7. <span data-ttu-id="96d6a-167">如果用户步骤的页面的提供程序的范围之外，配置文件向导从对话框中删除提供程序的隐藏的控件和调用下一个提供程序或显示其下一页上，如果这正印证了最后的提供程序。</span><span class="sxs-lookup"><span data-stu-id="96d6a-167">If the user steps outside the provider's range of pages, the Profile Wizard deletes the provider's hidden controls from the dialog box and calls the next provider or displays its next page if that was the last provider.</span></span> 
    

