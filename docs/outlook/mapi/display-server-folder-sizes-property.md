---
title: Display Server Folder Sizes 属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- Display Server Folder Sizes Property
api_type:
- COM
ms.assetid: 38429fdb-be93-213a-a780-80f9837f55fa
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 85a8b5216eac1dd4e4cebd1313cb31c9b5d70227
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434548"
---
# <a name="display-server-folder-sizes-property"></a>Display Server Folder Sizes 属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在"文件夹大小"对话框中显示Outlook **指定** 文件夹的大小。 
  
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
|Kind.lpwstrName：  <br/> |L"urn：schemas-microsoft-com：office：outlook#serverfoldersizes"  <br/> |
   
此属性在 Microsoft Outlook 2003 Service Pack (SP) 1 中受支持。 如果 Outlook 的版本早于 Outlook 2003 SP 1，或者其值为 **false，Outlook** 将仅显示本地存储上文件夹的大小。 如果在使用 Outlook 2003 SP 1 的存储区上设置此属性，Outlook 将查询服务器和本地驱动器上每个指定文件夹的大小。 
  
若要在服务器上查询文件夹大小，Outlook [使用 IMsgStore：：OpenEntry](imsgstore-openentry.md)打开存储区上的文件夹，并传递标志 **MAPI_NO_CACHE**，然后查询 PR_MESSAGE_SIZE_EXTENDED **。** 然后，存储提供程序应在服务器上返回文件夹大小。
  
若要查询本地驱动器上文件夹的大小，Outlook打开不带 MAPI_NO_CACHE **标志的文件夹**。 然后，它将 **查询PR_MESSAGE_SIZE_EXTENDED**;存储提供程序应返回本地驱动器上指定文件夹的大小。
  
通过设置此属性，将存储内容同步到服务器的存储提供程序显示文件夹"文件夹大小"对话框中Outlook **服务器上存储** 大小数据。 然后，用户可以将其当前服务器存储使用情况与服务器配额进行比较。 
  

