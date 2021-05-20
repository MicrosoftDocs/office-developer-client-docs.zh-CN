---
title: MAPI 对象和属性的权限
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 32669cbe-5460-4043-99cc-c609608f48da
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4efa9cd1596cffe19a19a62059f81fa553343d77
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33436172"
---
# <a name="permissions-for-mapi-objects-and-properties"></a><span data-ttu-id="bbd71-103">MAPI 对象和属性的权限</span><span class="sxs-lookup"><span data-stu-id="bbd71-103">Permissions for MAPI Objects and Properties</span></span>

  
  
<span data-ttu-id="bbd71-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="bbd71-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="bbd71-105">访问权限或可允许的操作集可以是 MAPI 对象和这些对象所支持各个属性的特征。</span><span class="sxs-lookup"><span data-stu-id="bbd71-105">Access permission, or the set of permissable operations, can be a characteristic of MAPI objects and of individual properties supported by those objects.</span></span> <span data-ttu-id="bbd71-106">对象访问由对象的父对象决定。</span><span class="sxs-lookup"><span data-stu-id="bbd71-106">Object access is determined by an object's parent.</span></span> <span data-ttu-id="bbd71-107">对于邮件，其文件夹确定访问权限。</span><span class="sxs-lookup"><span data-stu-id="bbd71-107">For a message, its folder determines access permissions.</span></span> <span data-ttu-id="bbd71-108">对于邮件用户或通讯组列表，其通讯簿容器会做出此决定。</span><span class="sxs-lookup"><span data-stu-id="bbd71-108">For a messaging user or distribution list, its address book container makes this determination.</span></span> <span data-ttu-id="bbd71-109">当邮件等对象驻留在两个文件夹中时，该对象的两个副本的权限可能不同。</span><span class="sxs-lookup"><span data-stu-id="bbd71-109">When an object such as a message resides in two folders, the permissions for the two copies of the object can be different.</span></span> 
  
<span data-ttu-id="bbd71-110">使用这些对象的客户端可以通过在 [IMAPISession：：OpenEntry](imapisession-openentry.md) 调用上设置 MAPI_BEST_ACCESS 标志来请求对象允许的最高访问权限级别。</span><span class="sxs-lookup"><span data-stu-id="bbd71-110">Clients using these objects can request the highest level of access permitted for the object by setting the MAPI_BEST_ACCESS flag on the [IMAPISession::OpenEntry](imapisession-openentry.md) call.</span></span> <span data-ttu-id="bbd71-111">根据实现该对象的服务提供商，客户端可能获得或可能不会被授予必要的访问级别。</span><span class="sxs-lookup"><span data-stu-id="bbd71-111">Depending on the service provider implementing the object, the client may or may not be granted the level of access necessary.</span></span> <span data-ttu-id="bbd71-112">客户端可以通过调用对象 **GetProps** 方法检索 PR_ACCESS ([PidTagAccess](pidtagaccess-canonical-property.md)属性来确定) 级别。 </span><span class="sxs-lookup"><span data-stu-id="bbd71-112">Clients can determine the level of access that they were granted by calling the object **GetProps** method to retrieve the **PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) property.</span></span> <span data-ttu-id="bbd71-113">但是，由于服务提供商必须动态生成此属性的值，因此建议客户端仅在必要时检索该值。</span><span class="sxs-lookup"><span data-stu-id="bbd71-113">However, because the service provider must dynamically generate the value for this property, it is recommended that clients retrieve it only when necessary.</span></span> 
  
<span data-ttu-id="bbd71-114">若要确定容器（如文件夹、通讯簿容器或通讯组列表）是否允许修改，请调用其 **GetProps** 方法来检索 **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="bbd71-114">To determine whether a container such as a folder, address book container, or distribution list allows modification, call its **GetProps** method to retrieve the **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) property.</span></span> <span data-ttu-id="bbd71-115">容器级别访问会影响客户端显示其用户界面的方法。</span><span class="sxs-lookup"><span data-stu-id="bbd71-115">Container level access affects clients in terms of how they display their user interfaces.</span></span> <span data-ttu-id="bbd71-116">它还会影响容器中对象的实现者，包括其用户界面显示及其常规实现。</span><span class="sxs-lookup"><span data-stu-id="bbd71-116">It also impacts the implementers of objects within containers in terms of their user interface display and their general implementation.</span></span> 
  
