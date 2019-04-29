---
title: HrDoABDetailsWithExchangeContext
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: b4e7fed2-88e4-4e14-90b6-913a1b7e338a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 353a663071a9f23f0d2330169d3ac7747e047c2b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421366"
---
# <a name="hrdoabdetailswithexchangecontext"></a><span data-ttu-id="e3573-103">HrDoABDetailsWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="e3573-103">HrDoABDetailsWithExchangeContext</span></span>

  
  
<span data-ttu-id="e3573-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e3573-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e3573-105">确保**OpenEntry**方法由预期的 Exchange 通讯簿提供程序打开。</span><span class="sxs-lookup"><span data-stu-id="e3573-105">Ensures that the **OpenEntry** method is opened by the expected Exchange address book provider.</span></span> <span data-ttu-id="e3573-106">此函数的工作方式类似于[IAddrBook::D etails](iaddrbook-details.md), 但使用由_pEmsmdbUID_参数标识的 Exchange 通讯簿打开**entryID** 。</span><span class="sxs-lookup"><span data-stu-id="e3573-106">This function works similarly to [IAddrBook::Details](iaddrbook-details.md), but opens the **entryID** using the Exchange address book identified by the  _pEmsmdbUID_ parameter.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e3573-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="e3573-107">Header file:</span></span>  <br/> |<span data-ttu-id="e3573-108">abhelp</span><span class="sxs-lookup"><span data-stu-id="e3573-108">abhelp.h</span></span>  <br/> |
|<span data-ttu-id="e3573-109">实现者：</span><span class="sxs-lookup"><span data-stu-id="e3573-109">Implemented by:</span></span>  <br/> |<span data-ttu-id="e3573-110">MAPI</span><span class="sxs-lookup"><span data-stu-id="e3573-110">MAPI</span></span>  <br/> |
|<span data-ttu-id="e3573-111">调用者：</span><span class="sxs-lookup"><span data-stu-id="e3573-111">Called by:</span></span>  <br/> |<span data-ttu-id="e3573-112">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="e3573-112">Client applications and service providers</span></span>  <br/> |
   
```cpp
HRESULT HrOpenABEntryWithExchangeContext(
  LPMAPISESSION   pmsess,
  const MAPIUID  *pEmsmdbUID,
  LPADRBOOK pAddrBook,
  ULONG_PTR FAR * lpulUIParam,
  LPFNDISMISS lpfnDismiss,
  LPVOID lpvDismissContext,
  ULONG cbEntryID,
  LPENTRYID lpEntryID,
  LPENTRYID lpEntryID,
  LPFNBUTTON lpfButtonCallback,
  LPVOID lpvButtonContext,
  LPSTR lpszButtonText,
  ULONG ulFlags,
);
```

## <a name="parameters"></a><span data-ttu-id="e3573-113">参数</span><span class="sxs-lookup"><span data-stu-id="e3573-113">Parameters</span></span>

 <span data-ttu-id="e3573-114">_pmsess_</span><span class="sxs-lookup"><span data-stu-id="e3573-114">_pmsess_</span></span>
  
> <span data-ttu-id="e3573-115">登录的**IMAPISession**。</span><span class="sxs-lookup"><span data-stu-id="e3573-115">The logged on **IMAPISession**.</span></span> <span data-ttu-id="e3573-116">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="e3573-116">It cannot be NULL.</span></span>
    
 <span data-ttu-id="e3573-117">_pEmsmdbUID_</span><span class="sxs-lookup"><span data-stu-id="e3573-117">_pEmsmdbUID_</span></span>
  
