---
title: MAPI 对象和属性的权限
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 32669cbe-5460-4043-99cc-c609608f48da
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 11c8a58e6cfe0719e8683c4e7a0fd966972117c4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22569377"
---
# <a name="permissions-for-mapi-objects-and-properties"></a><span data-ttu-id="27b42-103">MAPI 对象和属性的权限</span><span class="sxs-lookup"><span data-stu-id="27b42-103">Permissions for MAPI Objects and Properties</span></span>

  
  
<span data-ttu-id="27b42-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="27b42-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="27b42-105">访问权限或的一组 permissable 操作可以是特征以及支持这些对象的各个属性的 MAPI 对象。</span><span class="sxs-lookup"><span data-stu-id="27b42-105">Access permission, or the set of permissable operations, can be a characteristic of MAPI objects and of individual properties supported by those objects.</span></span> <span data-ttu-id="27b42-106">对象访问取决于对象的父对象。</span><span class="sxs-lookup"><span data-stu-id="27b42-106">Object access is determined by an object's parent.</span></span> <span data-ttu-id="27b42-107">对于一条消息，其文件夹决定访问权限。</span><span class="sxs-lookup"><span data-stu-id="27b42-107">For a message, its folder determines access permissions.</span></span> <span data-ttu-id="27b42-108">对于消息的用户或通讯组列表中，其通讯簿容器使此决定。</span><span class="sxs-lookup"><span data-stu-id="27b42-108">For a messaging user or distribution list, its address book container makes this determination.</span></span> <span data-ttu-id="27b42-109">当一条消息，如对象驻留在两个文件夹中时，可以不同对象的两个副本的权限。</span><span class="sxs-lookup"><span data-stu-id="27b42-109">When an object such as a message resides in two folders, the permissions for the two copies of the object can be different.</span></span> 
  
<span data-ttu-id="27b42-110">使用这些对象的客户端可以请求的最高对象允许通过[IMAPISession::OpenEntry](imapisession-openentry.md)呼叫设置 MAPI_BEST_ACCESS 标志的访问级别。</span><span class="sxs-lookup"><span data-stu-id="27b42-110">Clients using these objects can request the highest level of access permitted for the object by setting the MAPI_BEST_ACCESS flag on the [IMAPISession::OpenEntry](imapisession-openentry.md) call.</span></span> <span data-ttu-id="27b42-111">根据服务提供商实现对象后，客户端可能或可能未授予的必要的访问级别。</span><span class="sxs-lookup"><span data-stu-id="27b42-111">Depending on the service provider implementing the object, the client may or may not be granted the level of access necessary.</span></span> <span data-ttu-id="27b42-112">客户端可以确定，它们通过调用**GetProps**方法检索**PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) 属性的对象授予的访问的级别。</span><span class="sxs-lookup"><span data-stu-id="27b42-112">Clients can determine the level of access that they were granted by calling the object **GetProps** method to retrieve the **PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) property.</span></span> <span data-ttu-id="27b42-113">但是，因为服务提供商必须动态生成此属性的值，它被建议客户端检索它仅在必要时。</span><span class="sxs-lookup"><span data-stu-id="27b42-113">However, because the service provider must dynamically generate the value for this property, it is recommended that clients retrieve it only when necessary.</span></span> 
  
<span data-ttu-id="27b42-114">若要确定是否如文件夹、 通讯簿容器或通讯组列表容器允许修改，请调用其**GetProps**方法来检索**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="27b42-114">To determine whether a container such as a folder, address book container, or distribution list allows modification, call its **GetProps** method to retrieve the **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) property.</span></span> <span data-ttu-id="27b42-115">容器级别访问影响客户端在其用户界面的显示方式。</span><span class="sxs-lookup"><span data-stu-id="27b42-115">Container level access affects clients in terms of how they display their user interfaces.</span></span> <span data-ttu-id="27b42-116">它还会影响对象在其用户界面显示和其常规实现容器内的实施。</span><span class="sxs-lookup"><span data-stu-id="27b42-116">It also impacts the implementers of objects within containers in terms of their user interface display and their general implementation.</span></span> 
  
