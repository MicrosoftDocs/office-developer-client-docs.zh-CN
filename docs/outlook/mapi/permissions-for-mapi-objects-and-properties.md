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
# <a name="permissions-for-mapi-objects-and-properties"></a>MAPI 对象和属性的权限

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
访问权限或可允许的操作集可以是 MAPI 对象和这些对象所支持各个属性的特征。 对象访问由对象的父对象决定。 对于邮件，其文件夹确定访问权限。 对于邮件用户或通讯组列表，其通讯簿容器会做出此决定。 当邮件等对象驻留在两个文件夹中时，该对象的两个副本的权限可能不同。 
  
使用这些对象的客户端可以通过在 [IMAPISession：：OpenEntry](imapisession-openentry.md) 调用上设置 MAPI_BEST_ACCESS 标志来请求对象允许的最高访问权限级别。 根据实现该对象的服务提供商，客户端可能获得或可能不会被授予必要的访问级别。 客户端可以通过调用对象 **GetProps** 方法检索 PR_ACCESS ([PidTagAccess](pidtagaccess-canonical-property.md)属性来确定) 级别。  但是，由于服务提供商必须动态生成此属性的值，因此建议客户端仅在必要时检索该值。 
  
若要确定容器（如文件夹、通讯簿容器或通讯组列表）是否允许修改，请调用其 **GetProps** 方法来检索 **PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性。 容器级别访问会影响客户端显示其用户界面的方法。 它还会影响容器中对象的实现者，包括其用户界面显示及其常规实现。 
  
对特定属性的访问由 MAPI 为拥有该属性的对象设置的属性架构确定。 属性架构指定对象及其访问权限的必需属性和可选属性集。 与由对象的父对象确定的对象访问不同，属性访问是全局访问。 无论对象的父对象的访问要求如何，每个对象对属性具有相同的权限（由架构确定）。
  
当属性为只读时，它将始终可用于 **GetProps** 或 **OpenProperty** 调用。 但是，根据支持属性的对象的实现， **修改属性的 SetProps** 方法和删除该属性的 **DeleteProps** 方法有两种可能的结果： 
  
- 失败并返回MAPI_E_NO_ACCESS
    
- 成功，不执行任何操作
    
通过使用继承自 **IMAPIProp** 接口的 [IPropData](ipropdataimapiprop.md)接口，还可以检索或设置属性和对象访问。 MAPI 提供基于内存中数据的 **IPropData** 的实现。 在某些情况下，服务提供商可以使用 **IPropData** 实现 **IMAPIProp，** 例如，对于其状态对象，或者他们使用的数据库没有内置事务。 **IPropData** 以独占方式在内存中工作，因此无需锁定和解锁数据。 
  
## <a name="see-also"></a>另请参阅



[MAPI 属性概述](mapi-property-overview.md)

