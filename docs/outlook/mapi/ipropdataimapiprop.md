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
ms.openlocfilehash: aed9120ac264a6c47c9d02502093e56d3268d08a
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279540"
---
# <a name="ipropdata--imapiprop"></a><span data-ttu-id="13e9e-103">IPropData : IMAPIProp</span><span class="sxs-lookup"><span data-stu-id="13e9e-103">IPropData : IMAPIProp</span></span>

  
  
<span data-ttu-id="13e9e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="13e9e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="13e9e-105">提供检索和更改对象的属性的访问权限的功能。</span><span class="sxs-lookup"><span data-stu-id="13e9e-105">Provides the ability to retrieve and change the access for an object's properties.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="13e9e-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="13e9e-106">Header file:</span></span>  <br/> |<span data-ttu-id="13e9e-107">Mapiutil</span><span class="sxs-lookup"><span data-stu-id="13e9e-107">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="13e9e-108">公开者:</span><span class="sxs-lookup"><span data-stu-id="13e9e-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="13e9e-109">属性数据对象</span><span class="sxs-lookup"><span data-stu-id="13e9e-109">Property data object</span></span>  <br/> |
|<span data-ttu-id="13e9e-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="13e9e-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="13e9e-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="13e9e-111">MAPI</span></span>  <br/> |
|<span data-ttu-id="13e9e-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="13e9e-112">Called by:</span></span>  <br/> |<span data-ttu-id="13e9e-113">服务提供商和客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="13e9e-113">Service providers and client applications</span></span>  <br/> |
|<span data-ttu-id="13e9e-114">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="13e9e-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="13e9e-115">IID_IMAPIPropData</span><span class="sxs-lookup"><span data-stu-id="13e9e-115">IID_IMAPIPropData</span></span>  <br/> |
|<span data-ttu-id="13e9e-116">指针类型:</span><span class="sxs-lookup"><span data-stu-id="13e9e-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="13e9e-117">LPPROPDATA</span><span class="sxs-lookup"><span data-stu-id="13e9e-117">LPPROPDATA</span></span>  <br/> |
|<span data-ttu-id="13e9e-118">事务模型:</span><span class="sxs-lookup"><span data-stu-id="13e9e-118">Transaction model:</span></span>  <br/> |<span data-ttu-id="13e9e-119">Nontransacted</span><span class="sxs-lookup"><span data-stu-id="13e9e-119">Nontransacted</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="13e9e-120">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="13e9e-120">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="13e9e-121">HrSetObjAccess</span><span class="sxs-lookup"><span data-stu-id="13e9e-121">HrSetObjAccess</span></span>](ipropdata-hrsetobjaccess.md) <br/> |<span data-ttu-id="13e9e-122">设置对象的访问级别。</span><span class="sxs-lookup"><span data-stu-id="13e9e-122">Sets the access level for the object.</span></span>  <br/> |
|[<span data-ttu-id="13e9e-123">HrSetPropAccess</span><span class="sxs-lookup"><span data-stu-id="13e9e-123">HrSetPropAccess</span></span>](ipropdata-hrsetpropaccess.md) <br/> |<span data-ttu-id="13e9e-124">设置一个或多个对象属性的访问级别和状态。</span><span class="sxs-lookup"><span data-stu-id="13e9e-124">Sets the access level and status for one or more of the object's properties.</span></span>  <br/> |
|[<span data-ttu-id="13e9e-125">HrGetPropAccess</span><span class="sxs-lookup"><span data-stu-id="13e9e-125">HrGetPropAccess</span></span>](ipropdata-hrgetpropaccess.md) <br/> |<span data-ttu-id="13e9e-126">检索一个或多个对象属性的访问级别和状态。</span><span class="sxs-lookup"><span data-stu-id="13e9e-126">Retrieves the access level and status for one or more of the object's properties.</span></span>  <br/> |
|[<span data-ttu-id="13e9e-127">HrAddObjProps</span><span class="sxs-lookup"><span data-stu-id="13e9e-127">HrAddObjProps</span></span>](ipropdata-hraddobjprops.md) <br/> |<span data-ttu-id="13e9e-128">将 PT_OBJECT 类型的一个或多个属性添加到对象中。</span><span class="sxs-lookup"><span data-stu-id="13e9e-128">Adds one or more properties of type PT_OBJECT to the object.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="13e9e-129">注解</span><span class="sxs-lookup"><span data-stu-id="13e9e-129">Remarks</span></span>

<span data-ttu-id="13e9e-130">**IPropData:: IMAPIProp**接口由 MAPI 实现, 并且主要由可通过调用[CreateIProp](createiprop.md)函数来访问此实现的服务提供程序使用。</span><span class="sxs-lookup"><span data-stu-id="13e9e-130">The **IPropData::IMAPIProp** interface is implemented by MAPI and used primarily by service providers that access this implementation by calling the [CreateIProp](createiprop.md) function.</span></span> 
  
<span data-ttu-id="13e9e-131">有关对象和属性的访问级别的详细信息, 请参阅[对象和属性的权限](permissions-for-mapi-objects-and-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="13e9e-131">For more information about access levels on objects and properties, see [Permissions for Objects and Properties](permissions-for-mapi-objects-and-properties.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="13e9e-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13e9e-132">See also</span></span>



[<span data-ttu-id="13e9e-133">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="13e9e-133">MAPI Interfaces</span></span>](mapi-interfaces.md)

