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
ms.openlocfilehash: 65255e14fd849d730e92bd86027642eef2c687bc
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584973"
---
# <a name="hide-meeting-update-option-property"></a>隐藏会议更新选项属性

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
隐藏该选项发送给仅添加或删除的与会者的会议更新。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|公开上：  <br/> |[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)对象  <br/> |
|通过创建：  <br/> |存储提供程序  <br/> |
|通过来访问：  <br/> |Outlook 和其他客户端  <br/> |
|属性类型  <br/> |PT_BOOLEAN  <br/> |
|访问类型：  <br/> |读/写  <br/> |
   
## <a name="remarks"></a>备注

若要提供的任何存储功能，存储提供程序必须实现[IMAPIProp: IUnknown](imapipropiunknown.md)并返回任何传递给[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)调用这些属性的有效属性标记。 当属性标记为任何这些属性传递给[IMAPIProp::GetProps](imapiprop-getprops.md)时，存储提供程序必须也会返回正确的属性值。 [HrGetOneProp](hrgetoneprop.md)和[HrSetOneProp](hrsetoneprop.md)用于获取或设置这些属性，可以调用存储提供程序。 
  
若要检索此属性的值，客户应首先使用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)获取该属性标记，然后[IMAPIProp::GetProps](imapiprop-getprops.md)获取值中指定此属性标记。 调用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)时, 指定的输入的参数_lppPropNames_指向[MAPINAMEID](mapinameid.md)结构的以下值：
  
|||
|:-----|:-----|
|lpGuid:  <br/> |PS_PUBLIC_STRINGS  <br/> |
|ulKind:  <br/> |MNID_STRING  <br/> |
|Kind.lpwstrName:  <br/> |L"urn： 架构-microsoft-com:office:outlook #allornonemtgupdatedlg"  <br/> |
   
使用服务器发送会议更新存储提供程序可以修改**向与会者发送更新**对话框。 此功能很有用，因为当服务器发送会议更新时，服务器不知道哪些与会者已添加或删除以来初始会议请求的用户。 当此属性为**true**时，**发送给添加或删除的与会者仅更新**选项不会显示在**向与会者发送更新**对话框。 
  
如果 Outlook 版本早于 Microsoft Office Outlook 2003 Service Pack 1，或如果其值为**false**，则忽略此属性。
  