<span data-ttu-id="27b42-117">设置通过 MAPI 拥有属性的对象的属性架构决定了到特定属性的访问。</span><span class="sxs-lookup"><span data-stu-id="27b42-117">Access to a particular property is determined by the property schema set up by MAPI for the object that owns the property.</span></span> <span data-ttu-id="27b42-118">属性架构指定了一组对象和其访问权限的必需的和可选属性。</span><span class="sxs-lookup"><span data-stu-id="27b42-118">Property schemas specify the set of required and optional properties for an object and their access permission.</span></span> <span data-ttu-id="27b42-119">与由该对象的父对象的访问，不同属性访问是全局设置。</span><span class="sxs-lookup"><span data-stu-id="27b42-119">Unlike object access which is determined by the object's parent, property access is global.</span></span> <span data-ttu-id="27b42-120">每个对象，无论对象的父级的访问要求具有相同权限的属性确定由架构。</span><span class="sxs-lookup"><span data-stu-id="27b42-120">Every object, regardless of the access requirements of the object's parent, has the same permissions for the property as determined by the schema.</span></span>
  
<span data-ttu-id="27b42-121">如果属性是只读的它始终将提供使用**GetProps**或**OpenProperty**呼叫。</span><span class="sxs-lookup"><span data-stu-id="27b42-121">When a property is read-only, it will always be available with a **GetProps** or **OpenProperty** call.</span></span> <span data-ttu-id="27b42-122">但是，具体取决于支持属性的对象的实现，有**SetProps**方法修改的属性以及将其删除**DeleteProps**方法的两个可能的结果：</span><span class="sxs-lookup"><span data-stu-id="27b42-122">However, depending on the implementation of the object supporting the property, there are two possible outcomes for the **SetProps** method for modifying a property and the **DeleteProps** method for removing it:</span></span> 
  
- <span data-ttu-id="27b42-123">失败并返回 MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="27b42-123">Fail and return MAPI_E_NO_ACCESS</span></span>
    
- <span data-ttu-id="27b42-124">成功进行任何操作</span><span class="sxs-lookup"><span data-stu-id="27b42-124">Succeed with no action taken</span></span>
    
<span data-ttu-id="27b42-125">此外可以检索或使用从**IMAPIProp**接口继承的[IPropData](ipropdataimapiprop.md)接口设置属性和对象的访问。</span><span class="sxs-lookup"><span data-stu-id="27b42-125">Property and object access can also be retrieved or set by using the [IPropData](ipropdataimapiprop.md) interface that inherits from the **IMAPIProp** interface.</span></span> <span data-ttu-id="27b42-126">MAPI 提供**IPropData**基于内存中的数据的实现。</span><span class="sxs-lookup"><span data-stu-id="27b42-126">MAPI provides an implementation of **IPropData** that is based on data in memory.</span></span> <span data-ttu-id="27b42-127">服务提供商可以使用**IPropData**来实现**IMAPIProp**在某些情况下，例如，对于其状态对象，或如果他们使用的数据库未包含内置的事务。</span><span class="sxs-lookup"><span data-stu-id="27b42-127">Service providers can use **IPropData** to implement **IMAPIProp** in certain circumstances, such as for their status object or if they are using a database that does not have built-in transactions.</span></span> <span data-ttu-id="27b42-128">**IPropData**适用于以独占方式在内存中，这样就无需锁定和解除锁定数据。</span><span class="sxs-lookup"><span data-stu-id="27b42-128">**IPropData** works exclusively in memory, making it unnecessary to lock and unlock data.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="27b42-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27b42-129">See also</span></span>



[<span data-ttu-id="27b42-130">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="27b42-130">MAPI Property Overview</span></span>](mapi-property-overview.md)

