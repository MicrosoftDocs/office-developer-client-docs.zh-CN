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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348592"
---
# <a name="permissions-for-mapi-objects-and-properties"></a><span data-ttu-id="4fcae-103">MAPI 对象和属性的权限</span><span class="sxs-lookup"><span data-stu-id="4fcae-103">Permissions for MAPI Objects and Properties</span></span>

  
  
<span data-ttu-id="4fcae-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4fcae-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4fcae-105">访问权限或 permissable 操作集可以是 MAPI 对象的特征, 也可以是这些对象支持的各个属性。</span><span class="sxs-lookup"><span data-stu-id="4fcae-105">Access permission, or the set of permissable operations, can be a characteristic of MAPI objects and of individual properties supported by those objects.</span></span> <span data-ttu-id="4fcae-106">对象访问由对象的父对象决定。</span><span class="sxs-lookup"><span data-stu-id="4fcae-106">Object access is determined by an object's parent.</span></span> <span data-ttu-id="4fcae-107">对于邮件, 其文件夹决定了访问权限。</span><span class="sxs-lookup"><span data-stu-id="4fcae-107">For a message, its folder determines access permissions.</span></span> <span data-ttu-id="4fcae-108">对于邮件用户或通讯组列表, 其通讯簿容器做出此决定。</span><span class="sxs-lookup"><span data-stu-id="4fcae-108">For a messaging user or distribution list, its address book container makes this determination.</span></span> <span data-ttu-id="4fcae-109">当一个对象 (如邮件) 位于两个文件夹中时, 该对象的两个副本的权限可以不同。</span><span class="sxs-lookup"><span data-stu-id="4fcae-109">When an object such as a message resides in two folders, the permissions for the two copies of the object can be different.</span></span> 
  
<span data-ttu-id="4fcae-110">使用这些对象的客户端可以通过在[IMAPISession:: OpenEntry](imapisession-openentry.md)调用上设置 MAPI_BEST_ACCESS 标志来请求允许的最高级别的访问权限。</span><span class="sxs-lookup"><span data-stu-id="4fcae-110">Clients using these objects can request the highest level of access permitted for the object by setting the MAPI_BEST_ACCESS flag on the [IMAPISession::OpenEntry](imapisession-openentry.md) call.</span></span> <span data-ttu-id="4fcae-111">根据实现该对象的服务提供程序, 客户端可能会或可能不会被授予所需的访问权限级别。</span><span class="sxs-lookup"><span data-stu-id="4fcae-111">Depending on the service provider implementing the object, the client may or may not be granted the level of access necessary.</span></span> <span data-ttu-id="4fcae-112">客户端可以通过调用对象**GetProps**方法来检索**PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) 属性, 从而确定授予它们的访问级别。</span><span class="sxs-lookup"><span data-stu-id="4fcae-112">Clients can determine the level of access that they were granted by calling the object **GetProps** method to retrieve the **PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) property.</span></span> <span data-ttu-id="4fcae-113">但是, 由于服务提供程序必须为此属性动态生成值, 因此建议客户端仅在必要时才进行检索。</span><span class="sxs-lookup"><span data-stu-id="4fcae-113">However, because the service provider must dynamically generate the value for this property, it is recommended that clients retrieve it only when necessary.</span></span> 
  
<span data-ttu-id="4fcae-114">若要确定文件夹、通讯簿容器或通讯组列表等容器是否允许修改, 请调用其**GetProps**方法以检索**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="4fcae-114">To determine whether a container such as a folder, address book container, or distribution list allows modification, call its **GetProps** method to retrieve the **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) property.</span></span> <span data-ttu-id="4fcae-115">容器级访问将根据客户端显示其用户界面的方式影响客户端。</span><span class="sxs-lookup"><span data-stu-id="4fcae-115">Container level access affects clients in terms of how they display their user interfaces.</span></span> <span data-ttu-id="4fcae-116">它还会影响容器中的对象在其用户界面显示及其常规实现方面的实现。</span><span class="sxs-lookup"><span data-stu-id="4fcae-116">It also impacts the implementers of objects within containers in terms of their user interface display and their general implementation.</span></span> 
  
