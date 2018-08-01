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
ms.openlocfilehash: 39f255a277403073132dfd3cd21c995eefe904c9
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775400"
---
# <a name="imapiformcontainer--iunknown"></a><span data-ttu-id="8b9ba-103">IMAPIFormContainer : IUnknown</span><span class="sxs-lookup"><span data-stu-id="8b9ba-103">IMAPIFormContainer : IUnknown</span></span>

  
  
<span data-ttu-id="8b9ba-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="8b9ba-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8b9ba-105">管理表单库中的窗体。</span><span class="sxs-lookup"><span data-stu-id="8b9ba-105">Manages forms in form libraries.</span></span> <span data-ttu-id="8b9ba-106">此接口用于创建特定于应用程序的表单库。</span><span class="sxs-lookup"><span data-stu-id="8b9ba-106">This interface is used to create application-specific form libraries.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="8b9ba-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="8b9ba-107">Header file:</span></span>  <br/> |<span data-ttu-id="8b9ba-108">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="8b9ba-108">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="8b9ba-109">由公开：</span><span class="sxs-lookup"><span data-stu-id="8b9ba-109">Exposed by:</span></span>  <br/> |<span data-ttu-id="8b9ba-110">窗体的容器对象</span><span class="sxs-lookup"><span data-stu-id="8b9ba-110">Form container objects</span></span>  <br/> |
|<span data-ttu-id="8b9ba-111">通过实现：</span><span class="sxs-lookup"><span data-stu-id="8b9ba-111">Implemented by:</span></span>  <br/> |<span data-ttu-id="8b9ba-112">窗体库提供程序</span><span class="sxs-lookup"><span data-stu-id="8b9ba-112">Form library providers</span></span>  <br/> |
|<span data-ttu-id="8b9ba-113">调用：</span><span class="sxs-lookup"><span data-stu-id="8b9ba-113">Called by:</span></span>  <br/> |<span data-ttu-id="8b9ba-114">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="8b9ba-114">Client applications</span></span>  <br/> |
|<span data-ttu-id="8b9ba-115">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="8b9ba-115">Interface identifier:</span></span>  <br/> |<span data-ttu-id="8b9ba-116">IID_IMAPIFormContainer</span><span class="sxs-lookup"><span data-stu-id="8b9ba-116">IID_IMAPIFormContainer</span></span>  <br/> |
|<span data-ttu-id="8b9ba-117">指针类型：</span><span class="sxs-lookup"><span data-stu-id="8b9ba-117">Pointer type:</span></span>  <br/> |<span data-ttu-id="8b9ba-118">LPMAPIFORMCONTAINER</span><span class="sxs-lookup"><span data-stu-id="8b9ba-118">LPMAPIFORMCONTAINER</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="8b9ba-119">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="8b9ba-119">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="8b9ba-120">InstallForm</span><span class="sxs-lookup"><span data-stu-id="8b9ba-120">InstallForm</span></span>](imapiformcontainer-installform.md) <br/> |<span data-ttu-id="8b9ba-121">将窗体安装到窗体容器。</span><span class="sxs-lookup"><span data-stu-id="8b9ba-121">Installs a form into a form container.</span></span>  <br/> |
|[<span data-ttu-id="8b9ba-122">RemoveForm</span><span class="sxs-lookup"><span data-stu-id="8b9ba-122">RemoveForm</span></span>](imapiformcontainer-removeform.md) <br/> |<span data-ttu-id="8b9ba-123">从窗体容器中删除特定的窗体。</span><span class="sxs-lookup"><span data-stu-id="8b9ba-123">Removes a particular form from a form container.</span></span>  <br/> |
|[<span data-ttu-id="8b9ba-124">ResolveMessageClass</span><span class="sxs-lookup"><span data-stu-id="8b9ba-124">ResolveMessageClass</span></span>](imapiformcontainer-resolvemessageclass.md) <br/> |<span data-ttu-id="8b9ba-125">解析为其窗体的窗体容器中的邮件类，并返回该窗体的窗体信息对象。</span><span class="sxs-lookup"><span data-stu-id="8b9ba-125">Resolves a message class to its form in a form container and returns a form information object for that form.</span></span>  <br/> |
|[<span data-ttu-id="8b9ba-126">ResolveMultipleMessageClasses</span><span class="sxs-lookup"><span data-stu-id="8b9ba-126">ResolveMultipleMessageClasses</span></span>](imapiformcontainer-resolvemultiplemessageclasses.md) <br/> |<span data-ttu-id="8b9ba-127">解析为其在窗体容器中的窗体的邮件类的一组，并返回这些表单的信息对象的窗体的数组。</span><span class="sxs-lookup"><span data-stu-id="8b9ba-127">Resolves a group of message classes to their forms in a form container and returns an array of form information objects for those forms.</span></span>  <br/> |
|[<span data-ttu-id="8b9ba-128">CalcFormPropSet</span><span class="sxs-lookup"><span data-stu-id="8b9ba-128">CalcFormPropSet</span></span>](imapiformcontainer-calcformpropset.md) <br/> |<span data-ttu-id="8b9ba-129">返回一个数组由安装窗体容器中的所有窗体的属性。</span><span class="sxs-lookup"><span data-stu-id="8b9ba-129">Returns an array of the properties used by all forms installed in a form container.</span></span>  <br/> |
|[<span data-ttu-id="8b9ba-130">GetDisplay</span><span class="sxs-lookup"><span data-stu-id="8b9ba-130">GetDisplay</span></span>](imapiformcontainer-getdisplay.md) <br/> |<span data-ttu-id="8b9ba-131">返回一个窗体容器的显示名称。</span><span class="sxs-lookup"><span data-stu-id="8b9ba-131">Returns the display name of a form container.</span></span>  <br/> |
|[<span data-ttu-id="8b9ba-132">时出错</span><span class="sxs-lookup"><span data-stu-id="8b9ba-132">GetLastError</span></span>](imapiformcontainer-getlasterror.md) <br/> |<span data-ttu-id="8b9ba-133">返回包含有关以前对窗体容器对象发生的错误的信息的[MAPIERROR](mapierror.md)结构。</span><span class="sxs-lookup"><span data-stu-id="8b9ba-133">Returns a [MAPIERROR](mapierror.md) structure containing information about the previous error occurring to the form container object.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="8b9ba-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b9ba-134">See also</span></span>



[<span data-ttu-id="8b9ba-135">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="8b9ba-135">MAPI Interfaces</span></span>](mapi-interfaces.md)

