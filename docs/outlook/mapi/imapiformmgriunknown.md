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
ms.openlocfilehash: 4fdd50a1108a6546445516664b01fb0f994fbfdb
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775443"
---
# <a name="imapiformmgr--iunknown"></a><span data-ttu-id="39ba1-103">IMAPIFormMgr : IUnknown</span><span class="sxs-lookup"><span data-stu-id="39ba1-103">IMAPIFormMgr : IUnknown</span></span>

  
  
<span data-ttu-id="39ba1-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="39ba1-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="39ba1-105">启用表单查看器获取有关的信息和激活窗体服务器。</span><span class="sxs-lookup"><span data-stu-id="39ba1-105">Enables form viewers to obtain information about and activate form servers.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="39ba1-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="39ba1-106">Header file:</span></span>  <br/> |<span data-ttu-id="39ba1-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="39ba1-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="39ba1-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="39ba1-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="39ba1-109">窗体管理器对象</span><span class="sxs-lookup"><span data-stu-id="39ba1-109">Form manager objects</span></span>  <br/> |
|<span data-ttu-id="39ba1-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="39ba1-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="39ba1-111">窗体库提供程序</span><span class="sxs-lookup"><span data-stu-id="39ba1-111">Form library providers</span></span>  <br/> |
|<span data-ttu-id="39ba1-112">调用：</span><span class="sxs-lookup"><span data-stu-id="39ba1-112">Called by:</span></span>  <br/> |<span data-ttu-id="39ba1-113">表单查看器</span><span class="sxs-lookup"><span data-stu-id="39ba1-113">Form viewers</span></span>  <br/> |
|<span data-ttu-id="39ba1-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="39ba1-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="39ba1-115">IID_IMAPIFormMgr</span><span class="sxs-lookup"><span data-stu-id="39ba1-115">IID_IMAPIFormMgr</span></span>  <br/> |
|<span data-ttu-id="39ba1-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="39ba1-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="39ba1-117">LPMAPIFORMMGR</span><span class="sxs-lookup"><span data-stu-id="39ba1-117">LPMAPIFORMMGR</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="39ba1-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="39ba1-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="39ba1-119">LoadForm</span><span class="sxs-lookup"><span data-stu-id="39ba1-119">LoadForm</span></span>](imapiformmgr-loadform.md) <br/> |<span data-ttu-id="39ba1-120">启动打开现有邮件窗体。</span><span class="sxs-lookup"><span data-stu-id="39ba1-120">Starts a form to open an existing message.</span></span>  <br/> |
|[<span data-ttu-id="39ba1-121">ResolveMessageClass</span><span class="sxs-lookup"><span data-stu-id="39ba1-121">ResolveMessageClass</span></span>](imapiformmgr-resolvemessageclass.md) <br/> |<span data-ttu-id="39ba1-122">将邮件类解析为其表单中的窗体容器中，并返回该窗体的窗体信息对象。</span><span class="sxs-lookup"><span data-stu-id="39ba1-122">Resolves a message class to its form within a form container, and returns a form information object for that form.</span></span>  <br/> |
|[<span data-ttu-id="39ba1-123">ResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="39ba1-123">ResolveMultipleMessageClasses</span></span>](imapiformmgr-resolvemultiplemessageclasses.md) <br/> |<span data-ttu-id="39ba1-124">将一组的邮件类解析为其的窗体中的窗体容器中，并返回这些表单的信息对象的窗体的数组。</span><span class="sxs-lookup"><span data-stu-id="39ba1-124">Resolves a group of message classes to their forms within a form container, and returns an array of form information objects for those forms.</span></span>  <br/> |
|[<span data-ttu-id="39ba1-125">CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="39ba1-125">CalcFormPropSet</span></span>](imapiformmgr-calcformpropset.md) <br/> |<span data-ttu-id="39ba1-126">返回一个数组的一组表单使用的属性。</span><span class="sxs-lookup"><span data-stu-id="39ba1-126">Returns an array of the properties that a group of forms uses.</span></span>  <br/> |
|[<span data-ttu-id="39ba1-127">CreateForm</span><span class="sxs-lookup"><span data-stu-id="39ba1-127">CreateForm</span></span>](imapiformmgr-createform.md) <br/> |<span data-ttu-id="39ba1-128">启动表单创建新邮件基于窗体的邮件类别。</span><span class="sxs-lookup"><span data-stu-id="39ba1-128">Launches a form to create a new message based on the form's message class.</span></span>  <br/> |
|[<span data-ttu-id="39ba1-129">SelectForm</span><span class="sxs-lookup"><span data-stu-id="39ba1-129">SelectForm</span></span>](imapiformmgr-selectform.md) <br/> |<span data-ttu-id="39ba1-130">显示一个对话框，允许用户选择一个窗体，并返回描述该窗体的窗体信息对象。</span><span class="sxs-lookup"><span data-stu-id="39ba1-130">Presents a dialog box that enables the user to select a form, and returns a form information object that describes that form.</span></span>  <br/> |
|[<span data-ttu-id="39ba1-131">SelectMultipleForms</span><span class="sxs-lookup"><span data-stu-id="39ba1-131">SelectMultipleForms</span></span>](imapiformmgr-selectmultipleforms.md) <br/> |<span data-ttu-id="39ba1-132">显示一个对话框，使用户能够选择多个表单，并返回介绍这些表单的信息对象的窗体的数组。</span><span class="sxs-lookup"><span data-stu-id="39ba1-132">Presents a dialog box that enables the user to select multiple forms, and returns an array of form information objects that describe those forms.</span></span>  <br/> |
|[<span data-ttu-id="39ba1-133">SelectFormContainer</span><span class="sxs-lookup"><span data-stu-id="39ba1-133">SelectFormContainer</span></span>](imapiformmgr-selectformcontainer.md) <br/> |<span data-ttu-id="39ba1-134">显示一个对话框，使用户能够选择窗体容器，并返回对 container 对象选定的用户界面。</span><span class="sxs-lookup"><span data-stu-id="39ba1-134">Presents a dialog box that enables the user to select a form container, and returns an interface for the container object the user selected.</span></span>  <br/> |
|[<span data-ttu-id="39ba1-135">OpenFormContainer</span><span class="sxs-lookup"><span data-stu-id="39ba1-135">OpenFormContainer</span></span>](imapiformmgr-openformcontainer.md) <br/> |<span data-ttu-id="39ba1-136">打开特定窗体容器[IMAPIFormContainer](imapiformcontaineriunknown.md)界面。</span><span class="sxs-lookup"><span data-stu-id="39ba1-136">Opens an [IMAPIFormContainer](imapiformcontaineriunknown.md) interface for a specific form container.</span></span>  <br/> |
|[<span data-ttu-id="39ba1-137">PrepareForm</span><span class="sxs-lookup"><span data-stu-id="39ba1-137">PrepareForm</span></span>](imapiformmgr-prepareform.md) <br/> |<span data-ttu-id="39ba1-138">下载用于打开的表单。</span><span class="sxs-lookup"><span data-stu-id="39ba1-138">Downloads a form for opening.</span></span>  <br/> |
|[<span data-ttu-id="39ba1-139">IsInConflict</span><span class="sxs-lookup"><span data-stu-id="39ba1-139">IsInConflict</span></span>](imapiformmgr-isinconflict.md) <br/> |<span data-ttu-id="39ba1-140">确定窗体是否可以处理其自己的邮件冲突。</span><span class="sxs-lookup"><span data-stu-id="39ba1-140">Determines whether a form can handle its own message conflicts.</span></span>  <br/> |
|[<span data-ttu-id="39ba1-141">时出错</span><span class="sxs-lookup"><span data-stu-id="39ba1-141">GetLastError</span></span>](imapiformmgr-getlasterror.md) <br/> |<span data-ttu-id="39ba1-142">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面对窗体管理器对象发生的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="39ba1-142">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error occurring to the form manager object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="39ba1-143">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39ba1-143">See also</span></span>



[<span data-ttu-id="39ba1-144">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="39ba1-144">MAPI Interfaces</span></span>](mapi-interfaces.md)

