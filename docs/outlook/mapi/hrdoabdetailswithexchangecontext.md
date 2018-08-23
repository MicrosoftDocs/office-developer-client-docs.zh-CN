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
ms.openlocfilehash: d882fa1e705969ae06da46710fc7216625ca932e
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22566374"
---
# <a name="hrdoabdetailswithexchangecontext"></a><span data-ttu-id="b95a5-103">HrDoABDetailsWithExchangeContext</span><span class="sxs-lookup"><span data-stu-id="b95a5-103">HrDoABDetailsWithExchangeContext</span></span>

  
  
<span data-ttu-id="b95a5-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="b95a5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="b95a5-105">确保**OpenEntry**方法打开的预期的 Exchange 通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="b95a5-105">Ensures that the **OpenEntry** method is opened by the expected Exchange address book provider.</span></span> <span data-ttu-id="b95a5-106">此函数工作方式类似于[IAddrBook::Details](iaddrbook-details.md)，但打开**entryID**使用_pEmsmdbUID_参数标识的 Exchange 通讯簿。</span><span class="sxs-lookup"><span data-stu-id="b95a5-106">This function works similarly to [IAddrBook::Details](iaddrbook-details.md), but opens the **entryID** using the Exchange address book identified by the  _pEmsmdbUID_ parameter.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="b95a5-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="b95a5-107">Header file:</span></span>  <br/> |<span data-ttu-id="b95a5-108">abhelp.h</span><span class="sxs-lookup"><span data-stu-id="b95a5-108">abhelp.h</span></span>  <br/> |
|<span data-ttu-id="b95a5-109">通过实现：</span><span class="sxs-lookup"><span data-stu-id="b95a5-109">Implemented by:</span></span>  <br/> |<span data-ttu-id="b95a5-110">MAPI</span><span class="sxs-lookup"><span data-stu-id="b95a5-110">MAPI</span></span>  <br/> |
|<span data-ttu-id="b95a5-111">调用：</span><span class="sxs-lookup"><span data-stu-id="b95a5-111">Called by:</span></span>  <br/> |<span data-ttu-id="b95a5-112">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="b95a5-112">Client applications and service providers</span></span>  <br/> |
   
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

## <a name="parameters"></a><span data-ttu-id="b95a5-113">参数</span><span class="sxs-lookup"><span data-stu-id="b95a5-113">Parameters</span></span>

 <span data-ttu-id="b95a5-114">_pmsess_</span><span class="sxs-lookup"><span data-stu-id="b95a5-114">_pmsess_</span></span>
  
> <span data-ttu-id="b95a5-115">登录**IMAPISession**。</span><span class="sxs-lookup"><span data-stu-id="b95a5-115">The logged on **IMAPISession**.</span></span> <span data-ttu-id="b95a5-116">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="b95a5-116">It cannot be NULL.</span></span>
    
 <span data-ttu-id="b95a5-117">_pEmsmdbUID_</span><span class="sxs-lookup"><span data-stu-id="b95a5-117">_pEmsmdbUID_</span></span>
  
> <span data-ttu-id="b95a5-118">指向标识包含该函数用于打开的项标识符 Exchange 通讯簿提供程序的 Exchange 服务**emsmdbUID**的指针。</span><span class="sxs-lookup"><span data-stu-id="b95a5-118">A pointer to an **emsmdbUID** that identifies the Exchange Service that contains the Exchange address book provider that is used by the function to open the entry identifier.</span></span> <span data-ttu-id="b95a5-119">如果传入的项标识符不是 Exchange 通讯簿提供程序条目标识符，则忽略此参数，并函数与[IAddrBook::OpenEntry](iaddrbook-openentry.md)相似之处。</span><span class="sxs-lookup"><span data-stu-id="b95a5-119">If the incoming entry identifier is not an Exchange address book provider entry identifier, this parameter is ignored and the function behaves like [IAddrBook::OpenEntry](iaddrbook-openentry.md).</span></span> <span data-ttu-id="b95a5-120">如果此参数为 NULL 或**MAPIUID**，此函数的还行为与[IAddrBook::OpenEntry](iaddrbook-openentry.md)完全相同。</span><span class="sxs-lookup"><span data-stu-id="b95a5-120">If this parameter is NULL or a zero **MAPIUID**, this function also acts exactly like [IAddrBook::OpenEntry](iaddrbook-openentry.md).</span></span> 
    
 <span data-ttu-id="b95a5-121">_pAddrBook_</span><span class="sxs-lookup"><span data-stu-id="b95a5-121">_pAddrBook_</span></span>
  
