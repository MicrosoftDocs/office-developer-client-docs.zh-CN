---
title: 显示服务器文件夹大小属性
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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32337077"
---
# <a name="display-server-folder-sizes-property"></a>显示服务器文件夹大小属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
在 "Outlook**文件夹大小**" 对话框中显示服务器上指定文件夹的大小。 
  
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
|类型 lpwstrName:  <br/> |L "urn: 架构-microsoft-com: office: outlook # serverfoldersizes"  <br/> |
   
此属性在 Microsoft Outlook 2003 Service Pack (SP) 1 中受支持。 如果 outlook 的版本早于 outlook 2003 SP 1, 或者其值为**false**, 则 outlook 将仅显示本地存储区上的文件夹大小。 如果在使用 Outlook 2003 SP 1 的存储上设置此属性, 则 Outlook 将查询服务器和本地驱动器上的每个指定文件夹的大小。 
  
若要在服务器上查询文件夹大小, Outlook 将使用[IMsgStore:: OpenEntry](imsgstore-openentry.md)打开存储区中的文件夹, 并传递标志**MAPI_NO_CACHE**, 然后对**PR_MESSAGE_SIZE_EXTENDED**进行查询。 然后, 存储提供程序应返回服务器上的文件夹大小。
  
若要查询本地驱动器上文件夹的大小, Outlook 将打开不带**MAPI_NO_CACHE**标志的文件夹。 然后, 它查询**PR_MESSAGE_SIZE_EXTENDED**;存储提供程序应返回本地驱动器上指定文件夹的大小。
  
设置了此属性后, 将存储内容同步到服务器的存储提供程序可以在 "Outlook**文件夹大小**" 对话框中显示服务器上的文件夹大小数据。 然后, 用户可以将当前的服务器存储使用率与服务器配额进行比较。 
  

