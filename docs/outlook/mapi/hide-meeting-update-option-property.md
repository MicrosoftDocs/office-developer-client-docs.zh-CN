---
title: 隐藏会议更新选项属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- Hide Meeting Update Option Property
api_type:
- COM
ms.assetid: 9e7b413f-a88a-a4ec-8d57-1f3058cce4a4
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: ac7c891fa05560231a257f9bd52ccbbfe564b49d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33412098"
---
# <a name="hide-meeting-update-option-property"></a>隐藏会议更新选项属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
隐藏仅向添加或删除的与会者发送会议更新的选项。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|在：  <br/> |[IMsgStore ： IMAPIProp](imsgstoreimapiprop.md) 对象  <br/> |
|创建者：  <br/> |存储提供程序  <br/> |
|访问者：  <br/> |Outlook客户端和其他客户端  <br/> |
|属性类型  <br/> |PT_BOOLEAN  <br/> |
|访问类型：  <br/> |读/写  <br/> |
   
## <a name="remarks"></a>备注

若要提供任何存储功能，存储提供程序必须实现 [IMAPIProp ： IUnknown](imapipropiunknown.md) 并返回传递给 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 调用的任何属性的有效属性标记。 当其中任何属性的属性标记传递到 [IMAPIProp：：GetProps](imapiprop-getprops.md)时，存储提供程序还必须返回正确的属性值。 存储提供程序可以调用 [HrGetOneProp](hrgetoneprop.md) 和 [HrSetOneProp](hrsetoneprop.md) 获取或设置这些属性。 
  
若要检索此属性的值，客户端应首先使用 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 获取属性标记，然后在 [IMAPIProp：：GetProps](imapiprop-getprops.md) 中指定此属性标记以获取值。 调用 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md)时，为输入参数 _lppPropNames_ 指向的 [MAPINAMEID](mapinameid.md)结构指定以下值：
  
|||
|:-----|:-----|
|lpGuid：  <br/> |PS_PUBLIC_STRINGS  <br/> |
|ulKind：  <br/> |MNID_STRING  <br/> |
|Kind.lpwstrName：  <br/> |L"urn：schemas-microsoft-com：office：outlook#allornonemtgupdatedlg"  <br/> |
   
使用服务器发送会议更新的应用商店提供商可以修改"将更新发送到 **与会者"** 对话框。 此功能很有用，因为服务器发送会议更新时，服务器不知道自初始会议请求以来用户已添加或删除了哪些与会者。 当此属性为 **true** 时 **，"仅** 向已添加或删除的与会者发送更新"选项不会显示在"将更新发送到 **与会者"** 对话框中。 
  
如果服务包的版本早于 Outlook 2003 Service Pack 1 Microsoft Office Outlook或其值为 **false，** 则忽略此属性。
  

