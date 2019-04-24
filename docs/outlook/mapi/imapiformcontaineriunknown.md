---
title: IMAPIFormContainer IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormContainer
api_type:
- COM
ms.assetid: 437c8a75-1121-4919-8bd4-d57c0d6f4b9a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 208af28307a60615ecafda0992881c5df36aa56f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342187"
---
# <a name="imapiformcontainer--iunknown"></a><span data-ttu-id="d4479-103">IMAPIFormContainer : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d4479-103">IMAPIFormContainer : IUnknown</span></span>

  
  
<span data-ttu-id="d4479-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d4479-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d4479-105">管理表单库中的表单。</span><span class="sxs-lookup"><span data-stu-id="d4479-105">Manages forms in form libraries.</span></span> <span data-ttu-id="d4479-106">此接口用于创建特定于应用程序的表单库。</span><span class="sxs-lookup"><span data-stu-id="d4479-106">This interface is used to create application-specific form libraries.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="d4479-107">标头文件：</span><span class="sxs-lookup"><span data-stu-id="d4479-107">Header file:</span></span>  <br/> |<span data-ttu-id="d4479-108">Mapiform</span><span class="sxs-lookup"><span data-stu-id="d4479-108">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="d4479-109">公开者:</span><span class="sxs-lookup"><span data-stu-id="d4479-109">Exposed by:</span></span>  <br/> |<span data-ttu-id="d4479-110">表单容器对象</span><span class="sxs-lookup"><span data-stu-id="d4479-110">Form container objects</span></span>  <br/> |
|<span data-ttu-id="d4479-111">实现者：</span><span class="sxs-lookup"><span data-stu-id="d4479-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="d4479-112">表单库提供程序</span><span class="sxs-lookup"><span data-stu-id="d4479-112">Form library providers</span></span>  <br/> |
|<span data-ttu-id="d4479-113">调用者：</span><span class="sxs-lookup"><span data-stu-id="d4479-113">Called by:</span></span>  <br/> |<span data-ttu-id="d4479-114">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="d4479-114">Client applications</span></span>  <br/> |
|<span data-ttu-id="d4479-115">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="d4479-115">Interface identifier:</span></span>  <br/> |<span data-ttu-id="d4479-116">IID_IMAPIFormContainer</span><span class="sxs-lookup"><span data-stu-id="d4479-116">IID_IMAPIFormContainer</span></span>  <br/> |
|<span data-ttu-id="d4479-117">指针类型:</span><span class="sxs-lookup"><span data-stu-id="d4479-117">Pointer type:</span></span>  <br/> |<span data-ttu-id="d4479-118">LPMAPIFORMCONTAINER</span><span class="sxs-lookup"><span data-stu-id="d4479-118">LPMAPIFORMCONTAINER</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="d4479-119">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="d4479-119">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="d4479-120">InstallForm</span><span class="sxs-lookup"><span data-stu-id="d4479-120">InstallForm</span></span>](imapiformcontainer-installform.md) <br/> |<span data-ttu-id="d4479-121">将表单安装到表单容器中。</span><span class="sxs-lookup"><span data-stu-id="d4479-121">Installs a form into a form container.</span></span>  <br/> |
|[<span data-ttu-id="d4479-122">RemoveForm</span><span class="sxs-lookup"><span data-stu-id="d4479-122">RemoveForm</span></span>](imapiformcontainer-removeform.md) <br/> |<span data-ttu-id="d4479-123">从表单容器中删除特定的窗体。</span><span class="sxs-lookup"><span data-stu-id="d4479-123">Removes a particular form from a form container.</span></span>  <br/> |
|[<span data-ttu-id="d4479-124">ResolveMessageClass</span><span class="sxs-lookup"><span data-stu-id="d4479-124">ResolveMessageClass</span></span>](imapiformcontainer-resolvemessageclass.md) <br/> |<span data-ttu-id="d4479-125">将邮件类别解析为表单容器中的窗体, 并返回该窗体的窗体信息对象。</span><span class="sxs-lookup"><span data-stu-id="d4479-125">Resolves a message class to its form in a form container and returns a form information object for that form.</span></span>  <br/> |
|[<span data-ttu-id="d4479-126">ResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="d4479-126">ResolveMultipleMessageClasses</span></span>](imapiformcontainer-resolvemultiplemessageclasses.md) <br/> |<span data-ttu-id="d4479-127">将一组消息类解析为表单容器中的窗体, 并返回这些窗体的窗体信息对象的数组。</span><span class="sxs-lookup"><span data-stu-id="d4479-127">Resolves a group of message classes to their forms in a form container and returns an array of form information objects for those forms.</span></span>  <br/> |
|[<span data-ttu-id="d4479-128">CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="d4479-128">CalcFormPropSet</span></span>](imapiformcontainer-calcformpropset.md) <br/> |<span data-ttu-id="d4479-129">返回安装在表单容器中的所有表单所使用的属性的数组。</span><span class="sxs-lookup"><span data-stu-id="d4479-129">Returns an array of the properties used by all forms installed in a form container.</span></span>  <br/> |
|[<span data-ttu-id="d4479-130">GetDisplay</span><span class="sxs-lookup"><span data-stu-id="d4479-130">GetDisplay</span></span>](imapiformcontainer-getdisplay.md) <br/> |<span data-ttu-id="d4479-131">返回表单容器的显示名称。</span><span class="sxs-lookup"><span data-stu-id="d4479-131">Returns the display name of a form container.</span></span>  <br/> |
|[<span data-ttu-id="d4479-132">GetLastError</span><span class="sxs-lookup"><span data-stu-id="d4479-132">GetLastError</span></span>](imapiformcontainer-getlasterror.md) <br/> |<span data-ttu-id="d4479-133">返回一个[MAPIERROR](mapierror.md)结构, 其中包含有关在表单容器对象中发生的上一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="d4479-133">Returns a [MAPIERROR](mapierror.md) structure containing information about the previous error occurring to the form container object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="d4479-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4479-134">See also</span></span>



[<span data-ttu-id="d4479-135">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="d4479-135">MAPI Interfaces</span></span>](mapi-interfaces.md)

