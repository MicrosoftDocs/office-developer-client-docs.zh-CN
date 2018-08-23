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
ms.openlocfilehash: b2aa08ea14df87f24cda3da0137ae4bfa2c50b40
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22576013"
---
# <a name="imapiformfactory--iunknown"></a><span data-ttu-id="47d60-103">IMAPIFormFactory : IUnknown</span><span class="sxs-lookup"><span data-stu-id="47d60-103">IMAPIFormFactory : IUnknown</span></span>

  
  
<span data-ttu-id="47d60-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="47d60-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="47d60-105">支持在分布式计算环境中的可配置的运行时窗体。</span><span class="sxs-lookup"><span data-stu-id="47d60-105">Supports the use of configurable run-time forms in distributed computing environments.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="47d60-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="47d60-106">Header file:</span></span>  <br/> |<span data-ttu-id="47d60-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="47d60-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="47d60-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="47d60-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="47d60-109">窗体中心对象</span><span class="sxs-lookup"><span data-stu-id="47d60-109">Form factory objects</span></span>  <br/> |
|<span data-ttu-id="47d60-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="47d60-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="47d60-111">表单服务器</span><span class="sxs-lookup"><span data-stu-id="47d60-111">Form servers</span></span>  <br/> |
|<span data-ttu-id="47d60-112">调用：</span><span class="sxs-lookup"><span data-stu-id="47d60-112">Called by:</span></span>  <br/> |<span data-ttu-id="47d60-113">表单查看器</span><span class="sxs-lookup"><span data-stu-id="47d60-113">Form viewers</span></span>  <br/> |
|<span data-ttu-id="47d60-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="47d60-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="47d60-115">IID_IMAPIFormFactory</span><span class="sxs-lookup"><span data-stu-id="47d60-115">IID_IMAPIFormFactory</span></span>  <br/> |
|<span data-ttu-id="47d60-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="47d60-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="47d60-117">LPMAPIFORMFACTORY</span><span class="sxs-lookup"><span data-stu-id="47d60-117">LPMAPIFORMFACTORY</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="47d60-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="47d60-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="47d60-119">CreateClassFactory</span><span class="sxs-lookup"><span data-stu-id="47d60-119">CreateClassFactory</span></span>](imapiformfactory-createclassfactory.md) <br/> |<span data-ttu-id="47d60-120">返回窗体类工厂对象。</span><span class="sxs-lookup"><span data-stu-id="47d60-120">Returns a class factory object for the form.</span></span>  <br/> |
|[<span data-ttu-id="47d60-121">时出错</span><span class="sxs-lookup"><span data-stu-id="47d60-121">GetLastError</span></span>](imapiformfactory-getlasterror.md) <br/> |<span data-ttu-id="47d60-122">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面对窗体中心对象发生的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="47d60-122">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error occurring to the form factory object.</span></span>  <br/> |
|[<span data-ttu-id="47d60-123">LockServer</span><span class="sxs-lookup"><span data-stu-id="47d60-123">LockServer</span></span>](imapiformfactory-lockserver.md) <br/> |<span data-ttu-id="47d60-124">在内存中保留的打开的窗体服务器。</span><span class="sxs-lookup"><span data-stu-id="47d60-124">Keeps an open form server in memory.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="47d60-125">注解</span><span class="sxs-lookup"><span data-stu-id="47d60-125">Remarks</span></span>

<span data-ttu-id="47d60-126">**IMAPIFormFactory**接口基于[IClassFactory](http://msdn.microsoft.com/en-us/library/ms694364%28VS.85%29.aspx)接口，并实现**IMAPIFormFactory**对象应还继承**IClassFactory**。</span><span class="sxs-lookup"><span data-stu-id="47d60-126">The **IMAPIFormFactory** interface is based on the [IClassFactory](http://msdn.microsoft.com/en-us/library/ms694364%28VS.85%29.aspx) interface, and objects that implement **IMAPIFormFactory** should also inherit from **IClassFactory**.</span></span>
  
 <span data-ttu-id="47d60-127">**IMAPIFormFactory**是表单查看器用于创建新表单对象时窗体服务器支持多个邮件类的接口 （即，多个窗体的对象的类型）。</span><span class="sxs-lookup"><span data-stu-id="47d60-127">**IMAPIFormFactory** is the interface that form viewers use to create new form objects when a form server supports more than one message class (that is, more than one type of form object).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="47d60-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="47d60-128">See also</span></span>



[<span data-ttu-id="47d60-129">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="47d60-129">MAPI Interfaces</span></span>](mapi-interfaces.md)

