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
  
显示表用于显示一个属性表一个特殊的对话框，该对话框由一个或多个专用于显示和可能编辑一个或多个属性的选项卡式属性页组成。 与每个显示表关联的是 [IAttach ： IMAPIProp](iattachimapiprop.md) 接口实现。 [IMAPIProp](imapipropiunknown.md)实现维护数据展示的属性属性表。 
  
显示表中的行表示窗体中的属性表。 大多数控件都可以与使用 **IMAPIProp** 实现维护的属性相关联。 当用户更改可修改控件的值时，将更新相应的属性。 
  
显示表中的列表示控件的属性，如控件在控件属性表、类型、关联结构和标识符。 有关所需显示表格列的完整列表，请参阅[Display Tables。](display-tables.md)
  
MAPI 通过属性表与显示表关联的 **IMAPIProp** 实现或直接读取显示表中的属性值，向客户端应用程序的用户显示数据。 在用户使用更改控件属性表时，MAPI 调用 [IMAPIProp：：SetProps](imapiprop-setprops.md) 以保存更改的控件（如果控件的 DT_SET_IMMEDIATE 标志已设置）。 对于未设置DT_SET_IMMEDIATE控件，当用户通过单击"确定"或"立即应用"按钮关闭对话框时，将保存对 **属性** 的更改。 当单击其中任一按钮或"取消"按钮时，MAPI 会从属性表中删除该按钮。 
  
MAPI 通过调用 [IMAPIProp 实现中的 IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法并请求 **PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性，或在调用 MAPI（如 [IMAPISupport：:D oConfigPropsheet）](imapisupport-doconfigpropsheet.md)时继承它，获取对显示表的访问权限。
  
当要求通讯簿提供程序显示有关邮件用户或通讯组列表的详细信息时，会使用第一种访问技术。 将发生以下处理：
  
1. 客户端调用 [IAddrBook：:D etails](iaddrbook-details.md) 方法。 
    
2. MAPI 调用通讯簿提供程序的 [IABLogon：：OpenEntry](iablogon-openentry.md) 方法来访问表示所选条目的邮件用户。 
    
3. MAPI 调用消息用户的 [IMAPIProp：：OpenProperty](imapiprop-openproperty.md) 方法来检索 **PR_DETAILS_TABLE** 属性，即详细信息对话框的显示表。 
    
4. MAPI 显示对话框，处理用户与信息的交互，在用户完成后将其删除。 
    
## <a name="see-also"></a>另请参阅



[MAPI 服务提供程序](mapi-service-providers.md)