> <span data-ttu-id="e3573-118">指向**emsmdbUID**的指针, 该链接标识包含 exchange 通讯簿提供程序的 exchange 服务, 该提供程序将使用该功能打开条目标识符。</span><span class="sxs-lookup"><span data-stu-id="e3573-118">A pointer to an **emsmdbUID** that identifies the Exchange Service that contains the Exchange address book provider that is used by the function to open the entry identifier.</span></span> <span data-ttu-id="e3573-119">如果传入条目标识符不是 Exchange 通讯簿提供程序条目标识符, 则此参数将被忽略, 并且函数的行为类似于[IAddrBook:: OpenEntry](iaddrbook-openentry.md)。</span><span class="sxs-lookup"><span data-stu-id="e3573-119">If the incoming entry identifier is not an Exchange address book provider entry identifier, this parameter is ignored and the function behaves like [IAddrBook::OpenEntry](iaddrbook-openentry.md).</span></span> <span data-ttu-id="e3573-120">如果此参数为 NULL 或零**MAPIUID**, 则此函数也相当于[IAddrBook:: OpenEntry](iaddrbook-openentry.md)。</span><span class="sxs-lookup"><span data-stu-id="e3573-120">If this parameter is NULL or a zero **MAPIUID**, this function also acts exactly like [IAddrBook::OpenEntry](iaddrbook-openentry.md).</span></span> 
    
 <span data-ttu-id="e3573-121">_pAddrBook_</span><span class="sxs-lookup"><span data-stu-id="e3573-121">_pAddrBook_</span></span>
  
> <span data-ttu-id="e3573-122">实时用于打开条目标识符的通讯簿。</span><span class="sxs-lookup"><span data-stu-id="e3573-122">[in] The address book used to open the entry identifier.</span></span> <span data-ttu-id="e3573-123">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="e3573-123">It cannot be NULL.</span></span>
    
 <span data-ttu-id="e3573-124">_lpulUIParam_</span><span class="sxs-lookup"><span data-stu-id="e3573-124">_lpulUIParam_</span></span>
  
> <span data-ttu-id="e3573-125">排除对话框的父窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="e3573-125">[out] A handle to the parent window for the dialog box.</span></span>
    
 <span data-ttu-id="e3573-126">_lpfnDismiss_</span><span class="sxs-lookup"><span data-stu-id="e3573-126">_lpfnDismiss_</span></span>
  
> <span data-ttu-id="e3573-127">实时指向基于**DISMISSMODELESS**原型的函数的指针或 NULL。</span><span class="sxs-lookup"><span data-stu-id="e3573-127">[in] A pointer to a function based on the **DISMISSMODELESS** prototype, or NULL.</span></span> <span data-ttu-id="e3573-128">此成员仅适用于对话框的无模式版本, 正如设置的 DIALOG_SDI 标志所指示的那样。</span><span class="sxs-lookup"><span data-stu-id="e3573-128">This member applies only to the modeless version of the dialog box, as indicated by the DIALOG_SDI flag being set.</span></span> <span data-ttu-id="e3573-129">MAPI 在用户消除无模式地址对话框时调用**DISMISSMODELESS**函数, 告知客户端正在调用对话框中不再处于活动状态的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e3573-129">MAPI calls the **DISMISSMODELESS** function when the user dismisses the modeless address dialog box, informing a client that is calling Details that the dialog box is no longer active.</span></span> 
    
 <span data-ttu-id="e3573-130">_lpvDismissContext_</span><span class="sxs-lookup"><span data-stu-id="e3573-130">_lpvDismissContext_</span></span>
  
> <span data-ttu-id="e3573-131">实时指向传递给_lpfnDismiss_参数指向的**DISMISSMODELESS**函数的上下文信息的指针。</span><span class="sxs-lookup"><span data-stu-id="e3573-131">[in] A pointer to context information to pass to the **DISMISSMODELESS** function pointed to by the  _lpfnDismiss_ parameter.</span></span> <span data-ttu-id="e3573-132">此参数仅适用于对话框的无模式版本, 方法是在_ulFlags_参数中包含**DIALOG_SDI**标志。</span><span class="sxs-lookup"><span data-stu-id="e3573-132">This parameter applies only to the modeless version of the dialog box by including the **DIALOG_SDI** flag in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="e3573-133">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="e3573-133">_cbEntryID_</span></span>
  
> <span data-ttu-id="e3573-134">实时由_lpEntryID_参数指定的条目标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="e3573-134">[in] The byte count of the entry identifier specified by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="e3573-135">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="e3573-135">_lpEntryID_</span></span>
  
> <span data-ttu-id="e3573-136">实时指向表示要打开的通讯簿条目的条目标识符的指针。</span><span class="sxs-lookup"><span data-stu-id="e3573-136">[in] A pointer to the entry identifier that represents the address book entry to open.</span></span>
    
 <span data-ttu-id="e3573-137">_lpfButtonCallback_</span><span class="sxs-lookup"><span data-stu-id="e3573-137">_lpfButtonCallback_</span></span>
  
