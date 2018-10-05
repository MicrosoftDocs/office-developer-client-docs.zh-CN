---
title: IMAPIFormFactory IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormFactory
api_type:
- COM
ms.assetid: 637be364-c393-430a-84b3-2c96aa553c22
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c60b542852653bd617b5b9f604bbc44d575e5cb3
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25384764"
---
# <a name="imapiformfactory--iunknown"></a><span data-ttu-id="e6bbb-103">IMAPIFormFactory : IUnknown</span><span class="sxs-lookup"><span data-stu-id="e6bbb-103">IMAPIFormFactory : IUnknown</span></span>

  
  
<span data-ttu-id="e6bbb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="e6bbb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="e6bbb-105">支持在分布式计算环境中的可配置的运行时窗体。</span><span class="sxs-lookup"><span data-stu-id="e6bbb-105">Supports the use of configurable run-time forms in distributed computing environments.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="e6bbb-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="e6bbb-106">Header file:</span></span>  <br/> |<span data-ttu-id="e6bbb-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="e6bbb-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="e6bbb-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="e6bbb-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="e6bbb-109">窗体中心对象</span><span class="sxs-lookup"><span data-stu-id="e6bbb-109">Form factory objects</span></span>  <br/> |
|<span data-ttu-id="e6bbb-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="e6bbb-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="e6bbb-111">表单服务器</span><span class="sxs-lookup"><span data-stu-id="e6bbb-111">Form servers</span></span>  <br/> |
|<span data-ttu-id="e6bbb-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="e6bbb-112">Called by:</span></span>  <br/> |<span data-ttu-id="e6bbb-113">表单查看器</span><span class="sxs-lookup"><span data-stu-id="e6bbb-113">Form viewers</span></span>  <br/> |
|<span data-ttu-id="e6bbb-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="e6bbb-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="e6bbb-115">IID_IMAPIFormFactory</span><span class="sxs-lookup"><span data-stu-id="e6bbb-115">IID_IMAPIFormFactory</span></span>  <br/> |
|<span data-ttu-id="e6bbb-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="e6bbb-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="e6bbb-117">LPMAPIFORMFACTORY</span><span class="sxs-lookup"><span data-stu-id="e6bbb-117">LPMAPIFORMFACTORY</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="e6bbb-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="e6bbb-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="e6bbb-119">CreateClassFactory</span><span class="sxs-lookup"><span data-stu-id="e6bbb-119">CreateClassFactory</span></span>](imapiformfactory-createclassfactory.md) <br/> |<span data-ttu-id="e6bbb-120">返回窗体类工厂对象。</span><span class="sxs-lookup"><span data-stu-id="e6bbb-120">Returns a class factory object for the form.</span></span>  <br/> |
|[<span data-ttu-id="e6bbb-121">时出错</span><span class="sxs-lookup"><span data-stu-id="e6bbb-121">GetLastError</span></span>](imapiformfactory-getlasterror.md) <br/> |<span data-ttu-id="e6bbb-122">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面对窗体中心对象发生的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="e6bbb-122">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error occurring to the form factory object.</span></span>  <br/> |
|[<span data-ttu-id="e6bbb-123">LockServer</span><span class="sxs-lookup"><span data-stu-id="e6bbb-123">LockServer</span></span>](imapiformfactory-lockserver.md) <br/> |<span data-ttu-id="e6bbb-124">在内存中保留的打开的窗体服务器。</span><span class="sxs-lookup"><span data-stu-id="e6bbb-124">Keeps an open form server in memory.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="e6bbb-125">说明</span><span class="sxs-lookup"><span data-stu-id="e6bbb-125">Remarks</span></span>

<span data-ttu-id="e6bbb-126">**IMAPIFormFactory**接口基于[IClassFactory](https://msdn.microsoft.com/library/ms694364%28VS.85%29.aspx)接口，并实现**IMAPIFormFactory**对象应还继承**IClassFactory**。</span><span class="sxs-lookup"><span data-stu-id="e6bbb-126">The **IMAPIFormFactory** interface is based on the [IClassFactory](https://msdn.microsoft.com/library/ms694364%28VS.85%29.aspx) interface, and objects that implement **IMAPIFormFactory** should also inherit from **IClassFactory**.</span></span>
  
 <span data-ttu-id="e6bbb-127">**IMAPIFormFactory**是表单查看器用于创建新表单对象时窗体服务器支持多个邮件类的接口 （即，多个窗体的对象的类型）。</span><span class="sxs-lookup"><span data-stu-id="e6bbb-127">**IMAPIFormFactory** is the interface that form viewers use to create new form objects when a form server supports more than one message class (that is, more than one type of form object).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="e6bbb-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6bbb-128">See also</span></span>



[<span data-ttu-id="e6bbb-129">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="e6bbb-129">MAPI Interfaces</span></span>](mapi-interfaces.md)

