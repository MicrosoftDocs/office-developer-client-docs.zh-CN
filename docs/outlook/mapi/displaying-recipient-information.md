---
title: 显示收件人信息
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 7ffec274-ee90-44c7-ab2e-7dfb502517a6
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e1c31e5edf702dd8f172f67e7055a96ae4cfff1c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412952"
---
# <a name="displaying-recipient-information"></a>显示收件人信息

**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 提供了一个显示收件人详细信息的常用对话框。 详细信息对话框从显示表和 **IMAPIProp** 实现创建。 显示表描述详细信息显示的外观 **，IMAPIProp** 实现控制收件人的数据。 提供程序负责提供每个收件人的显示表 **和 IMAPIProp** 实现。 
  
创建显示表的最简单方法是定义 [DTPAGE](dtpage.md) 结构并调用 [BuildDisplayTable](builddisplaytable.md)。 但是，某些提供程序（特别是允许创建一次收件人的只读提供程序）使用 **IPropData**。 **IMAPIProp** 实现可以是任何类型的属性对象。 
  
有两种方法可以调用此对话框 [：IAddrBook：:D etails](iaddrbook-details.md) 和 [IMAPISupport：:D etails](imapisupport-details.md)。 当提供程序调用这些方法之一来请求收件人的详细信息时，MAPI 首先通过调用其容器的 [IMAPIContainer：：OpenEntry](imapicontainer-openentry.md) 方法打开收件人。 接下来，它调用收件人的[IMAPIProp：：OpenProperty](imapiprop-openproperty.md)方法以请求PR_DETAILS_TABLE ([PidTagDetailsTable](pidtagdetailstable-canonical-property.md)) 属性。 **PR_DETAILS_TABLE** 是表示收件人的详细信息显示表的属性。 
  
[IPropData ： IMAPIProp](ipropdataimapiprop.md)接口可用于监视显示表控件上的更改，如以下过程所述。 
  
## <a name="monitor-changes-to-a-control"></a>监视对控件的更改
  
1. 在用户获取对控件的访问权限之前，调用 [IPropData：：HrSetObjAccess](ipropdata-hrsetobjaccess.md) 以设置控件对控件IPROP_CLEAN。 
    
2. 允许用户使用对话框。 
    
3. 用户完成后，调用 [IPropData：：HrGetPropAccess](ipropdata-hrgetpropaccess.md) 检索控件的当前访问级别。 
    
4. 如果访问级别为 IPROP_DIRTY，则用户已修改控件。 提供程序应：
    
   - 调用 [IPropData：：HrSetPropAccess](ipropdata-hrsetpropaccess.md) 将访问级别设置回IPROP_CLEAN。 
    
   - 调用属性数据对象的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法来检索已更改的属性，然后通过调用 [IMAPIProp：：SetProps 更新它](imapiprop-setprops.md)。
    
5. 如果访问级别仍处于IPROP_CLEAN，则尚未修改该控件。 
    
有关创建显示表的信息，请参阅显示 [表](display-tables.md)。
  