> <span data-ttu-id="e3573-138">实时指向基于**LPFNBUTTON**函数原型的函数的指针。</span><span class="sxs-lookup"><span data-stu-id="e3573-138">[in] A pointer to a function based on the **LPFNBUTTON** function prototype.</span></span> <span data-ttu-id="e3573-139">**LPFNBUTTON**函数将按钮添加到 "详细信息" 对话框中。</span><span class="sxs-lookup"><span data-stu-id="e3573-139">An **LPFNBUTTON** function adds a button to the details dialog box.</span></span> 
    
 <span data-ttu-id="e3573-140">_lpvButtonContext_</span><span class="sxs-lookup"><span data-stu-id="e3573-140">_lpvButtonContext_</span></span>
  
> <span data-ttu-id="e3573-141">实时指向用作_lpfButtonCallback_参数所指定函数的参数的数据的指针。</span><span class="sxs-lookup"><span data-stu-id="e3573-141">[in] A pointer to data that was used as a parameter for the function specified by the  _lpfButtonCallback_ parameter.</span></span> 
    
 <span data-ttu-id="e3573-142">_lpszButtonText_</span><span class="sxs-lookup"><span data-stu-id="e3573-142">_lpszButtonText_</span></span>
  
> <span data-ttu-id="e3573-143">实时指向一个字符串的指针, 该字符串包含要应用于已添加按钮的文本 (如果该按钮是可扩展的)。</span><span class="sxs-lookup"><span data-stu-id="e3573-143">[in] A pointer to a string that contains text to be applied to the added button, if that button is extensible.</span></span> <span data-ttu-id="e3573-144">当不需要可扩展按钮时, _lpszButtonText_参数应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="e3573-144">The  _lpszButtonText_ parameter should be NULL when an extensible button is not needed.</span></span> 
    
 <span data-ttu-id="e3573-145">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="e3573-145">_ulFlags_</span></span>
  
> <span data-ttu-id="e3573-146">实时用于控制_lpszButtonText_参数文本类型的标志的位掩码。</span><span class="sxs-lookup"><span data-stu-id="e3573-146">[in] A bitmask of flags that controls the type of the text for the  _lpszButtonText_ parameter.</span></span> <span data-ttu-id="e3573-147">可以设置以下标志:</span><span class="sxs-lookup"><span data-stu-id="e3573-147">The following flags can be set:</span></span> 
    
<span data-ttu-id="e3573-148">AB_TELL_DETAILS_CHANGE</span><span class="sxs-lookup"><span data-stu-id="e3573-148">AB_TELL_DETAILS_CHANGE</span></span>
  
> <span data-ttu-id="e3573-149">指示如果实际对地址进行了更改, 则详细信息返回 TRUE; 否则返回 false。否则, 详细信息将返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="e3573-149">Indicates that Details returns TRUE if changes are actually made to the address; otherwise, Details returns FALSE.</span></span>
    
<span data-ttu-id="e3573-150">DIALOG_MODAL</span><span class="sxs-lookup"><span data-stu-id="e3573-150">DIALOG_MODAL</span></span>
  
> <span data-ttu-id="e3573-151">显示 "常用地址" 对话框的模式版本。</span><span class="sxs-lookup"><span data-stu-id="e3573-151">Displays the modal version of the common address dialog box.</span></span> <span data-ttu-id="e3573-152">此标志与 DIALOG_SDI 互斥。</span><span class="sxs-lookup"><span data-stu-id="e3573-152">This flag is mutually exclusive with DIALOG_SDI.</span></span>
    
<span data-ttu-id="e3573-153">DIALOG_SDI</span><span class="sxs-lookup"><span data-stu-id="e3573-153">DIALOG_SDI</span></span>
  
> <span data-ttu-id="e3573-154">显示 "常用地址" 对话框的无模式版本。</span><span class="sxs-lookup"><span data-stu-id="e3573-154">Displays the modeless version of the common address dialog box.</span></span> <span data-ttu-id="e3573-155">此标志与 DIALOG_MODAL 互斥。</span><span class="sxs-lookup"><span data-stu-id="e3573-155">This flag is mutually exclusive with DIALOG_MODAL.</span></span>
    
<span data-ttu-id="e3573-156">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="e3573-156">MAPI_UNICODE</span></span>
  
> <span data-ttu-id="e3573-157">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="e3573-157">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="e3573-158">如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="e3573-158">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    

