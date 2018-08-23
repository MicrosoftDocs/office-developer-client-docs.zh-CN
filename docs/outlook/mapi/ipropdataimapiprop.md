---
title: IPropData IMAPIProp
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPropData
api_type:
- COM
ms.assetid: 30b8ae9e-0c0c-4468-b286-29e083696fed
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: c320b2c42b9a14c6dc428fc3df59991528cdbe36
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22592568"
---
# <a name="ipropdata--imapiprop"></a><span data-ttu-id="bb39d-103">IPropData : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="bb39d-103">IPropData : IMAPIProp</span></span>

  
  
<span data-ttu-id="bb39d-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bb39d-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bb39d-105">提供能够检索和更改对象的属性的访问。</span><span class="sxs-lookup"><span data-stu-id="bb39d-105">Provides the ability to retrieve and change the access for an object's properties.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="bb39d-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="bb39d-106">Header file:</span></span>  <br/> |<span data-ttu-id="bb39d-107">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="bb39d-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="bb39d-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="bb39d-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="bb39d-109">属性的数据对象</span><span class="sxs-lookup"><span data-stu-id="bb39d-109">Property data object</span></span>  <br/> |
|<span data-ttu-id="bb39d-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="bb39d-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="bb39d-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="bb39d-111">MAPI</span></span>  <br/> |
|<span data-ttu-id="bb39d-112">调用：</span><span class="sxs-lookup"><span data-stu-id="bb39d-112">Called by:</span></span>  <br/> |<span data-ttu-id="bb39d-113">服务提供商和客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="bb39d-113">Service providers and client applications</span></span>  <br/> |
|<span data-ttu-id="bb39d-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="bb39d-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="bb39d-115">IID_IMAPIPropData</span><span class="sxs-lookup"><span data-stu-id="bb39d-115">IID_IMAPIPropData</span></span>  <br/> |
|<span data-ttu-id="bb39d-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="bb39d-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="bb39d-117">LPPROPDATA</span><span class="sxs-lookup"><span data-stu-id="bb39d-117">LPPROPDATA</span></span>  <br/> |
|<span data-ttu-id="bb39d-118">事务模型：</span><span class="sxs-lookup"><span data-stu-id="bb39d-118">Transaction model:</span></span>  <br/> |<span data-ttu-id="bb39d-119">Nontransacted</span><span class="sxs-lookup"><span data-stu-id="bb39d-119">Nontransacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="bb39d-120">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="bb39d-120">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="bb39d-121">HrSetObjAccess</span><span class="sxs-lookup"><span data-stu-id="bb39d-121">HrSetObjAccess</span></span>](ipropdata-hrsetobjaccess.md) <br/> |<span data-ttu-id="bb39d-122">设置该对象的访问级别。</span><span class="sxs-lookup"><span data-stu-id="bb39d-122">Sets the access level for the object.</span></span>  <br/> |
|[<span data-ttu-id="bb39d-123">HrSetPropAccess</span><span class="sxs-lookup"><span data-stu-id="bb39d-123">HrSetPropAccess</span></span>](ipropdata-hrsetpropaccess.md) <br/> |<span data-ttu-id="bb39d-124">设置访问级别和一个或多个对象的属性的状态。</span><span class="sxs-lookup"><span data-stu-id="bb39d-124">Sets the access level and status for one or more of the object's properties.</span></span>  <br/> |
|[<span data-ttu-id="bb39d-125">HrGetPropAccess</span><span class="sxs-lookup"><span data-stu-id="bb39d-125">HrGetPropAccess</span></span>](ipropdata-hrgetpropaccess.md) <br/> |<span data-ttu-id="bb39d-126">检索的访问级别和一个或多个对象的属性的状态。</span><span class="sxs-lookup"><span data-stu-id="bb39d-126">Retrieves the access level and status for one or more of the object's properties.</span></span>  <br/> |
|[<span data-ttu-id="bb39d-127">HrAddObjProps</span><span class="sxs-lookup"><span data-stu-id="bb39d-127">HrAddObjProps</span></span>](ipropdata-hraddobjprops.md) <br/> |<span data-ttu-id="bb39d-128">添加到对象类型 PT_OBJECT 的一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="bb39d-128">Adds one or more properties of type PT_OBJECT to the object.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="bb39d-129">注解</span><span class="sxs-lookup"><span data-stu-id="bb39d-129">Remarks</span></span>

<span data-ttu-id="bb39d-130">**IPropData::IMAPIProp**接口是由 MAPI 实现，主要由服务提供商访问此实现通过调用[CreateIProp](createiprop.md)函数。</span><span class="sxs-lookup"><span data-stu-id="bb39d-130">The **IPropData::IMAPIProp** interface is implemented by MAPI and used primarily by service providers that access this implementation by calling the [CreateIProp](createiprop.md) function.</span></span> 
  
<span data-ttu-id="bb39d-131">有关访问级别上对象和属性的详细信息，请参阅[权限对象和属性](permissions-for-mapi-objects-and-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="bb39d-131">For more information about access levels on objects and properties, see [Permissions for Objects and Properties](permissions-for-mapi-objects-and-properties.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bb39d-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bb39d-132">See also</span></span>



[<span data-ttu-id="bb39d-133">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="bb39d-133">MAPI Interfaces</span></span>](mapi-interfaces.md)

