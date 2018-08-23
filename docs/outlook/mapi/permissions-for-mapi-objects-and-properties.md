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
# <a name="permissions-for-mapi-objects-and-properties"></a>MAPI 对象和属性的权限

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
访问权限或的一组 permissable 操作可以是特征以及支持这些对象的各个属性的 MAPI 对象。 对象访问取决于对象的父对象。 对于一条消息，其文件夹决定访问权限。 对于消息的用户或通讯组列表中，其通讯簿容器使此决定。 当一条消息，如对象驻留在两个文件夹中时，可以不同对象的两个副本的权限。 
  
使用这些对象的客户端可以请求的最高对象允许通过[IMAPISession::OpenEntry](imapisession-openentry.md)呼叫设置 MAPI_BEST_ACCESS 标志的访问级别。 根据服务提供商实现对象后，客户端可能或可能未授予的必要的访问级别。 客户端可以确定，它们通过调用**GetProps**方法检索**PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) 属性的对象授予的访问的级别。 但是，因为服务提供商必须动态生成此属性的值，它被建议客户端检索它仅在必要时。 
  
若要确定是否如文件夹、 通讯簿容器或通讯组列表容器允许修改，请调用其**GetProps**方法来检索**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性。 容器级别访问影响客户端在其用户界面的显示方式。 它还会影响对象在其用户界面显示和其常规实现容器内的实施。 
  
设置通过 MAPI 拥有属性的对象的属性架构决定了到特定属性的访问。 属性架构指定了一组对象和其访问权限的必需的和可选属性。 与由该对象的父对象的访问，不同属性访问是全局设置。 每个对象，无论对象的父级的访问要求具有相同权限的属性确定由架构。
  
如果属性是只读的它始终将提供使用**GetProps**或**OpenProperty**呼叫。 但是，具体取决于支持属性的对象的实现，有**SetProps**方法修改的属性以及将其删除**DeleteProps**方法的两个可能的结果： 
  
- 失败并返回 MAPI_E_NO_ACCESS
    
- 成功进行任何操作
    
此外可以检索或使用从**IMAPIProp**接口继承的[IPropData](ipropdataimapiprop.md)接口设置属性和对象的访问。 MAPI 提供**IPropData**基于内存中的数据的实现。 服务提供商可以使用**IPropData**来实现**IMAPIProp**在某些情况下，例如，对于其状态对象，或如果他们使用的数据库未包含内置的事务。 **IPropData**适用于以独占方式在内存中，这样就无需锁定和解除锁定数据。 
  
## <a name="see-also"></a>另请参阅



[MAPI 属性概述](mapi-property-overview.md)

