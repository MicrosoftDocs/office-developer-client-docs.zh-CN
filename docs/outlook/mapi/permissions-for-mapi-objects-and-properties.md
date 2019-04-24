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
# <a name="permissions-for-mapi-objects-and-properties"></a>MAPI 对象和属性的权限

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
访问权限或 permissable 操作集可以是 MAPI 对象的特征, 也可以是这些对象支持的各个属性。 对象访问由对象的父对象决定。 对于邮件, 其文件夹决定了访问权限。 对于邮件用户或通讯组列表, 其通讯簿容器做出此决定。 当一个对象 (如邮件) 位于两个文件夹中时, 该对象的两个副本的权限可以不同。 
  
使用这些对象的客户端可以通过在[IMAPISession:: OpenEntry](imapisession-openentry.md)调用上设置 MAPI_BEST_ACCESS 标志来请求允许的最高级别的访问权限。 根据实现该对象的服务提供程序, 客户端可能会或可能不会被授予所需的访问权限级别。 客户端可以通过调用对象**GetProps**方法来检索**PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) 属性, 从而确定授予它们的访问级别。 但是, 由于服务提供程序必须为此属性动态生成值, 因此建议客户端仅在必要时才进行检索。 
  
若要确定文件夹、通讯簿容器或通讯组列表等容器是否允许修改, 请调用其**GetProps**方法以检索**PR_ACCESS_LEVEL** ([PidTagAccessLevel](pidtagaccesslevel-canonical-property.md)) 属性。 容器级访问将根据客户端显示其用户界面的方式影响客户端。 它还会影响容器中的对象在其用户界面显示及其常规实现方面的实现。 
  
对特定属性的访问由 MAPI 为拥有该属性的对象设置的属性架构确定。 属性架构指定对象及其访问权限的必需属性和可选属性的集合。 与由对象的父对象所确定的对象访问不同, 属性访问是全局的。 每个对象 (无论对象的父对象的访问要求如何) 与该架构所确定的属性具有相同的权限。
  
当属性为只读时, 它将始终在**GetProps**或**OpenProperty**调用中可用。 但是, 根据支持属性的对象的实现, 用于修改属性的**SetProps**方法和用于删除属性的**DeleteProps**方法有两种可能的结果: 
  
- 失败并返回 MAPI_E_NO_ACCESS
    
- 成功时不执行任何操作
    
还可以使用继承自**IMAPIProp**接口的[IPropData](ipropdataimapiprop.md)接口来检索或设置属性和对象访问。 MAPI 提供了基于内存中的数据的**IPropData**的实现。 在某些情况下, 服务提供程序可以使用**IPropData**来实现**IMAPIProp** , 例如, 针对其状态对象或使用没有内置事务的数据库。 **IPropData**在内存中以独占方式运行, 因此不必锁定和解锁数据。 
  
## <a name="see-also"></a>另请参阅



[MAPI 属性概述](mapi-property-overview.md)

