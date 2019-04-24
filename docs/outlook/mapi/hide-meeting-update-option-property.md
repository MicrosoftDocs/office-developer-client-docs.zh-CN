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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32299508"
---
# <a name="hide-meeting-update-option-property"></a>隐藏会议更新选项属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
隐藏将会议更新仅发送给已添加或已删除的与会者的选项。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|公开于:  <br/> |[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)对象  <br/> |
|创建者:  <br/> |存储提供程序  <br/> |
|访问者:  <br/> |Outlook 和其他客户端  <br/> |
|属性类型  <br/> |PT_BOOLEAN  <br/> |
|访问类型:  <br/> |读/写  <br/> |
   
## <a name="remarks"></a>注解

若要提供任何存储功能, 存储提供程序必须实现[IMAPIProp: IUnknown](imapipropiunknown.md) , 并返回传递给[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)调用的任何这些属性的有效属性标记。 当这些属性中任一属性的属性标记传递给[IMAPIProp:: GetProps](imapiprop-getprops.md)时, 存储提供程序还必须返回正确的属性值。 存储提供程序可以调用[HrGetOneProp](hrgetoneprop.md)和[HrSetOneProp](hrsetoneprop.md)以获取或设置这些属性。 
  
若要检索此属性的值, 客户端应首先使用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)获取属性标记, 然后在[IMAPIProp:: GetProps](imapiprop-getprops.md)中指定此属性标记以获取值。 调用[IMAPIProp:: GetIDsFromNames](imapiprop-getidsfromnames.md)时, 请为输入参数_lppPropNames_所指向的[MAPINAMEID](mapinameid.md)结构指定以下值:
  
|||
|:-----|:-----|
|lpGuid:  <br/> |PS_PUBLIC_STRINGS  <br/> |
|ulKind:  <br/> |MNID_STRING  <br/> |
|类型 lpwstrName:  <br/> |L "urn: 架构-microsoft-com: office: outlook # allornonemtgupdatedlg"  <br/> |
   
使用服务器发送会议更新的存储提供程序可以修改 "**将更新发送到与会者**" 对话框。 此功能很有用, 因为当服务器发送会议更新时, 服务器不知道自最初会议请求以来用户添加或删除了哪些与会者。 当此属性为**true**时, "发送**或删除的与会者发送或删除的与会者**" 选项不会显示在 "**发送到与会者的更新**" 对话框中。 
  
如果 Outlook 的版本早于 Microsoft Office Outlook 2003 Service Pack 1, 或者其值为**false**, 则忽略此属性。
  

