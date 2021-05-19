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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32342117"
---
# <a name="imapiformfactory--iunknown"></a><span data-ttu-id="4cfbb-103">IMAPIFormFactory : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4cfbb-103">IMAPIFormFactory : IUnknown</span></span>

  
  
<span data-ttu-id="4cfbb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4cfbb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4cfbb-105">支持在分布式计算环境中使用可配置的运行时表单。</span><span class="sxs-lookup"><span data-stu-id="4cfbb-105">Supports the use of configurable run-time forms in distributed computing environments.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="4cfbb-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="4cfbb-106">Header file:</span></span>  <br/> |<span data-ttu-id="4cfbb-107">Mapiform.h</span><span class="sxs-lookup"><span data-stu-id="4cfbb-107">Mapiform.h</span></span>  <br/> |
|<span data-ttu-id="4cfbb-108">公开者：</span><span class="sxs-lookup"><span data-stu-id="4cfbb-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="4cfbb-109">表单工厂对象</span><span class="sxs-lookup"><span data-stu-id="4cfbb-109">Form factory objects</span></span>  <br/> |
|<span data-ttu-id="4cfbb-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="4cfbb-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="4cfbb-111">表单服务器</span><span class="sxs-lookup"><span data-stu-id="4cfbb-111">Form servers</span></span>  <br/> |
|<span data-ttu-id="4cfbb-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="4cfbb-112">Called by:</span></span>  <br/> |<span data-ttu-id="4cfbb-113">表单查看器</span><span class="sxs-lookup"><span data-stu-id="4cfbb-113">Form viewers</span></span>  <br/> |
|<span data-ttu-id="4cfbb-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="4cfbb-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="4cfbb-115">IID_IMAPIFormFactory</span><span class="sxs-lookup"><span data-stu-id="4cfbb-115">IID_IMAPIFormFactory</span></span>  <br/> |
|<span data-ttu-id="4cfbb-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="4cfbb-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="4cfbb-117">LPMAPIFORMFACTORY</span><span class="sxs-lookup"><span data-stu-id="4cfbb-117">LPMAPIFORMFACTORY</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="4cfbb-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="4cfbb-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="4cfbb-119">CreateClassFactory</span><span class="sxs-lookup"><span data-stu-id="4cfbb-119">CreateClassFactory</span></span>](imapiformfactory-createclassfactory.md) <br/> |<span data-ttu-id="4cfbb-120">返回窗体的类工厂对象。</span><span class="sxs-lookup"><span data-stu-id="4cfbb-120">Returns a class factory object for the form.</span></span>  <br/> |
|[<span data-ttu-id="4cfbb-121">GetLastError</span><span class="sxs-lookup"><span data-stu-id="4cfbb-121">GetLastError</span></span>](imapiformfactory-getlasterror.md) <br/> |<span data-ttu-id="4cfbb-122">返回 [一个 MAPIERROR](mapierror.md) 结构，其中包含有关表单工厂对象发生的上一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="4cfbb-122">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error occurring to the form factory object.</span></span>  <br/> |
|[<span data-ttu-id="4cfbb-123">LockServer</span><span class="sxs-lookup"><span data-stu-id="4cfbb-123">LockServer</span></span>](imapiformfactory-lockserver.md) <br/> |<span data-ttu-id="4cfbb-124">将打开的表单服务器保留到内存中。</span><span class="sxs-lookup"><span data-stu-id="4cfbb-124">Keeps an open form server in memory.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4cfbb-125">备注</span><span class="sxs-lookup"><span data-stu-id="4cfbb-125">Remarks</span></span>

<span data-ttu-id="4cfbb-126">**IMAPIFormFactory** 接口基于 [IClassFactory](https://msdn.microsoft.com/library/ms694364%28VS.85%29.aspx)接口，并且实现 **IMAPIFormFactory** 的对象还应从 **IClassFactory 继承**。</span><span class="sxs-lookup"><span data-stu-id="4cfbb-126">The **IMAPIFormFactory** interface is based on the [IClassFactory](https://msdn.microsoft.com/library/ms694364%28VS.85%29.aspx) interface, and objects that implement **IMAPIFormFactory** should also inherit from **IClassFactory**.</span></span>
  
 <span data-ttu-id="4cfbb-127">**IMAPIFormFactory** 是表单查看器在表单服务器支持多个邮件类（即多个表单对象类型）时 (创建新的表单对象的接口) 。</span><span class="sxs-lookup"><span data-stu-id="4cfbb-127">**IMAPIFormFactory** is the interface that form viewers use to create new form objects when a form server supports more than one message class (that is, more than one type of form object).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4cfbb-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4cfbb-128">See also</span></span>



[<span data-ttu-id="4cfbb-129">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="4cfbb-129">MAPI Interfaces</span></span>](mapi-interfaces.md)