<span data-ttu-id="4fcae-117">对特定属性的访问由 MAPI 为拥有该属性的对象设置的属性架构确定。</span><span class="sxs-lookup"><span data-stu-id="4fcae-117">Access to a particular property is determined by the property schema set up by MAPI for the object that owns the property.</span></span> <span data-ttu-id="4fcae-118">属性架构指定对象及其访问权限的必需属性和可选属性的集合。</span><span class="sxs-lookup"><span data-stu-id="4fcae-118">Property schemas specify the set of required and optional properties for an object and their access permission.</span></span> <span data-ttu-id="4fcae-119">与由对象的父对象所确定的对象访问不同, 属性访问是全局的。</span><span class="sxs-lookup"><span data-stu-id="4fcae-119">Unlike object access which is determined by the object's parent, property access is global.</span></span> <span data-ttu-id="4fcae-120">每个对象 (无论对象的父对象的访问要求如何) 与该架构所确定的属性具有相同的权限。</span><span class="sxs-lookup"><span data-stu-id="4fcae-120">Every object, regardless of the access requirements of the object's parent, has the same permissions for the property as determined by the schema.</span></span>
  
<span data-ttu-id="4fcae-121">当属性为只读时, 它将始终在**GetProps**或**OpenProperty**调用中可用。</span><span class="sxs-lookup"><span data-stu-id="4fcae-121">When a property is read-only, it will always be available with a **GetProps** or **OpenProperty** call.</span></span> <span data-ttu-id="4fcae-122">但是, 根据支持属性的对象的实现, 用于修改属性的**SetProps**方法和用于删除属性的**DeleteProps**方法有两种可能的结果:</span><span class="sxs-lookup"><span data-stu-id="4fcae-122">However, depending on the implementation of the object supporting the property, there are two possible outcomes for the **SetProps** method for modifying a property and the **DeleteProps** method for removing it:</span></span> 
  
- <span data-ttu-id="4fcae-123">失败并返回 MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="4fcae-123">Fail and return MAPI_E_NO_ACCESS</span></span>
    
- <span data-ttu-id="4fcae-124">成功时不执行任何操作</span><span class="sxs-lookup"><span data-stu-id="4fcae-124">Succeed with no action taken</span></span>
    
<span data-ttu-id="4fcae-125">还可以使用继承自**IMAPIProp**接口的[IPropData](ipropdataimapiprop.md)接口来检索或设置属性和对象访问。</span><span class="sxs-lookup"><span data-stu-id="4fcae-125">Property and object access can also be retrieved or set by using the [IPropData](ipropdataimapiprop.md) interface that inherits from the **IMAPIProp** interface.</span></span> <span data-ttu-id="4fcae-126">MAPI 提供了基于内存中的数据的**IPropData**的实现。</span><span class="sxs-lookup"><span data-stu-id="4fcae-126">MAPI provides an implementation of **IPropData** that is based on data in memory.</span></span> <span data-ttu-id="4fcae-127">在某些情况下, 服务提供程序可以使用**IPropData**来实现**IMAPIProp** , 例如, 针对其状态对象或使用没有内置事务的数据库。</span><span class="sxs-lookup"><span data-stu-id="4fcae-127">Service providers can use **IPropData** to implement **IMAPIProp** in certain circumstances, such as for their status object or if they are using a database that does not have built-in transactions.</span></span> <span data-ttu-id="4fcae-128">**IPropData**在内存中以独占方式运行, 因此不必锁定和解锁数据。</span><span class="sxs-lookup"><span data-stu-id="4fcae-128">**IPropData** works exclusively in memory, making it unnecessary to lock and unlock data.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4fcae-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4fcae-129">See also</span></span>



[<span data-ttu-id="4fcae-130">MAPI 属性概述</span><span class="sxs-lookup"><span data-stu-id="4fcae-130">MAPI Property Overview</span></span>](mapi-property-overview.md)

