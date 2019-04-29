---
title: 显示表实现
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: eb17675a-35e0-4545-b394-789d343510aa
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 6990e32445083c3465693df2c1a3d40b980853c4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435262"
---
# <a name="display-table-implementation"></a>显示表实现

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
显示表用于显示属性表, 这是一个特殊的对话框, 它由一个或多个选项卡式属性页组成, 专用于显示一个或多个属性, 并可能对其进行编辑。 与每个显示表相关的是[IAttach: IMAPIProp](iattachimapiprop.md)接口实现。 [IMAPIProp](imapipropiunknown.md)实现维护属性表中显示的属性数据。 
  
显示表中的行表示属性表中的控件。 大多数控件都可以与**IMAPIProp**实现所维护的属性相关联。 当用户更改了可修改控件的值时, 相应的属性也会更新。 
  
显示表中的列表示控件的属性, 如属性在属性表中的位置、类型、关联的结构和标识符。 有关必需的显示表格列的完整列表, 请参阅[显示表](display-tables.md)。
  
MAPI 通过读取与显示表关联的**IMAPIProp**实现中的属性值或直接从显示表中读取属性值, 来向客户端应用程序的用户显示属性表。 当用户使用属性表时, 如果更改了控件中的值, MAPI 调用[IMAPIProp:: SetProps](imapiprop-setprops.md)可以保存已更改的控件 (如果设置了控件的 DT_SET_IMMEDIATE 标志)。 对于没有设置 DT_SET_IMMEDIATE 标志的控件, 当用户通过单击 **"确定" 或 "** **立即应用**" 按钮消除对话框时, 将保存对属性所做的更改。 当单击这些按钮中的任何一个或 "**取消**" 按钮时, MAPI 都会从视图中删除属性表。 
  
MAPI 通过在**IMAPIProp**实现中调用[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法并请求**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性或通过将其继承在中, 可以获得对您的显示表的访问权限。对 MAPI 所做的呼叫 (如[IMAPISupport::D oconfigpropsheet](imapisupport-doconfigpropsheet.md))。
  
当要求通讯簿提供程序显示邮件用户或通讯组列表的详细信息时, 将使用第一种访问技术。 将发生以下处理:
  
1. 客户端调用[IAddrBook::D etails](iaddrbook-details.md)方法。 
    
2. MAPI 调用通讯簿提供程序的[IABLogon:: OpenEntry](iablogon-openentry.md)方法来访问代表所选条目的邮件用户。 
    
3. MAPI 调用邮件用户的[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)方法来检索**PR_DETAILS_TABLE**属性, 即 "详细信息" 对话框的显示表。 
    
4. MAPI 显示对话框, 处理用户与信息的交互, 并在用户完成时将其删除。 
    
## <a name="see-also"></a>另请参阅



[MAPI 服务提供程序](mapi-service-providers.md)

