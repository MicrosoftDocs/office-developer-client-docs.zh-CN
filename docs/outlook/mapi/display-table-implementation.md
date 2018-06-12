---
title: 显示表实现
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: eb17675a-35e0-4545-b394-789d343510aa
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 07ad94c423c3be425dc905dc578f55ad2c467a95
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774790"
---
# <a name="display-table-implementation"></a>显示表实现

  
  
**适用于**： Outlook 
  
显示表用于显示属性表、 特殊的对话框中，其中包含的专用于显示和可能编辑一个或多个属性的一个或多个选项卡式的属性页。 关联与每个显示表是[IAttach: IMAPIProp](iattachimapiprop.md)接口实现。 [IMAPIProp](imapipropiunknown.md)实现维护属性表中显示的属性数据。 
  
显示表中的行代表属性表中的控件。 大多数控件都可以与维护**IMAPIProp**实现与属性关联。 当用户更改可修改的控件的值时，将更新的相应属性。 
  
显示表中的列表示的控件，如在属性表、 类型、 关联的结构及其标识符中的位置的属性。 所需的显示表格列的完整列表，请参阅[显示表](display-tables.md)。
  
MAPI 通过读取属性值从与显示表格关联的**IMAPIProp**实现或显示表直接向客户端应用程序的用户显示属性表。 当用户与属性表，MAPI 更改值在控件中，调用[IMAPIProp::SetProps](imapiprop-setprops.md)保存已更改的控件，如果设置控件的 DT_SET_IMMEDIATE 标志。 对于没有设置 DT_SET_IMMEDIATE 标志的控件，当用户通过单击**确定**或**立即应用**按钮消除对话框保存对属性的更改。 单击这些按钮或**取消**按钮时，MAPI 从视图中删除的属性表。 
  
MAPI 获取的访问权显示表，通过在**IMAPIProp**实现中调用[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法，并要求**PR_DETAILS_TABLE** ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性或继承其中对 MAPI，如[IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md)所做的呼叫。
  
通讯簿提供程序时要求您显示有关消息用户或通讯组列表的详细信息时使用的第一个访问技术。 进行以下处理：
  
1. 客户端调用[IAddrBook::Details](iaddrbook-details.md)方法。 
    
2. MAPI 调用通讯簿提供程序的[IABLogon::OpenEntry](iablogon-openentry.md)方法来访问表示所选的项目的消息用户。 
    
3. MAPI 调用的消息的用户[IMAPIProp::OpenProperty](imapiprop-openproperty.md)方法来检索**PR_DETAILS_TABLE**属性，详细信息对话框的显示表。 
    
4. MAPI 显示的对话框中，处理用户交互的信息，并在完成后用户将其删除。 
    
## <a name="see-also"></a>另请参阅



[MAPI 服务提供商](mapi-service-providers.md)