> <span data-ttu-id="b95a5-122">[in]通讯簿用于打开的项标识符。</span><span class="sxs-lookup"><span data-stu-id="b95a5-122">[in] The address book used to open the entry identifier.</span></span> <span data-ttu-id="b95a5-123">它不能为 NULL。</span><span class="sxs-lookup"><span data-stu-id="b95a5-123">It cannot be NULL.</span></span>
    
 <span data-ttu-id="b95a5-124">_lpulUIParam_</span><span class="sxs-lookup"><span data-stu-id="b95a5-124">_lpulUIParam_</span></span>
  
> <span data-ttu-id="b95a5-125">[输出]对话框中的父窗口句柄。</span><span class="sxs-lookup"><span data-stu-id="b95a5-125">[out] A handle to the parent window for the dialog box.</span></span>
    
 <span data-ttu-id="b95a5-126">_lpfnDismiss_</span><span class="sxs-lookup"><span data-stu-id="b95a5-126">_lpfnDismiss_</span></span>
  
> <span data-ttu-id="b95a5-127">[in]一个指向基于**DISMISSMODELESS**原型或为空的一个函数指针。</span><span class="sxs-lookup"><span data-stu-id="b95a5-127">[in] A pointer to a function based on the **DISMISSMODELESS** prototype, or NULL.</span></span> <span data-ttu-id="b95a5-128">此成员仅适用于无模式版本的对话框中，如标志所指示的 DIALOG_SDI 设置。</span><span class="sxs-lookup"><span data-stu-id="b95a5-128">This member applies only to the modeless version of the dialog box, as indicated by the DIALOG_SDI flag being set.</span></span> <span data-ttu-id="b95a5-129">MAPI 调用的**DISMISSMODELESS**函数时在用户关闭无模式的地址对话框中，告知客户端的呼叫详细信息对话框中不再处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="b95a5-129">MAPI calls the **DISMISSMODELESS** function when the user dismisses the modeless address dialog box, informing a client that is calling Details that the dialog box is no longer active.</span></span> 
    
 <span data-ttu-id="b95a5-130">_lpvDismissContext_</span><span class="sxs-lookup"><span data-stu-id="b95a5-130">_lpvDismissContext_</span></span>
  
> <span data-ttu-id="b95a5-131">[in]指向上下文信息传递给**DISMISSMODELESS**函数_lpfnDismiss_参数指向的指针。</span><span class="sxs-lookup"><span data-stu-id="b95a5-131">[in] A pointer to context information to pass to the **DISMISSMODELESS** function pointed to by the  _lpfnDismiss_ parameter.</span></span> <span data-ttu-id="b95a5-132">此参数仅适用于无模式对话框中的版本通过_ulFlags_参数中包括**DIALOG_SDI**标志。</span><span class="sxs-lookup"><span data-stu-id="b95a5-132">This parameter applies only to the modeless version of the dialog box by including the **DIALOG_SDI** flag in the  _ulFlags_ parameter.</span></span> 
    
 <span data-ttu-id="b95a5-133">_cbEntryID_</span><span class="sxs-lookup"><span data-stu-id="b95a5-133">_cbEntryID_</span></span>
  
> <span data-ttu-id="b95a5-134">[in]_LpEntryID_参数指定的项标识符的字节数。</span><span class="sxs-lookup"><span data-stu-id="b95a5-134">[in] The byte count of the entry identifier specified by the  _lpEntryID_ parameter.</span></span> 
    
 <span data-ttu-id="b95a5-135">_lpEntryID_</span><span class="sxs-lookup"><span data-stu-id="b95a5-135">_lpEntryID_</span></span>
  
> <span data-ttu-id="b95a5-136">[in]一个指向代表打开的通讯簿条目的项标识符。</span><span class="sxs-lookup"><span data-stu-id="b95a5-136">[in] A pointer to the entry identifier that represents the address book entry to open.</span></span>
    
 <span data-ttu-id="b95a5-137">_lpfButtonCallback_</span><span class="sxs-lookup"><span data-stu-id="b95a5-137">_lpfButtonCallback_</span></span>
  
> <span data-ttu-id="b95a5-138">[in]基于**LPFNBUTTON**函数原型函数指针。</span><span class="sxs-lookup"><span data-stu-id="b95a5-138">[in] A pointer to a function based on the **LPFNBUTTON** function prototype.</span></span> <span data-ttu-id="b95a5-139">**LPFNBUTTON**函数将按钮添加到详细信息对话框。</span><span class="sxs-lookup"><span data-stu-id="b95a5-139">An **LPFNBUTTON** function adds a button to the details dialog box.</span></span> 
    
 <span data-ttu-id="b95a5-140">_lpvButtonContext_</span><span class="sxs-lookup"><span data-stu-id="b95a5-140">_lpvButtonContext_</span></span>
  