<span data-ttu-id="bbd71-117">对特定属性的访问由 MAPI 为拥有该属性的对象设置的属性架构确定。</span><span class="sxs-lookup"><span data-stu-id="bbd71-117">Access to a particular property is determined by the property schema set up by MAPI for the object that owns the property.</span></span> <span data-ttu-id="bbd71-118">属性架构指定对象及其访问权限的必需属性和可选属性集。</span><span class="sxs-lookup"><span data-stu-id="bbd71-118">Property schemas specify the set of required and optional properties for an object and their access permission.</span></span> <span data-ttu-id="bbd71-119">与由对象的父对象确定的对象访问不同，属性访问是全局访问。</span><span class="sxs-lookup"><span data-stu-id="bbd71-119">Unlike object access which is determined by the object's parent, property access is global.</span></span> <span data-ttu-id="bbd71-120">无论对象的父对象的访问要求如何，每个对象对属性具有相同的权限（由架构确定）。</span><span class="sxs-lookup"><span data-stu-id="bbd71-120">Every object, regardless of the access requirements of the object's parent, has the same permissions for the property as determined by the schema.</span></span>
  
<span data-ttu-id="bbd71-121">当属性为只读时，它将始终可用于 **GetProps** 或 **OpenProperty** 调用。</span><span class="sxs-lookup"><span data-stu-id="bbd71-121">When a property is read-only, it will always be available with a **GetProps** or **OpenProperty** call.</span></span> <span data-ttu-id="bbd71-122">但是，根据支持属性的对象的实现， **修改属性的 SetProps** 方法和删除该属性的 **DeleteProps** 方法有两种可能的结果：</span><span class="sxs-lookup"><span data-stu-id="bbd71-122">However, depending on the implementation of the object supporting the property, there are two possible outcomes for the **SetProps** method for modifying a property and the **DeleteProps** method for removing it:</span></span> 
  
- <span data-ttu-id="bbd71-123">失败并返回MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="bbd71-123">Fail and return MAPI_E_NO_ACCESS</span></span>
    
- <span data-ttu-id="bbd71-124">成功，不执行任何操作</span><span class="sxs-lookup"><span data-stu-id="bbd71-124">Succeed with no action taken</span></span>
    
<span data-ttu-id="bbd71-125">通过使用继承自 **IMAPIProp** 接口的 [IPropData](ipropdataimapiprop.md)接口，还可以检索或设置属性和对象访问。</span><span class="sxs-lookup"><span data-stu-id="bbd71-125">Property and object access can also be retrieved or set by using the [IPropData](ipropdataimapiprop.md) interface that inherits from the **IMAPIProp** interface.</span></span> <span data-ttu-id="bbd71-126">MAPI 提供基于内存中数据的 **IPropData** 的实现。</span><span class="sxs-lookup"><span data-stu-id="bbd71-126">MAPI provides an implementation of **IPropData** that is based on data in memory.</span></span> <span data-ttu-id="bbd71-127">在某些情况下，服务提供商可以使用 **IPropData** 实现 **IMAPIProp，** 例如，对于其状态对象，或者他们使用的数据库没有内置事务。</span><span class="sxs-lookup"><span data-stu-id="bbd71-127">Service providers can use **IPropData** to implement **IMAPIProp** in certain circumstances, such as for their status object or if they are using a database that does not have built-in transactions.</span></span> <span data-ttu-id="bbd71-128">**IPropData** 以独占方式在内存中工作，因此无需锁定和解锁数据。</span><span class="sxs-lookup"><span data-stu-id="bbd71-128">**IPropData** works exclusively in memory, making it unnecessary to lock and unlock data.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="bbd71-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bbd71-129">See also</span></span>



[<span data-ttu-id="bbd71-130">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="bbd71-130">MAPI Property Overview</span></span>](mapi-property-overview.md)

