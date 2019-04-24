---
title: IMAPIFormMgr IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgr
api_type:
- COM
ms.assetid: 8cbd1a42-7de6-43e0-8c77-7711773843d5
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: fbe6dc9364ee953661d574b70bcd225abcfe7a81
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321649"
---
# <a name="imapiformmgr--iunknown"></a><span data-ttu-id="846ce-103">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="846ce-103">IMAPIFormMgr : IUnknown</span></span>

  
  
<span data-ttu-id="846ce-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="846ce-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="846ce-105">使表单查看者能够获取和激活表单服务器的相关信息。</span><span class="sxs-lookup"><span data-stu-id="846ce-105">Enables form viewers to obtain information about and activate form servers.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="846ce-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="846ce-106">Header file:</span></span>  <br/> |<span data-ttu-id="846ce-107">Mapiform</span><span class="sxs-lookup"><span data-stu-id="846ce-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="846ce-108">公开者:</span><span class="sxs-lookup"><span data-stu-id="846ce-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="846ce-109">表单管理器对象</span><span class="sxs-lookup"><span data-stu-id="846ce-109">Form manager objects</span></span>  <br/> |
|<span data-ttu-id="846ce-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="846ce-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="846ce-111">表单库提供程序</span><span class="sxs-lookup"><span data-stu-id="846ce-111">Form library providers</span></span>  <br/> |
|<span data-ttu-id="846ce-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="846ce-112">Called by:</span></span>  <br/> |<span data-ttu-id="846ce-113">表单查看器</span><span class="sxs-lookup"><span data-stu-id="846ce-113">Form viewers</span></span>  <br/> |
|<span data-ttu-id="846ce-114">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="846ce-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="846ce-115">IID_IMAPIFormMgr</span><span class="sxs-lookup"><span data-stu-id="846ce-115">IID_IMAPIFormMgr</span></span>  <br/> |
|<span data-ttu-id="846ce-116">指针类型:</span><span class="sxs-lookup"><span data-stu-id="846ce-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="846ce-117">LPMAPIFORMMGR</span><span class="sxs-lookup"><span data-stu-id="846ce-117">LPMAPIFORMMGR</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="846ce-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="846ce-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="846ce-119">LoadForm</span><span class="sxs-lookup"><span data-stu-id="846ce-119">LoadForm</span></span>](imapiformmgr-loadform.md) <br/> |<span data-ttu-id="846ce-120">启动窗体以打开现有邮件。</span><span class="sxs-lookup"><span data-stu-id="846ce-120">Starts a form to open an existing message.</span></span>  <br/> |
|[<span data-ttu-id="846ce-121">ResolveMessageClass</span><span class="sxs-lookup"><span data-stu-id="846ce-121">ResolveMessageClass</span></span>](imapiformmgr-resolvemessageclass.md) <br/> |<span data-ttu-id="846ce-122">将邮件类别解析为表单容器中的窗体, 并返回该窗体的窗体信息对象。</span><span class="sxs-lookup"><span data-stu-id="846ce-122">Resolves a message class to its form within a form container, and returns a form information object for that form.</span></span>  <br/> |
|[<span data-ttu-id="846ce-123">ResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="846ce-123">ResolveMultipleMessageClasses</span></span>](imapiformmgr-resolvemultiplemessageclasses.md) <br/> |<span data-ttu-id="846ce-124">将一组消息类解析为表单容器中的表单, 并返回这些表单的表单信息对象的数组。</span><span class="sxs-lookup"><span data-stu-id="846ce-124">Resolves a group of message classes to their forms within a form container, and returns an array of form information objects for those forms.</span></span>  <br/> |
|[<span data-ttu-id="846ce-125">CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="846ce-125">CalcFormPropSet</span></span>](imapiformmgr-calcformpropset.md) <br/> |<span data-ttu-id="846ce-126">返回一组窗体使用的属性的数组。</span><span class="sxs-lookup"><span data-stu-id="846ce-126">Returns an array of the properties that a group of forms uses.</span></span>  <br/> |
|[<span data-ttu-id="846ce-127">CreateForm</span><span class="sxs-lookup"><span data-stu-id="846ce-127">CreateForm</span></span>](imapiformmgr-createform.md) <br/> |<span data-ttu-id="846ce-128">启动窗体以根据窗体的邮件类创建新邮件。</span><span class="sxs-lookup"><span data-stu-id="846ce-128">Launches a form to create a new message based on the form's message class.</span></span>  <br/> |
|[<span data-ttu-id="846ce-129">SelectForm</span><span class="sxs-lookup"><span data-stu-id="846ce-129">SelectForm</span></span>](imapiformmgr-selectform.md) <br/> |<span data-ttu-id="846ce-130">显示一个对话框, 使用户能够选择窗体, 并返回描述该窗体的窗体信息对象。</span><span class="sxs-lookup"><span data-stu-id="846ce-130">Presents a dialog box that enables the user to select a form, and returns a form information object that describes that form.</span></span>  <br/> |
|[<span data-ttu-id="846ce-131">SelectMultipleForms</span><span class="sxs-lookup"><span data-stu-id="846ce-131">SelectMultipleForms</span></span>](imapiformmgr-selectmultipleforms.md) <br/> |<span data-ttu-id="846ce-132">显示一个对话框, 允许用户选择多个窗体, 并返回描述这些窗体的窗体信息对象的数组。</span><span class="sxs-lookup"><span data-stu-id="846ce-132">Presents a dialog box that enables the user to select multiple forms, and returns an array of form information objects that describe those forms.</span></span>  <br/> |
|[<span data-ttu-id="846ce-133">SelectFormContainer</span><span class="sxs-lookup"><span data-stu-id="846ce-133">SelectFormContainer</span></span>](imapiformmgr-selectformcontainer.md) <br/> |<span data-ttu-id="846ce-134">显示一个对话框, 使用户可以选择表单容器, 并为用户选定的容器对象返回一个接口。</span><span class="sxs-lookup"><span data-stu-id="846ce-134">Presents a dialog box that enables the user to select a form container, and returns an interface for the container object the user selected.</span></span>  <br/> |
|[<span data-ttu-id="846ce-135">OpenFormContainer</span><span class="sxs-lookup"><span data-stu-id="846ce-135">OpenFormContainer</span></span>](imapiformmgr-openformcontainer.md) <br/> |<span data-ttu-id="846ce-136">打开特定表单容器的[IMAPIFormContainer](imapiformcontaineriunknown.md)接口。</span><span class="sxs-lookup"><span data-stu-id="846ce-136">Opens an [IMAPIFormContainer](imapiformcontaineriunknown.md) interface for a specific form container.</span></span>  <br/> |
|[<span data-ttu-id="846ce-137">PrepareForm</span><span class="sxs-lookup"><span data-stu-id="846ce-137">PrepareForm</span></span>](imapiformmgr-prepareform.md) <br/> |<span data-ttu-id="846ce-138">下载用于打开的表单。</span><span class="sxs-lookup"><span data-stu-id="846ce-138">Downloads a form for opening.</span></span>  <br/> |
|[<span data-ttu-id="846ce-139">IsInConflict</span><span class="sxs-lookup"><span data-stu-id="846ce-139">IsInConflict</span></span>](imapiformmgr-isinconflict.md) <br/> |<span data-ttu-id="846ce-140">确定表单是否可以处理自己的邮件冲突。</span><span class="sxs-lookup"><span data-stu-id="846ce-140">Determines whether a form can handle its own message conflicts.</span></span>  <br/> |
|[<span data-ttu-id="846ce-141">GetLastError</span><span class="sxs-lookup"><span data-stu-id="846ce-141">GetLastError</span></span>](imapiformmgr-getlasterror.md) <br/> |<span data-ttu-id="846ce-142">返回一个[MAPIERROR](mapierror.md)结构, 该结构包含上一个错误发生于表单管理器对象的相关信息。</span><span class="sxs-lookup"><span data-stu-id="846ce-142">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error occurring to the form manager object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="846ce-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="846ce-143">See also</span></span>



[<span data-ttu-id="846ce-144">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="846ce-144">MAPI Interfaces</span></span>](mapi-interfaces.md)