> <span data-ttu-id="b95a5-141">[in]指向作为参数指定由_lpfButtonCallback_参数的函数使用的数据的指针。</span><span class="sxs-lookup"><span data-stu-id="b95a5-141">[in] A pointer to data that was used as a parameter for the function specified by the  _lpfButtonCallback_ parameter.</span></span> 
    
 <span data-ttu-id="b95a5-142">_lpszButtonText_</span><span class="sxs-lookup"><span data-stu-id="b95a5-142">_lpszButtonText_</span></span>
  
> <span data-ttu-id="b95a5-143">[in]指向一个字符串，包含要应用于添加按钮，文本是否可扩展该按钮的指针。</span><span class="sxs-lookup"><span data-stu-id="b95a5-143">[in] A pointer to a string that contains text to be applied to the added button, if that button is extensible.</span></span> <span data-ttu-id="b95a5-144">不需要的可扩展按钮时， _lpszButtonText_参数应为 NULL。</span><span class="sxs-lookup"><span data-stu-id="b95a5-144">The  _lpszButtonText_ parameter should be NULL when an extensible button is not needed.</span></span> 
    
 <span data-ttu-id="b95a5-145">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="b95a5-145">_ulFlags_</span></span>
  
> <span data-ttu-id="b95a5-146">[in]位掩码的标志的控制_lpszButtonText_参数的文本的类型。</span><span class="sxs-lookup"><span data-stu-id="b95a5-146">[in] A bitmask of flags that controls the type of the text for the  _lpszButtonText_ parameter.</span></span> <span data-ttu-id="b95a5-147">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="b95a5-147">The following flags can be set:</span></span> 
    
<span data-ttu-id="b95a5-148">AB_TELL_DETAILS_CHANGE</span><span class="sxs-lookup"><span data-stu-id="b95a5-148">AB_TELL_DETAILS_CHANGE</span></span>
  
> <span data-ttu-id="b95a5-149">指示详细信息返回 TRUE 是否进行了更改实际的地址;否则，详细信息将返回 FALSE。</span><span class="sxs-lookup"><span data-stu-id="b95a5-149">Indicates that Details returns TRUE if changes are actually made to the address; otherwise, Details returns FALSE.</span></span>
    
<span data-ttu-id="b95a5-150">DIALOG_MODAL</span><span class="sxs-lookup"><span data-stu-id="b95a5-150">DIALOG_MODAL</span></span>
  
> <span data-ttu-id="b95a5-151">显示模式版本的通用的地址对话框。</span><span class="sxs-lookup"><span data-stu-id="b95a5-151">Displays the modal version of the common address dialog box.</span></span> <span data-ttu-id="b95a5-152">此标志是与 DIALOG_SDI 互斥。</span><span class="sxs-lookup"><span data-stu-id="b95a5-152">This flag is mutually exclusive with DIALOG_SDI.</span></span>
    
<span data-ttu-id="b95a5-153">DIALOG_SDI</span><span class="sxs-lookup"><span data-stu-id="b95a5-153">DIALOG_SDI</span></span>
  
> <span data-ttu-id="b95a5-154">显示通用的地址对话框的无模式版本。</span><span class="sxs-lookup"><span data-stu-id="b95a5-154">Displays the modeless version of the common address dialog box.</span></span> <span data-ttu-id="b95a5-155">此标志是与 DIALOG_MODAL 互斥。</span><span class="sxs-lookup"><span data-stu-id="b95a5-155">This flag is mutually exclusive with DIALOG_MODAL.</span></span>
    
<span data-ttu-id="b95a5-156">MAPI_UNICODE</span><span class="sxs-lookup"><span data-stu-id="b95a5-156">MAPI_UNICODE</span></span>
  
> <span data-ttu-id="b95a5-157">传入的字符串采用 Unicode 格式。</span><span class="sxs-lookup"><span data-stu-id="b95a5-157">The passed-in strings are in Unicode format.</span></span> <span data-ttu-id="b95a5-158">如果未设置 MAPI_UNICODE 标志的字符串是以 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="b95a5-158">If the MAPI_UNICODE flag is not set, the strings are in ANSI format.</span></span>
    

